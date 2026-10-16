# Security and privacy

This public repository is used for Math PDF Toolkit distribution metadata and verified downloadable Windows packages. No general-public release is live yet.

## Reporting security issues

**Do not post exploits, credentials, private PDFs, student data, or private diagnostics in public GitHub issues.**

Use GitHub's **Report a vulnerability / private security advisory** feature if available for this repository, or contact the maintainer via an already established private communication channel. Do not rely on an invented support email address. If the private advisory feature is unavailable, request a private contact method without including sensitive details.

Include a reproducible minimal example with synthetic PDFs when possible, software version, Windows version, the expected and actual result, and whether a release or updater is affected.

## Distribution security

- Do not activate update metadata for a ZIP that did not pass real Windows startup and installation acceptance.
- Validate HTTPS, release asset hostname, exact ZIP size, SHA-256, expected archive structure and installed EXE's own diagnostics before switch-over.
- Preserve existing installation and original PDF files on update or installation failure.
- An update manifest is an instruction to install software; restrict edits to trusted maintainers, preferably protect the `main` branch and use signed releases/manifests for broad distribution.
- No PDF documents, feedback, telemetry or background scanning should be uploaded just because update checking is enabled.
- If a user has already received an unverified beta, treat it as a separate preview and avoid forced auto-upgrades.

## Support status

The earlier Windows WebView UI hang was reported during preview tests. Therefore this repository does not yet distribute a generally validated production release.
