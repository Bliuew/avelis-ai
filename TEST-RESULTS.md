# Test results — 17 November 2026

Base main: `f097148f462f3d9cec67efd33765d7b1286d0b56`. Remote main was checked again before handoff and remained at this commit.

## Executed results

- `npm test`: **18 passed, 0 failed** — 14 domain checks and 4 preservation checks.
- `node ecosystem/tests/dom-qa.mjs` with jsdom installed outside the project: **21 passed, 0 failed**.
- `node --check ecosystem/app.js`: passed.
- Managed browser preview startup: **failed**, infrastructure error `listen EPERM 127.0.0.1:4173`. Real browser visual, accessibility and responsive layout checks remain **unverified**. DOM simulation is not a substitute for these checks.
- Remote feature branch write dry-run: **failed**, GitHub HTTP 403 permission denied. No remote branch, pull request or deployment was created. A local feature-branch commit, review patch and complete source archive are provided for manual submission.

## Mandatory acceptance mapping

| Acceptance item | Result and evidence |
| --- | --- |
| Original website sections remain functional | Original section/control IDs preserved; all original inline scripts initialize and Command Centre panels render in DOM. Full original interaction regression is not exhaustively browser-tested. |
| Advisor accepts CSV and calculates accurately | Passed: the actual file-input change handler reads the supplied `Transaction,Status,Amount CAD` / `DEMO-1,Approved,500.00` dataset; parser/statistics verify CAD 500; original chart calculation path runs. |
| Contacts create/edit | Passed through DOM forms and domain tests; archive/restore and prospect deduplication tested. |
| Opportunity forecasts update | Passed: 50,000 cents × 60% = 30,000 cents; updates and Won exclusion recalculate. |
| Simulated calls support participants | Passed: Connecting, Active, Hold, mute, participant addition/conference, transfer and Completed states; labelled transcript generated. |
| Messages post and convert to tasks | Passed: message posting, thread replies, group channel creation, stable message-task reference and escaped HTML rendering. |
| Workflow execution states | Passed: tasks, conditional cancellation, future scheduling guard, pause/resume, manager approval gating and completion. |
| Invoices recalculate | Passed: quantity and price changes update preview and saved integer-cent lines; invalid fractional cents rejected. |
| Payments update invoices/transactions | Passed through DOM form and domain assertions. |
| Duplicate transactions prevented | Passed: repeated key returns existing transaction; second key cannot pay an already-paid invoice. |
| Refund calculations | Passed: paid balance, spend, points, fee and settlement reverse; second refund rejected. |
| Sharim disconnect does not break Amā | Passed: CRM and opportunity operations continue after disconnect; payment actions fail explicitly. |
| Card assembly/detachment | State controls passed through DOM. **Artwork acceptance incomplete**: public-safe original module artwork is not available separately from the confidential/specification-bearing sheet. |
| Advisor generated dataset | Passed: original Advisor import uses actual transaction values; approved CAD 500 / fee CAD 12.80 / net CAD 487.20, and zero current receipts after refund. |
| Reports downloadable | Passed: original CSV/HTML report handlers and six new invoice, receipt, transaction, insight, prospect and overall report handlers initiate named downloads. Actual filesystem saving in a real browser is unverified. |
| Persistence/reset | Passed: reload from storage, rollback on failed mutation, storage quota warning, guided progress and explicit reset. Original namespace retained. |
| Mobile/desktop layouts | Responsive CSS implemented, but **unverified in an actual browser** because preview failed. |
| Original logos/branding unchanged | Passed: original Avelis and Ditheka image tags remain byte-identical; original archives remain byte-identical. Supplied Amā/Sharim JPEG logos copied directly; no redrawing. |
| No decorative buttons | All newly introduced controls are wired to routes, forms or handlers. Main journey and exports exercised in DOM; exhaustive real-browser button and keyboard coverage remains unverified. |

## Important prototype limitations

- Single-browser local persistence; no real multi-user delivery or multi-tab conflict resolution. Persistence may fail when storage is unavailable; in-memory work can still be exported.
- Voice controls simulate states; transcripts are fictional fixed samples and do not transcribe a call.
- Coaching uses configurable keyword/punctuation evidence, not model evaluation or inferred personality/emotion.
- Intelligence supports a small documented set of deterministic English/French keyword queries. The language selector is an interface choice, not a translation service. Document inspection is text-only word/keyword analysis.
- Attachment handling retains filename/size metadata; files are not stored, transmitted or scanned.
- Workflow emails and calls create local tasks; no outreach is actually sent. Scheduled execution advances only when the investor clicks execute after its configured date; no background scheduler exists.
- Commerce supports full-invoice payment/refund only. No partial settlement, tax engine, exchange rates, accounting compliance or real payment accounts are implemented. Fee settings apply prospectively.
- Card Studio uses virtual state controls without reproducing the original module artwork. The supplied full concept sheet was deliberately excluded from public source because it contains specifications and unsupported financial infrastructure claims. Hardware compatibility/certification remains unvalidated.
- Advisor's connected dataset describes current approved receipts; it is not a double-entry ledger or historical cash-flow journal.
- Event import into Avelis occurs when opening its page, with the original bounded local audit history. No server audit, live event stream or real security authorization is claimed.
- Existing private reviewer/pilot access remains disabled until secure backend configuration; no confidential reviewer storage or fake login was added.

## Required manual review before merge

Serve the root over HTTP and check desktop (1440px), tablet (768px) and mobile (390px) layouts, all themes, horizontal table navigation, keyboard focus order, screen-reader labels, actual file downloads, attachment labels, CSV import confirmation, negative inputs and every secondary control. Complete the Card Studio artwork item using founder-approved sanitized assets. Review the pull request before publishing main.
