# ELI Marketplace — Developer Terms

> **Status: draft for solicitor review.** These terms apply to anyone who submits a package to the
> ELI marketplace. Opening a pull request that adds or changes a package means you accept them.
> **Open items** (marked **[to confirm]**): governing law (§13) and the indemnity wording (§10).

## Plain-English summary

- **Your package stays yours.** You keep its copyright and choose its licence and its price.
- **We only take what we need to run the store.** That is the right to host, scan, review, sign,
  list and distribute your package.
- **You can sell it however you like:** free, one-off purchase, subscription, trial, or a free client
  for a paid service of your own. You handle payment, refunds and tax. The marketplace takes no fee.
- **Review is a security check, not a guarantee.** We check that the code does what its permissions
  say. We do not certify that it is good, or vouch for who you are.
- **A version never changes once it is approved.** To change anything, publish a new version, which
  is reviewed again.
- **We can delist a package** that turns out to be malicious, infringing or seriously vulnerable.
  We will tell you why, and you can appeal.

---

## 1. Definitions

- **"We", "us":** Jason Fitzgibbon Bridgeman, operator of the ELI marketplace.
- **"You", "publisher":** the person or organisation submitting a package.
- **"Package":** a plugin, MCP server, bundle, integration or other software you submit, with its
  manifest, listing text, icons and screenshots.
- **"Version":** one exact build of a package, identified by its id and version number.
- **"ELI":** ELI v3 and its successors, licensed under the ELI End User Licence Agreement.

## 2. Ownership and your choice of licence

2.1 You keep all rights in your package. Submitting it transfers no ownership to us.

2.2 You choose the licence your package is distributed under: for example MIT, Apache-2.0, a
GPL-family licence, or your own proprietary terms. You must state it in the manifest (`license`, and
`license_url` for anything other than a standard licence).

2.3 You choose your business model: free, perpetual purchase, subscription, trial, or a free package
that connects to a paid product of your own. You must state it accurately in the manifest
(`purchase`).

## 3. The licence you give us

You grant us a non-exclusive, worldwide, royalty-free licence to host, copy, scan, test, review, sign,
index, display and distribute your package, and to show your name, logo and listing text, as far as
we need to operate the marketplace. This licence ends when your package is removed, except that we may
keep:

- copies and review records we need for security, audit and provenance; and
- the ability for people who already obtained a version to verify and reinstall that version.

## 4. Building on ELI

4.1 **Interface licence.** We grant you a non-exclusive, worldwide, royalty-free licence to use ELI's
published plugin, bundle and MCP interfaces to build packages, and to distribute and sell those
packages under terms you choose, without a separate agreement with us. Those interfaces are the
manifest format, the plugin base classes and host API, the bundle contract and ELI's MCP integration.

4.2 **What it does not include.** This licence gives you no right to distribute ELI itself, or any
part of ELI beyond what a package needs in order to call those interfaces. Your package must not
include or redistribute ELI's code or binaries.

4.3 **Development copy.** To build and test a package you need a licensed copy of ELI, or a trial.

4.4 **Compatibility.** We will aim to keep the interfaces compatible within a major version of ELI,
and to announce changes in advance. Declare the range of ELI versions your package supports in the
manifest (`eli_min_version`, `eli_max_version`).

## 5. What you promise

You promise that:

1. you have the right to submit everything in the package, including its code, dependencies, assets
   and trademarks, and that distributing it as described does not infringe anyone's rights;
2. you comply with the licences of everything your package includes or depends on;
3. the manifest declares **every** permission and capability the package uses, and nothing in the
   package reaches beyond them;
4. the package contains no malware and nothing designed to deceive the user, evade review or behave
   differently once installed;
5. if the package sends or receives data over a network, or handles personal data, your listing links
   to a privacy notice (`privacy_url`) that says what it sends, where it goes and why; and
6. your listing describes the package, its price and its purchase model accurately.

## 6. Selling your package

6.1 Payment is between you and the buyer. You are responsible for checkout, taxes, refunds, support,
and any licence keys or entitlements your package uses. ELI does not process payments and cannot
confirm that one happened. Review is not escrow.

6.2 The marketplace currently charges no fee. If we later offer an optional integrated checkout, any
fee will apply only to sales made through it, and you will be told before you opt in.

6.3 If you sell perpetual licences, please plan for your buyers being able to keep using what they
bought if your licence server or business goes away.

## 7. Review, approval and versions

7.1 **Every version is reviewed.** Automated checks run first. They can reject a version, or pass it
to a person, but they cannot approve it. A person reads the code and decides.

7.2 **Approval is a signature.** On approval we sign a release statement for that exact version. It
covers the package id, the version number, the SHA-256 of the file, the declared permissions, the
dependencies and the MCP launch command. ELI refuses an official-marketplace listing whose statement
is unsigned or does not match.

7.3 **Versions are immutable.** An approved version never changes. Changing any of the things in §7.2
needs a new version number and a new review, and asking for more permissions gets a closer review.
Listing text, price display, screenshots and support links may be updated without a new review.

7.4 **Review depth follows risk.** A package with no permissions gets a lighter review than one asking
for file-system writes, process execution, credentials or control of the machine. Packages in
high-consequence fields may be limited to official or invited publishers.

7.5 **What review means.** Review means a person read that version and found nothing objectionable.
It is not a warranty, it does not certify that the package is fit for any purpose, it is not
professional certification, and it does not prove your identity.

## 8. Official packages

Packages published by us, such as ELI Legal and ELI VR, are marked **Official ELI** in the client.
That label means published and supported by us. No third-party package will carry it.

## 9. Security, delisting and appeal

9.1 **Reporting.** Report vulnerabilities in your package to us promptly, along with your plan to fix
them. If you believe a signing key of yours is compromised, tell us immediately.

9.2 **Delisting.** We may delist a package, withdraw approval of a version or warn users about it if
we find malicious behaviour, undeclared permissions or capabilities, infringement, a serious
unpatched vulnerability, or a material breach of these terms.

9.3 **Notice.** We will tell you why, unless doing so first would put users at risk. In that case we
will act first and tell you afterwards.

9.4 **Users.** Where it is safe, users who already installed a version keep it and are told why it was
delisted. Where it is not safe, ELI disables or quarantines the package and explains why. It does not
silently delete users' files.

9.5 **Appeal.** You may appeal a delisting by email. A person who did not make the original decision
will review the appeal where that is practical.

## 10. Responsibility

You are responsible for your package and for claims arising from it. You agree to compensate us for
losses caused by a breach of your promises in §5. **[to confirm: indemnity wording]** We provide the
marketplace "as is", and to the extent the law allows we are not liable to you for lost sales, profits
or data arising from listing, reviewing or delisting a package.

## 11. Ending these terms

You can remove your package at any time by asking us. We can stop listing it under §9. §§3, 9.4 and
10 continue after removal.

## 12. Changes

We may change these terms for future submissions and will announce changes in this repository.
A change does not apply to a version that was approved before it, unless you agree.

## 13. Governing law

**[to confirm]**

Contact: [jaybridgeman0095@gmail.com](mailto:jaybridgeman0095@gmail.com)
