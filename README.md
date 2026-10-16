# Math PDF Toolkit — Official Releases

**Public download and update-metadata repository for Math PDF Toolkit.**

> **Status: PRE-RELEASE SETUP — no verified general-public release is available yet.**

This repository is a **distribution channel**, not the source-code repository. The existing Friends Preview beta is an invitation-only test package; its initial Windows WebView window has exhibited a startup hang. **Do not treat that beta as a verified public release.**

## Where downloads will appear

- [GitHub Releases](https://github.com/phch0809-create/math-pdf-toolkit-releases/releases) — available **after Windows validation**
- `releases/latest.json` — machine-readable update metadata, **created only after a validated build is published**

Until the first approved release, automatic update checks should report **"no official update available"**, not fabricate an update.

## Update policy

1. A trusted HTTPS manifest announces the version, asset URL, expected file size and SHA-256 checksum.
2. The application shows release notes; a person **chooses** whether to download and install.
3. The full download is verified before installation. A separate updater installs to a new version directory, without replacing a running EXE.
4. The new executable must pass post-install checks; failure retains the previous version and user settings.
5. Active PDF processing must finish or be safely stopped before installing.

**No silent installation, forced exit, automatic PDF upload, or background monitoring is enabled by this repository.** This repository currently contains **no approved EXE or active update manifest**.

## Privacy and source separation

- PDF documents stay on the user's computer under the application's local-processing design.
- **Never commit** private development source, customer/student PDFs, user feedback, logs, credentials, access tokens or teaching materials here.
- Only independently verified distribution artifacts, their checksums, changelogs, and notices belong here.
- App feedback is not collected by GitHub automatically. Do not put sensitive material in public issues.

See [RELEASE_PROCESS.md](RELEASE_PROCESS.md), [SECURITY.md](SECURITY.md), and [docs/update-manifest.example.json](docs/update-manifest.example.json) (a non-live format example).

## License notices

Any distributed ZIP must include licenses and notices of third-party components, including bundled native libraries. The release process requires a manual licensing review before general publication.

© 2026 Math PDF Toolkit. No warranty for test versions.
