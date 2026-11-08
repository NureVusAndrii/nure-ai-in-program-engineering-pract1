# Figma Implementation Brief — Mini Issue Tracker (editable low-fidelity UX/UI)

## Purpose and release scope

Build and maintain an editable grayscale desktop UX/UI prototype for a small internal issue tracker. Include exactly US-01 through US-08: create, view, assign, set priority, track status, comment, update status, view important non-closed issues. Defer US-09 attachments; leave SR-10 and SR-11 AI recommendations for future releases. Preserve existing working Figma navigation; never replace it with a landing page or rasterized mockup.

## Design constraints

Native editable Figma layers; clear frame IDs; Auto Layout and local reusable components where practical; annotations outside product frames. Preserve original styling, controls, and prototype connections. No real backend, no invented login method, no separate assignment/priority/status/comments product pages. Demo uses three fictional users: Member A, Member B (Team Members), Lead (Team Lead).

## Canonical product surfaces and exact data

- **S-01** Authentication boundary: "Authentication entry — mechanism TBD"; no login inputs.
- **S-02-A** All Issues: table columns ID, Title, Status, Priority, Assignee; All/Important tabs, New Issue, clickable issue title; all eight fixture rows.
- **S-02-B** Important Issues: same table and data, only ISS-001, ISS-002, ISS-003, ISS-007.
- **S-02-C** No registered issues: "No issues yet" and New Issue.
- **M-01-A–G** centered overlay over current list: Title (required), Description (required), Cancel, Create, X; 7 states for blank/filled/error combinations.
- **S-03** Issue Details: ID, Title, Description, Status, Priority, Assignee, Author, Created at; comment list and input; Back; permitted controls for assignment, priority and status.
- **S-03-NEW** prepared created issue details with Open, Not Set, author and timestamp.
- **REF-01..06** service-only reference examples: role permissions, status transitions, Important predicate, comment error/success, empty/initial states, component states. Not part of main navigation.

## Fixture data

| ID | Title | Status | Priority | Assignee |
|---|---|---|---|---|
| ISS-001 | Login fails | Open | Critical | Member A |
| ISS-002 | Dashboard loading error | In Progress | High | Member B |
| ISS-003 | Export button not responding | Resolved | High | Member A |
| ISS-004 | Old notification issue | Closed | Critical | Member B |
| ISS-005 | Profile image misaligned | Open | Normal | Unassigned |
| ISS-006 | Search results inconsistent | Open | Not Set | Unassigned |
| ISS-007 | API timeout | Resolved | Critical | Lead |
| ISS-008 | Tooltip overlaps button | In Progress | Low | Member A |

Important predicate: `(priority = High OR priority = Critical) AND status != Closed`. Resolved is not Closed; Not Set is absence, not a selectable priority.

## Permissions

All authenticated users: view/create/comment. Only Lead: assign one team member and set/change priority. Only **current assignee**: change status (Lead non-assignee cannot). Status values Open, In Progress, Resolved, Closed. Allowed edges only Open→In Progress; In Progress→Resolved; Resolved→In Progress; Resolved→Closed. Closed has no outgoing edge. Do not disable unrelated comment or priority actions solely because status is Closed.

## M-01 overlay and validation

Use real Figma `Open overlay` from both S-02-A and S-02-B, `Swap overlay` for state changes, `Close overlay` for Cancel/X. Keep calling list visible and preserve its tab. States: A both empty no errors; B Title filled; C Description filled; D both filled; E both empty both required errors; F Title filled Description error; G Description filled Title error. Clicking an empty field simulates prefilled text; users can fill either first. `Create` from A→E, B→F, C→G; from D→S-03-NEW; no invalid state may lead to success. The form accepts only Title and Description; success prepares unique-looking ID, Open, Not Set, author, timestamp; do not claim actual persistence.

## Comments and empty/error examples

Empty comment: `Comment is required`. Saved example: text, author and timestamp. Failed save: error, no new saved entry, text retained. Show zero-registered-issues separately from zero-important-issues. Show non-assignee disabled status and Lead-only assignment/priority. Include all four status edges and Closed terminal state.

## Navigation intent

All↔Important; New Issue→Open overlay; Cancel/X→Close overlay; field click→Swap overlay; valid Create→prepared S-03-NEW; issue row→matching S-03; Back→calling list state. Reference states outside main flow; forbidden actions have no success hotspots. Prototype transitions are demonstrations, not working backend.

## Exclusions

No delete, attachments, change history, AI recommendations, invented login, analytics, bulk actions, Jira/GitHub integrations, extra roles, extra status/priority values, unrelated product screens, or source-code hosting.

## Acceptance checklist

- [ ] 8 stories and 33 AC mapped to screen/state and test
- [ ] All 8 rows and correct Important 4-row subset
- [ ] Both Title and Description required independently
- [ ] Current list visible behind M-01 overlays
- [ ] Correct default status/priority and issue metadata
- [ ] All four permission contexts demonstrated
- [ ] Exactly four allowed status edges; Closed terminal
- [ ] Comments: empty/success/failed-save states
- [ ] Empty All vs empty Important distinguished
- [ ] All frames editable and names readable
- [ ] Main prototype links run in Present; test record written by operator
- [ ] No out-of-scope controls or fake implementation claims

**Figma source:** https://www.figma.com/design/BlBanabnVhdnqtKHHZa8qg/Untitled?node-id=0-1. Human review and actual Present run are required to certify completion.
