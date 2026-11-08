# UX/UI Design Input Pack — v1.0 (source-derived)

## Джерело
`../00_sources/SD_Spec.docx` §§0–9. Джерело має пріоритет над похідними документами. Усі 33 критерії наведено у `Traceability_33AC.csv`; для US-03 вихідні критерії **не мають власних номерів**.

## Продукт та ролі
Mini Issue Tracker — внутрішній вебзастосунок для реєстрації, відстеження й координації проблем невеликої команди. Основні користувачі: Team Member, Team Lead; три попередньо задані користувачі (два Member, один Lead), BR-01. Assignee — відношення до конкретної заявки, не роль.

## Остаточний Release Scope
Included: US-01–US-08 (§8). Deferred: US-09 attachments. Future: SR-10 автоматична категоризація, SR-11 рекомендація priority. Out of scope: customer portal, billing, source-code hosting, CI/CD, time tracking, full project management, mobile app; інтеграції із зовнішніми трекерами (KC-05).

## Бізнес-правила SOURCE
- BR-01/02: лише автентифіковані члени команди; кожен може створювати issue.
- BR-03/04: новий issue = Open, priority відсутній (`Not Set`).
- BR-05/06: встановлені значення priority Low/Normal/High/Critical; змінює лише Team Lead.
- US-03, AC п.1–4: один assignee, член команди; призначає лише Team Lead; assignee відображено.
- BR-07/08/08.1 + AC-07.4: статуси Open, In Progress, Resolved, Closed; змінює тільки поточний assignee; дозволені Open→In Progress, In Progress→Resolved, Resolved→Closed, Resolved→In Progress. Closed без вихідних переходів.
- BR-09/09.1 + AC-08.1–4: Important = priority ∈ {High,Critical} AND status != Closed; Resolved не Closed.
- BR-10/11: delete і користувацька історія змін відсутні.
- US-06: comment текст, author, time; порожній і невдалий save не створюють запису.

## NFR і межі дизайну
NFR-01 response < 1s; NFR-02 authentication; NFR-03 HTTPS; NFR-04 backup усіх даних (актуальна §8). Макет не доводить latency, серверну автентифікацію, HTTPS, backup, persistence чи авторизацію.

## SOURCE CHECK
US-01 5; US-02 5; US-03 4 ненумеровані; US-04 2; US-05 3; US-06 5; US-07 5; US-08 4 = **33**. Gherkin не рахується вдруге. Повний перелік із source IDs у CSV.

## UNRESOLVED / UX proposals
Q-01 спосіб authentication не визначено: не малювати парольну форму. Q-02 default assignee після Create у S1 не встановлено: `unassigned` є **PROPOSED D-04**, потребує погодження. Q-03 перепризначення Team Lead прямо не деталізоване: **PROPOSED D-04**. Q-04 Apply / disabled / return-to-tab — UX choices, не AC. Q-05 технічне представлення Not Set (null/enum) не визначено.


**Уточнення для актуального пакета:** реальний Figma URL див. у `../03_figma/Figma_Link_and_Version.md`; виконання інтерактивних сценаріїв за словами студента не є незалежним тестом. Повний Source Check — `Source_Check.md`.


## Реєстр включених 33 Acceptance Criteria (зміст джерела)

| Story | Source criterion | Очікувана поведінка |
|---|---|---|
| US-01 | AC-01.1 | Title і Description |
| US-01 | AC-01.2 | Title required |
| US-01 | AC-01.3 | Description required |
| US-01 | AC-01.4 | ID, Open, created_at, author |
| US-01 | AC-01.5 | Priority absent / Not Set |
| US-02 | AC-02.1 | Список для авторизованого користувача |
| US-02 | AC-02.2 | ID Title Status Priority Assignee |
| US-02 | AC-02.3 | Відкриття деталей |
| US-02 | AC-02.4 | ID Title Description Status Priority Assignee Author Created at |
| US-02 | AC-02.5 | Empty list |
| US-03 | US-03, AC, пункт 1 | Один assignee |
| US-03 | US-03, AC, пункт 2 | Assignee — член команди |
| US-03 | US-03, AC, пункт 3 | Лише Team Lead призначає |
| US-03 | US-03, AC, пункт 4 | Поточний assignee відображено |
| US-04 | AC-04.1 | Low Normal High Critical |
| US-04 | AC-04.2 | Лише Team Lead встановлює priority |
| US-05 | AC-05.1 | Поточний status issue |
| US-05 | AC-05.2 | Status на сторінці деталей |
| US-05 | AC-05.3 | Status у списку |
| US-06 | AC-06.1 | Comment не порожній |
| US-06 | AC-06.2 | Збережений comment видно |
| US-06 | AC-06.3 | Author comment |
| US-06 | AC-06.4 | Дата/час comment |
| US-06 | AC-06.5 | Save failure: error, немає comment |
| US-07 | AC-07.1 | Новий issue Open |
| US-07 | AC-07.2 | 4 статуси |
| US-07 | AC-07.3 | Збереження status і повторний перегляд |
| US-07 | AC-07.4 | Non-assignee не змінює status |
| US-07 | AC-07.5 | Інші status values заборонено |
| US-08 | AC-08.1 | High і не Closed включено |
| US-08 | AC-08.2 | Critical і не Closed включено |
| US-08 | AC-08.3 | Low/Normal виключено |
| US-08 | AC-08.4 | Closed виключено |

> Для US-03 `п.1–4` — адресація чотирьох ненумерованих пунктів вихідної специфікації, а не нові source IDs.
