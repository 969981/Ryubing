# Ryubing upstream mirror & automatic builds

This repository tracks the upstream [Ryubing Forgejo](https://git.ryujinx.app/projects/Ryubing) project.

- **`main`**: GitHub Actions automation and documentation (this branch).
- **`upstream-master`**: unmodified upstream `master` branch, synchronized automatically.
- **Releases**: snapshot builds created from `upstream-master`, only when a source revision lacks a release.

**Primary upstream:** `https://git.ryujinx.app/projects/Ryubing.git`  
**Read-only fallback:** `https://git.aocro.com/mirrors/Ryubing.git` (used only if primary cannot be reached; it may lag).

The workflow checks for changes approximately every 10 minutes (GitHub-hosted schedules are best effort).
It attempts Windows x64, Linux x64 and macOS universal builds. Failed builds do not publish a release, and the next check can retry them.

To launch the workflow manually, visit **Actions → Sync Ryubing and Release → Run workflow**.
The GitHub Actions token needs **Contents: read and write** to push the mirror branch and publish Releases.

The builds are community snapshots, not official Ryubing releases. Official source remains the authority.
