# Storage integrity checks

Run from the repository root with Node.js 22 or later:

```sh
npm install --no-save --package-lock=false fake-indexeddb
node tests/storage-integrity.cjs
```

These tests execute the actual app storage, backup, and restore functions with fake-indexeddb and mocked dialogs/downloads. They check normal save/reopen and full backup restore, late transaction aborts, failed-save warnings and retry, atomic restore rollback, missing backup media, incomplete restores, and invalid base64 media.

All eight checks passed during development. The inline app JavaScript also passed syntax checking.

This is simulated database testing, not browser rendering, real downloads, operating-system durability, or iPhone testing. A local Chromium installation attempt failed, so no browser test result is claimed. Next: on an iPhone, use a disposable project with a real photo and recording, save and close/reopen the app, export a backup, restore it as a separate project, and verify photo display, audio playback, notes, parts, tasks, and reassembly progress. Keep existing clock records and previous backups intact.
