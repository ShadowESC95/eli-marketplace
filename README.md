# ELI Marketplace

Plugins and MCP servers for [ELI](https://geteli.tech). Browse the store at
**[plugins.geteli.tech](https://plugins.geteli.tech)**.

This repository *is* the marketplace. The store page is generated from
`index.json`, and ELI fetches that same file — so what you see listed is exactly
what the client will accept.

## Installing something

You don't install from here. Open ELI, go to **Settings → 🛒 Marketplace**, find
the plugin and click Install. ELI verifies the checksum and signature, scans the
file with every scanner available on your machine, and asks you about each
permission before anything is written to disk.

A website is not allowed to trigger an install. If it were, the browser would
become the attack surface and the consent dialog would be spoofable.

## Submitting a plugin

Open a pull request adding a directory under `plugins/`:

```
plugins/your_plugin/
  plugin.py          # the plugin itself
  eli_plugin.json    # its manifest, including every permission it needs
```

What happens next:

1. **CI reviews it automatically.** The same checks a user's machine runs — the
   manifest is validated, the code is checked against what it declares, and
   eleven scanners look at it. The verdict is posted as a comment.
2. **A maintainer reads it.** CI cannot approve; it can only reject or say "ready
   for a human". If a scanner could approve, the signature would attest to nothing
   but the scanner's opinion.
3. **If approved, it is signed and merged.** The signature is the approval. Your
   plugin appears on the store on the next deploy.

Nothing goes live because a timer expired, and there is no upload endpoint. The
default state of every submission is "not listed".

### What gets a submission rejected outright

- **Using a capability the manifest doesn't declare.** This is the big one. The
  consent dialog is built from your manifest, so undeclared code reaches past what
  the user agreed to. Declare everything you use.
- Malware indicators from any scanner.
- A manifest that doesn't parse, or an id that isn't 2–48 lowercase characters.

### What gets you asked questions

- **Permissions you declare but don't appear to use.** Ask for the least you need;
  a broad ask is usually copy-paste, but it will be queried.
- A permission set that doesn't match the description. A unit converter asking for
  `network` needs to explain itself. No scanner can judge this, which is the whole
  reason a person reviews.

### Testing your submission before you open the PR

```bash
python /path/to/ELI/tools/marketplace/review.py plugins/your_plugin
```

Exit 0 means no blocking findings. It does not mean approved.

## Selling a plugin

A listing may carry a `price` and a `purchase_url`, and may require a licence key
that the client passes to your own server. ELI does not process payments and
cannot confirm one happened. Review is not escrow — that is between you and the
buyer.

## What review means

A person read the code and nothing objected. That raises the floor. It does not
prove the author is who they say, that a plugin does what it claims, or that a
later version is as careful as the one that was read. ELI still asks the user
about every capability and enforces them while the plugin runs.
