# Developer-Verifiable Screen Contracts — G3

**Рівні:** UI = статичний стан; SIM = прототипна симуляція; IMPL = справжній вебзастосунок. Кожна дія має precondition, visible result та тест. Усі C-ID нижче — **контрактні ідентифікатори**, не твердження про фактичні layer names у Figma.

## S-01 — authentication boundary

Actor: unauthenticated. Purpose: вказати обмеження доступу BR-01/NFR-02. Visible: Mini Issue Tracker; Authentication entry — mechanism TBD. Inputs: немає. Controls: немає. Error: не вигадувати password/SSO. Prototype demo починається з S-02 як authenticated fixture. IMPL: actual login/session/ACL.

## S-02 — Issues List (A/B/C)

Actor: Member/Lead, authenticated fixture. Visible columns: `ID`, `Title`, `Status`, `Priority`, `Assignee` (для відсутнього — `Unassigned`). Long Title має повністю відкриватися в S-03. Default A: усі 8 issues. B: Important subset 001/002/003/007. C: 0 rows, `No issues yet`. `No important issues found` — інший empty state, коли є issues, але жоден не проходить фільтр.

| C-ID | Control | Visibility/condition | Action/result | Source/test |
|---|---|---|---|---|
| C-S02-01 | All Issues tab | authenticated | A; all issues | AC-02.1, T-08/09 |
| C-S02-02 | Important Issues tab | authenticated | B; `(High or Critical) and != Closed` | AC-08.1–4, T-08 |
| C-S02-03 | New Issue | authenticated | M-01-A overlay | AC-01.1, T-01/09 |
| C-S02-04 | Issue title/row | authenticated, row exists | S-03 same ID | AC-02.3, T-09 |

## M-01 — Create Issue overlay (A–G)

Actor: authenticated Member/Lead. Only user-entered fields: Title and Description. Visible labels `Title (required)`, `Description (required)`. No priority, assignee, status, attachment or category input. Demo field clicks substitute predefined fixture values; valid form success prepares ID, Open, Not Set, author, created_at. Missing Title: `Title is required`; missing Description: `Description is required`; if both empty, **both errors** visible.

| C-ID | Control | Condition/action | Expected | Source/test |
|---|---|---|---|---|
| C-M01-TITLE | Title input | click empty field (SIM) | prefilled demo Title; clear only its error | AC-01.1/2, T-01/02 |
| C-M01-DESC | Description textarea | click empty field (SIM) | prefilled demo Description; clear only its error | AC-01.1/3, T-01/02 |
| C-M01-CREATE | Create | both nonempty → prepared S-03-NEW; otherwise validation | no issue on invalid | AC-01.2–5, T-01/02 |
| C-M01-CANCEL | Cancel / X | any state | Close overlay, caller preserved | D-07, T-09 |

UI/SIM cannot prove unique ID generation, current-user author, persistence, real keyboard validation. Those are IMPL.

## S-03 — Issue Details

Actor: authenticated. Visible data: `ID`, `Title`, `Description`, `Status`, `Priority`, `Assignee`, `Author`, `Created at`. Missing assignee: `Unassigned`; missing priority: `Not Set`. Comments: each saved entry has text, author, creation timestamp.

| C-ID | Control | Who/when | Action/result | Source/test |
|---|---|---|---|---|
| C-S03-01 | Back to Issues | all authenticated | Return to calling list/tab | D-07, T-09 |
| C-S03-02 | Assignee selector + Apply | Team Lead only | select exactly one existing team member; current assignee visible | US-03, T-03 |
| C-S03-03 | Priority selector + Apply | Team Lead only | select Low/Normal/High/Critical; Not Set display-only | AC-04.1/2, T-04 |
| C-S03-04 | Status selector + Apply | current assignee AND legal outgoing edge | change status to allowed next | AC-07.2–5, BR-08.1, T-05/06 |
| C-S03-05 | Comment textarea | any authenticated | nonempty text required | AC-06.1, T-07 |
| C-S03-06 | Add Comment | any authenticated, nonempty text | success: text/author/time; failed save: error, no saved entry | AC-06.2–5, T-07 |

**Important:** `Closed` has no status transitions; this does **not** automatically disable comments or priority changes. Non-assignee Lead has no status permission. Member assignee may change status, but not assignee/priority.

## Permission matrix (SOURCE/DERIVED)

| Actor / issue relation | View | Create | Comment | Assign | Priority | Status* |
|---|---|---|---|---|---|---|
| Team Member, non-assignee | Yes | Yes | Yes | No | No | No |
| Team Member, current assignee | Yes | Yes | Yes | No | No | Yes |
| Team Lead, non-assignee | Yes | Yes | Yes | Yes | Yes | No |
| Team Lead, current assignee | Yes | Yes | Yes | Yes | Yes | Yes |

*Yes тільки коли поточний status має дозволений вихідний перехід. Unassigned issue не має current assignee; ніхто не може змінювати status до призначення.

## Full status transition matrix

`✓` означає зміну значення; `—` — заборонено. Same-state selection не є переходом.

| From \ To | Open | In Progress | Resolved | Closed |
|---|---|---|---|---|
| Open | same | ✓ | — | — |
| In Progress | — | same | ✓ | — |
| Resolved | — | ✓ | same | ✓ |
| Closed | — | — | — | same |

## Priority and Important

Selectable priority: **Low, Normal, High, Critical**. `Not Set` — початкове відсутнє значення, а не п'ятий рівень чи reset. Important predicate: `(priority ∈ {High,Critical}) AND (status != Closed)`. Thus `Resolved + High` included; `Closed + Critical` excluded; `Not Set` excluded. Fixture: All 8 rows, Important 4 (001, 002, 003, 007).

## Comment state contract

- Empty comment → inline `Comment is required`; no saved comment.
- Successful simulated save → comment text + author + created_at in list.
- Failed save → `Could not save comment. Please try again.`; no new saved comment, input remains for retry.

## Coverage and limits

Each source AC is linked in `../01_requirements/Traceability_33AC.csv`. T-01–T-10 are defined in `../04_quality_assurance/Prototype_Test_Record.md`. Static disabled state is not backend authorization; displayed comment is not persistence; performance/HTTPS/backup/authentication require implementation tests.
