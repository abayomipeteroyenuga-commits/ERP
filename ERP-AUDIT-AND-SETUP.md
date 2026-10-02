# Ethan Digital Academy ERP — Version 3

## What changed
- Payments link to a specific invoice. A receipt can no longer be counted against multiple invoices for the same learner/course. Verified receipts without an invoice remain unassigned; edit them to reconcile.
- Invoice status shows Paid, Part Paid, Unpaid or Overdue; printouts include verified receipts and outstanding balance. Overpayment against a linked invoice is blocked.
- Accepted applicants convert to learner records once, with duplicate-email protection. Conversion does not provision a login.
- Learner summaries show receipts, invoice balances, course allocations, attendance counts and published results.
- Mark a whole allocated class present, absent, late or excused. Repeated saves update the existing learner/course/date record.
- Class scheduling checks overlapping instructor or venue bookings.
- Deletion moves records to a recycle bin. Restore is available. Linked learner/course history and verified receipts are protected from deletion.
- Course Allocations allows active, paused, completed and cancelled status.
- Search matches linked learner/course names. Lists show 20 records per page.
- Dashboard shows active learners, verified receipts, outstanding balances, applications, today's classes and overdue invoices.
- Reports identify verified receipts awaiting invoice assignment.

## Existing functionality
Learner/course/staff records, admissions, assignments, assessment planning, results, certificates, announcements, attendance, timetable, payments, invoices, expenses, equipment, CSV exports, local activity history and JSON backup/restore.

## Run and upload
Extract this ZIP. Upload its contents to the GitHub repository root, with index.html at the root. This is a static site; no build command is required. For Vercel use Framework Preset: Other, no build command, Output Directory: .

## Data migration and backup
The same browser storage key is retained from v2. Export a JSON backup before replacing an existing deployment. Existing receipts are not automatically assigned to invoices. In Payment Records, edit each receipt and select the matching invoice. Legacy Confirmed statuses should be reviewed and changed to Verified by an administrator where appropriate. Invoices include only payments explicitly marked Verified and linked to that invoice.

Records belong to the browser and the website origin. A local file, GitHub Pages, Vercel and the private preview each have separate data stores. To transfer records between them, export then restore a backup. Clearing browser data removes local records, including the recycle bin.

## Scope and limitations
This build opens as an administration preview without academy sign-in. Do not expose this preview as a production multi-user system. New modules do not sync with Supabase merely by entering credentials. Shared records, secure authentication/roles and server authorization need backend integration.

Staff directory entries are personnel records, not accounts. Admissions conversion creates a local learner record. Email sending, payment gateways, automatic reconciliation, online quiz delivery/marking and public certificate verification are not connected. Certificates require a published score of at least 60%; completion eligibility still needs manual review. The activity history is local and not tamper-proof. Cash reports are operational summaries, not statutory accounts.

A verified payment can allocate a course even when the fee is partially paid; the learner is marked Part Paid. Admin decides whether to allocate access and can pause it under Course Allocations. Editing a receipt does not automatically revoke existing course access.

## Validation
Syntax checks passed. Automated JavaScript tests covered module rendering in a test harness, per-invoice reconciliation, overpayment rejection, repeated allocation, bulk-attendance updates, linked-record protection, application conversion, recycle/restore, timetable overlap, score bounds, certificate prerequisites, dashboard/report output and learner result filtering. A full visual browser/end-to-end check was not available in this environment.
