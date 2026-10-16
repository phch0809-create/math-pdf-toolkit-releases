# Math PDF Toolkit — Official Releases

**Public download and update-metadata repository for Math PDF Toolkit.**

> **Status: FRIENDS BETA CANDIDATE READY — general-public release and auto-update are not active.**

**The early beta is published:** [v0.8.4-beta.1 release](https://github.com/phch0809-create/math-pdf-toolkit-releases/releases/tag/v0.8.4-beta.1) with a verified ZIP attached. Read [Friends Preview Beta notes](BETA_TESTING.md) for instructions and known issues. It is **not** a stable general-public release.

This repository is a **distribution channel**, not the source-code repository. The existing Friends Preview beta is an invitation-only test package; its initial Windows WebView window has exhibited a startup hang. **Do not treat that beta as a verified public release.**

## Where downloads will appear

- [GitHub Releases](https://github.com/phch0809-create/math-pdf-toolkit-releases/releases) — available **after Windows validation**
- `releases/beta.json` — machine-readable **opt-in test** update metadata (active); `releases/latest.json` — production update metadata, **not created yet**

Until the first approved release, automatic update checks should report **"no official update available"**, not fabricate an update.

## Update policy

1. A trusted HTTPS manifest announces the version, asset URL, expected file size and SHA-256 checksum.
2. The application shows release notes; a person **chooses** whether to download and install.
3. The full download is verified before installation. A separate updater installs to a new version directory, without replacing a running EXE.
4. The new executable must pass post-install checks; failure retains the previous version and user settings.
5. Active PDF processing must finish or be safely stopped before installing.

**No silent installation, forced exit, or automatic PDF upload is enabled by this repository.** The opt-in [beta-channel manifest](releases/beta.json) now points to the published v0.8.4 test ZIP. The production `releases/latest.json` remains absent. Existing v0.8.4 EXEs have only a manual update-menu link and cannot self-update; the future v0.9.2+ updater engine must be installed once and configured to use the beta channel.

## Privacy and source separation

- PDF documents stay on the user's computer under the application's local-processing design.
- **Never commit** private development source, customer/student PDFs, user feedback, logs, credentials, access tokens or teaching materials here.
- Only independently verified distribution artifacts, their checksums, changelogs, and notices belong here.
- App feedback is not collected by GitHub automatically. Do not put sensitive material in public issues.

See [RELEASE_PROCESS.md](RELEASE_PROCESS.md), [SECURITY.md](SECURITY.md), and [docs/update-manifest.example.json](docs/update-manifest.example.json) (a non-live format example).

## License notices

Any distributed ZIP must include licenses and notices of third-party components, including bundled native libraries. The release process requires a manual licensing review before general publication.

© 2026 Math PDF Toolkit. No warranty for test versions.
