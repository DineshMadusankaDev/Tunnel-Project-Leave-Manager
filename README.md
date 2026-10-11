# Tunnel Project Leave Manager (PWA)

A mobile-first, standalone HTML/CSS/JavaScript leave request manager for the Habarana–Palugaswewa Tunnel Project.

## Features
- Preloaded employee codes/names from the existing Mariner's Daily Manpower Report app (84 records).
- Record leave requests received by phone call, WhatsApp, SMS, in person, or other.
- Pending, approved, and rejected states; rejection reason capture.
- Monthly rule: 4 approved leave days per calendar month. Multi-day requests are counted across calendar months.
- Requests exceeding the monthly limit require a written reason and a supporting document to approve.
- Sick leave medical-document tracking.
- Employee monthly history, remaining allowance, and pending count.
- Local-only storage with JSON backup and restore.
- Optional document attachments stored locally in IndexedDB (max 5 MB per file).
- Installable PWA with offline app-shell caching.

## Deploy to GitHub Pages
1. Upload `index.html`, `manifest.webmanifest`, `sw.js`, and `icon.svg` to a GitHub repository or a dedicated folder in a Pages-enabled repository.
2. Enable GitHub Pages for the branch/folder containing these files.
3. Open the HTTPS Pages URL on Android Chrome.
4. Use Chrome menu → **Add to Home screen** / **Install app**.

## Important storage note
This app stores data in the browser on one device. It does not sync with another phone and does not automatically capture WhatsApp, SMS, or calls. Export a JSON backup regularly. Attachments and backups can contain sensitive medical information; keep them private. Browser storage can be cleared by the user or the operating system.

## Leave policy behavior
- Only approved requests count toward the 4-day monthly allowance.
- Pending requests are not counted until approved.
- Requests that cross a month boundary are counted per calendar month.
- Requests overlapping another pending/approved request for the same employee are blocked.
- Over-limit requests require a written reason and an actual supporting-document attachment before approval.
- Sick requests require an actual medical-report attachment before approval.

## Test checklist
- Add a request from each source type.
- Approve and reject a pending request; ensure rejected requests do not count against allowance.
- Approve four days, then test a fifth day with and without reason/document.
- Test a date range crossing two calendar months.
- Export backup, clear a test request, then restore backup.
- Attach a small PDF/image, export backup, and restore it on the same browser.