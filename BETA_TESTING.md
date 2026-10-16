# Math PDF Toolkit — Friends Preview Beta

> **Early-access testing only. Not a stable release.** Windows 10/11 x64 (EXE bundle; Python installation not required).

## Candidate package

- Release candidate: **v0.8.4-beta.1** (legacy processing engine v0.8 + manual-update menu v0.8.4)
- File: `MathPDFToolkit_Friends_Preview_v0.8.4_UpdateMenu_win64.zip`
- File size: **39,782,062 bytes**
- SHA-256: `6800d363dbe00a29f34dcf1c0c2bd2a534dad511c991c311bcc8212cb9a7b772`
- Existing owner-held [Google Drive copy](https://drive.google.com/file/d/1pNe1Bcyb9ygHDIS0l7ggtkEewzAa9Cz7/view) — **access is not currently verified for anonymous users**; testers may need explicit permission. The goal is a GitHub Pre-release asset available to invited beta testers.
- The code ZIPs labeled v0.9.x Developer Beta are **not** deployable Windows EXEs.

**Publication state:** source files, SHA and release notes are prepared. A GitHub *Pre-release asset* has not been uploaded/published yet. Do not claim the GitHub Release exists until a release URL and download are independently verified.

## Install and use

1. Download the Windows ZIP from a link supplied by the maintainer, and extract **all** files into a new local folder (for example `D:\MathPDFToolkitBeta`). Do not run from inside the ZIP or from an online-only Google Drive placeholder.
2. Double-click **`시작하기.cmd`** (top level). This opens the app using the **browser-safe local mode** with an EXE acting as a local service.
3. Use the **+ 파일 추가** button for large PDFs. When a PDF is *dragged into the browser*, the browser-security workaround can make a local copy, taking more time/storage.
4. Test a **non-sensitive throwaway PDF** first: (a) compression, (b) merging two PDFs, (c) splitting a few pages. Compare outputs with originals.
5. Use `피드백_작성하기.cmd` to write feedback. **Feedback is local only** unless the user independently sends it to the developer.
6. Close the toolkit from the application's **앱 종료** button.

## Known limitations and risk

- Early Windows WebView native UI had an **응답 없음 / Not responding** hang. Launch via `시작하기.cmd` browser-safe mode instead.
- The update button in this particular beta **only opens the manual download folder**. It does **not** check versions automatically, silently upgrade, install, or roll back.
- Current v0.9.1/0.9.2 source improvements (new settings dialog, speed-first compression, per-tab progress and new auto-update engine) are **not bundled in this beta**.
- Large PDFs may take considerable time and memory to compress, particularly when sourced from synced/network paths.
- As an unsigned experimental application it may display Windows warnings. **Do not instruct users to disable security protections**.
- The third-party license review, Windows PC acceptance, and updater installation/rollback verification are **not complete**.
- Preserve originals; try with copies and verify extracted PDF pages/quality before relying on results.

## Suggested bug report

Include:
- app version (v0.8.4 beta), Windows version, attempted operation and number/approximate size of files;
- expected result and actual result, reproduction steps, screenshot if possible;
- optional redacted error text or log excerpts.

**Do not upload or publicly post actual PDFs, student/customer records, credentials, or sensitive paths.** No automatic telemetry, online feedback delivery or document upload is enabled by this document.

## Beta release publication checklist

Maintainer only: visit [New release](https://github.com/phch0809-create/math-pdf-toolkit-releases/releases/new), set tag `v0.8.4-beta.1`, select **This is a pre-release**, attach the exact ZIP named above, use this note for release text, publish and **verify the public download and SHA-256**. Do **not** publish `releases/latest.json` for this beta; stable automatic update is still off.

Future stable releases must pass [RELEASE_PROCESS.md](RELEASE_PROCESS.md).
