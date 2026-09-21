# Distribution policy

1. **Scope.** This repository distributes accepted built artifacts of Gao DePIN and their
   public metadata. Nothing else is committed here: no application source, no engineering
   history, no key material, no credentials, no logs.
2. **Source of truth.** The canonical engineering source is `gao-core/gao-depin` (private).
   Every release records `source_repository` and `source_sha` in
   `releases/<tag>/artifact-record.json`, in `releases/<tag>/publication.json` and in the
   release notes. A canonical source identifier is provenance; no source content is published.
3. **Publication boundary.** Releases are published one way — from the canonical engineering
   process, after acceptance, into this public distribution repository. This repository has
   no engineering authority: nothing is developed, reviewed or built here.
4. **Tag naming.** `depin-<platform>-<tier>-<sha8>` — e.g. `depin-android-dev-9d5aa12d`.
   `<tier>` is `dev` for a Developer Preview. No `product/`, `stable`, `ga` or store naming.
5. **Immutability.** Assets and tags are never modified or removed. A correction is a new tag.
   A hash-bound record (`artifact-record.json`, `SHA256SUMS`) is never edited in place; a new
   fact is a new record (`publication.json`).
6. **Publication gate.** Before an asset is attached: its SHA-256 and size must equal the
   accepted values of the acceptance record; the archive is listed and must carry no
   identity-, key-, owner-, wallet-, intent- or state-shaped entry; a secret-safety review
   (credential filetypes and patterns) must pass. The verdicts are written in the record.
7. **Round trip.** After publication the asset is downloaded back anonymously and must hash
   to the recorded SHA-256 before any download surface links to it.
8. **Historical locations.** A release first published elsewhere keeps its original records
   byte-for-byte here as provenance; `publication.json` names the current location.
