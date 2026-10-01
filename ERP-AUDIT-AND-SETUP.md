# Ethan Digital Academy ERP — workflow update

This build is a single-browser workspace. It does not provide shared server records or secure multi-user access. All new modules operate on browser-local records, even if Supabase credentials are later supplied. Backend adapters and database authorization must be implemented and tested before live multi-user use.

## Working workflows added
- Learner creation, editing, search, CSV export and duplicate-email validation.
- Course creation, editing, fees, publication state and duplicate-course-code validation.
- Staff personnel directory (records, not login accounts).
- Admissions tracking with application status.
- Assignments and assessment scheduling registers.
- Attendance recording with duplicate checks per learner/course/date.
- Class scheduling with start/end-time validation.
- Results with score validation and publication status.
- Certificate records, requiring a published result of at least 60%; printable output. Completion must also be checked manually. Certificate verification is local only.
- Pending/verified/rejected payment records. Verified receipts can allocate a course without creating a second payment.
- Invoices with balances computed from verified learner/course payments. Multiple invoices for the same learner/course are not independently reconciled; use one invoice per learner/course.
- Printable payment, invoice and certificate records using the browser Print / Save PDF function.
- Announcements, operational totals, CSV exports and local activity history.
- Expense and equipment registers, JSON backup and validated restore.
- Saved academy settings are loaded back into the settings form.

## Not connected / not enabled
- Shared database synchronization and secure account authentication/role enforcement.
- Staff login provisioning, password reset and automatic emails.
- Payment gateway charging, automatic bank reconciliation and independent invoice allocation.
- Payroll, statutory accounting, tax filing and audited financial statements.
- Online quiz delivery/submission and automatic marking. Assessment register and manual results are available.
- Public certificate verification and automated course-completion eligibility.
- The local activity log can be modified by the device user; it is not a tamper-proof audit trail.

## Installation
Extract the ZIP and upload its contents to the repository root. Keep index.html at the root. Serve as a static site. No build command is required. The preview opens directly without academy sign-in. Export backups regularly because clearing browser storage removes local records.

## Validation
JavaScript syntax checks and workflow tests passed for record creation/editing, duplicate attendance prevention, score bounds, certificate prerequisites, invoice balance arithmetic, activity logging and learner result filtering. Browser visual/end-to-end verification was not completed because the local browser runtime was unavailable and the hosted preview requires the owner's ChatGPT login.
