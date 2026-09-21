# gao-depin-releases

**Public release distribution for Gao DePIN.** This repository publishes accepted release
artifacts of the Gao DePIN app (today: the Android APK, Developer Preview) as immutable GitHub
Release assets, so that anyone can download them from a stable URL and verify them.

| | |
|---|---|
| **Canonical engineering source** | `gao-core/gao-depin` — private. Source code is not published here. |
| **Public distribution** | `gao-developer/gao-depin-releases` — this repository. Release artifacts and their public metadata only. |

This repository contains no source code, no engineering history, no signing keys, no wallet
material, no node identities, no credentials and no internal logs. Its Git history is a
publication history: one commit per publication, generated from accepted artifacts.

## What is here

| Path | Content |
|---|---|
| `releases/<tag>/artifact-record.json` | the machine-readable identity of every artifact published under that tag (filename, canonical source commit, SHA-256, size, package, version, signer fingerprint, release tier, acceptance) — preserved byte-for-byte from the release's first publication, as provenance |
| `releases/<tag>/SHA256SUMS` | the SHA-256 of every asset of that release, `sha256sum -c` / `shasum -a 256 -c` shaped — preserved byte-for-byte |
| `releases/<tag>/publication.json` | the current publication record: where the release is published now, its assets and their digests, and the provenance of its first publication |
| `releases/index.json` | the index of every release published here |
| GitHub Releases | the artifacts themselves, attached to the tag named in the records |

## Distribution policy

- **Immutable.** A release asset is never replaced, re-uploaded, renamed or deleted once
  published; a newer build is published under a new tag. Tags are never moved.
- **Source-addressed.** A tag names the source revision it was built from
  (`depin-<platform>-<tier>-<sha8>`), and the record binds the exact commit of the canonical
  repository. A tag here does not point at that commit — the source is private — the record does.
- **Byte-exact.** An asset is the exact accepted artifact: never rebuilt, re-signed, aligned,
  recompressed or repackaged for publication. Its SHA-256 is measured from the bytes and listed
  in the record, in `SHA256SUMS` and in the release notes.
- **Truthfully labelled.** The release tier is stated on every release. A **Developer Preview**
  (DEV) build is signed with a development certificate, is not on Google Play or the App Store,
  and is not a Product, stable or GA release.
- **Generic.** An artifact carries no device-specific state: no node identity, owner wallet,
  membership intent, handoff session or device identifier.
- **Published after acceptance only.** A release reaches this repository after its acceptance
  in the canonical engineering process; future releases are published here.

## Verify a download

```
shasum -a 256 <file>        # macOS
sha256sum <file>            # Linux
```

The value must equal the SHA-256 in the release notes, in `releases/<tag>/SHA256SUMS` and in
`releases/<tag>/artifact-record.json`.

## Where to download

The Gao Developer Portal lists the current builds with their identity and install steps:
https://dev-sdk.gao.global/downloads/ (DEV). The Download buttons there link straight to
release assets.

## Publication history

The first release generation (`depin-android-dev-9d5aa12d`, 2026-09-19) was first published at
`github.com/gao-core/gao-depin-releases`, which remains the historical location of that
publication. The same accepted bytes are published here; `releases/<tag>/publication.json`
records both locations and the digests that bind them.
