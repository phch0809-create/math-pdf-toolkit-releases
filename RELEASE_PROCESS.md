# Math PDF Toolkit — Release Process (Windows)

**State: PRE-RELEASE.** This document is a gate, not an authorization to publish files.

## 1. Release scope

- This public repository contains **only** distribution instructions, approved release assets hosted as GitHub Releases, a machine-readable public update manifest when approved, and required license notices.
- Keep source, users' PDFs, student records, user feedback, logs, keys, access tokens, and any private material OUT of this repository.
- **Do not publish** private development ZIPs or a build with an unresolved Windows startup hang.
- `releases/latest.json` MUST NOT be created or pointed to a real ZIP until a package clears all gates below.
- The Friends Preview v0.8.x is not yet a validated stable release; preserve it separately.

## 2. Build and QA gate

For each proposed version:

1. Build the portable Windows x64 ZIP from a clean, verified source revision (record the source SHA and build environment).
2. Inspect generated ZIP paths for traversal/symlink surprises; compute exact byte size and SHA-256.
3. Run unit/regression tests for PDF compress, merge, split, previews and history; verify original PDFs remain untouched.
4. Run `MathPDFToolkit.exe --doctor` **from the bundled ZIP** on actual Windows.
5. Run **the actual startup path** (including default browser-first mode). Load the UI, add at least five PDFs, check that compress/merge/split work and finish without freezes or crashes.
6. Repeat launch and a representative operation on another Windows machine without Python installed.
7. Inspect packaged third-party notices, licenses (including native binaries), privacy statements, and any required copyright attributions. Perform a malware/security review and consider signing binaries.
8. Test application shutdown; feedback/history persistence; cancellation; in-progress PDF safety; update rejection of bad ZIP, incorrect hash, missing EXE, failed doctor or revoked release.
9. Record evidence and an explicit approver for public release. If any test fails, keep the release HOLD.

The previous version must remain installed and usable. Settings, PDFs, feedback and history must not be wiped. Never run destructive changes against real teaching/customer files to test the updater.

## 3. Publish a verified candidate

1. Draft GitHub Release with tag `vX.Y.Z` in **this** repository.
2. Upload the exact verified portable ZIP as a **Release asset**, not a source file.
3. Copy the asset's final HTTPS download URL and run `release_tools/make_manifest.py` from the **private development source** with that verified ZIP and its version. This calculates size and SHA-256; do not use example values or manually guess.
4. Compare generated checksum/size with the local ZIP; independently download the Release asset and verify again.
5. Publish verified release notes and third-party license notices.
6. After release and the download URL are confirmed publicly accessible, publish `releases/latest.json` (schema 1) on `main`. It must reference the same Release asset and its exact size and SHA-256.
7. Run real update checks from a test computer; approve download, verify hash, install side-by-side, pass `--doctor`, relaunch and verify rollback on failure.
8. Roll out to more users only after tester acceptance. Preserve the prior stable release and checksum for rollback.

**A GitHub commit, a local smoke test, or creation of a Release draft is not proof of completed rollout.**

## 4. Manifest source-of-truth

`releases/latest.json` is an **opt-in live endpoint only after approval**, served as:
`https://raw.githubusercontent.com/phch0809-create/math-pdf-toolkit-releases/main/releases/latest.json`

Expected fields, matching the existing v0.9.2 updater:
- `schema`: integer `1`
- `version`: dotted numeric version (e.g. `0.9.3`)
- `notes`: release notes string
- `download_url`: approved HTTPS Release ZIP asset URL
- `size_bytes`: actual archive byte size
- `sha256`: lowercase 64-digit digest for that exact ZIP

Until an approved stable release, **the live file is deliberately absent**. A `404` must be treated as "update channel not configured" or "no verified release" — never a green "latest" claim.

## 5. Security, privacy and updates

- Application must check only allowlisted HTTPS hosts and validate both checksum and size.
- User explicitly approves download and installation; no forced background restart while processing PDFs.
- Retain a prior working release on failure, and do not silently delete files.
- For widespread distribution, consider signed version manifests and Authenticode signing, not only a mutable HTTPS manifest plus a checksum supplied by the same channel.
- Update metadata describes program files only; no user PDF contents or diagnostics are required to check for updates.

See `SECURITY.md` for vulnerability reporting.
