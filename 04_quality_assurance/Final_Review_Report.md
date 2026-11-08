# G6 — фінальний аудит доступних доказів (08.11.2026)

## Матеріали і метод

Прочитано `SD_Spec.docx`, методичні вказівки, попередній документальний пакет та два архіви (наш попередній і сторонній приклад **лише для оцінки рівня оформлення**). Актуальний Figma URL: https://www.figma.com/design/BlBanabnVhdnqtKHHZa8qg/Untitled?node-id=0-1. Прямий доступ до поточного canvas і Present недоступний, тому **жоден поточний UI-state не оголошено PASS лише за текстом brief**. Є раніше надані скриншоти частини фреймів і повідомлення студента про завершені переходи; це часткові/непрямі докази, не повна перевірка поточної версії.

## Видимість доказів

- Відомі зі старіших скриншотів: S-02-A/B, M-01-A..G, частина S-03; вони не підтверджують поточну версію.
- Повідомлено студентом: усі переходи у поточному прототипі працюють.
- **Не перевірено незалежно:** читабельність усіх актуальних REF states, native editability, поточні зв'язки, всі 4 status transitions, permission restrictions, comment error/success, empty states.

## Частина A — coverage усіх 33 AC

Нижче `DOCUMENT MAPPED` означає лише наявність контракту/тесту. `NOT VERIFIABLE` не означає, що вимога порушена; означає, що немає перевіреного фактичного доказу для актуального Figma.

| Source | Expected | Screen/State | Observed evidence | Result | Remaining test |
|---|---|---|---|---|---|
| AC-01.1 | Title і Description | M-01-A..G / S-03-NEW | DOCUMENT MAPPED | NOT VERIFIABLE (current Figma) | T-01/T-02 |
| AC-01.2 | Title required | M-01-A..G / S-03-NEW | DOCUMENT MAPPED | NOT VERIFIABLE (current Figma) | T-01/T-02 |
| AC-01.3 | Description required | M-01-A..G / S-03-NEW | DOCUMENT MAPPED | NOT VERIFIABLE (current Figma) | T-01/T-02 |
| AC-01.4 | ID, Open, created_at, author | M-01-A..G / S-03-NEW | DOCUMENT MAPPED | NOT VERIFIABLE (current Figma) | T-01/T-02 |
| AC-01.5 | Priority absent / Not Set | M-01-A..G / S-03-NEW | DOCUMENT MAPPED | NOT VERIFIABLE (current Figma) | T-01/T-02 |
| AC-02.1 | Список для авторизованого користувача | S-02/S-03 | DOCUMENT MAPPED | NOT VERIFIABLE (current Figma) | T-09 |
| AC-02.2 | ID Title Status Priority Assignee | S-02/S-03 | DOCUMENT MAPPED | NOT VERIFIABLE (current Figma) | T-09 |
| AC-02.3 | Відкриття деталей | S-02/S-03 | DOCUMENT MAPPED | NOT VERIFIABLE (current Figma) | T-09 |
| AC-02.4 | ID Title Description Status Priority Assignee Author Created at | S-02/S-03 | DOCUMENT MAPPED | NOT VERIFIABLE (current Figma) | T-09 |
| AC-02.5 | Empty list | S-02/S-03 | DOCUMENT MAPPED | NOT VERIFIABLE (current Figma) | T-09 |
| US-03, AC, пункт 1 | Один assignee | S-03 / REF-01 | DOCUMENT MAPPED | NOT VERIFIABLE (current Figma) | T-03 |
| US-03, AC, пункт 2 | Assignee — член команди | S-03 / REF-01 | DOCUMENT MAPPED | NOT VERIFIABLE (current Figma) | T-03 |
| US-03, AC, пункт 3 | Лише Team Lead призначає | S-03 / REF-01 | DOCUMENT MAPPED | NOT VERIFIABLE (current Figma) | T-03 |
| US-03, AC, пункт 4 | Поточний assignee відображено | S-03 / REF-01 | DOCUMENT MAPPED | NOT VERIFIABLE (current Figma) | T-03 |
| AC-04.1 | Low Normal High Critical | S-03/REF-01 | DOCUMENT MAPPED | NOT VERIFIABLE (current Figma) | T-04 |
| AC-04.2 | Лише Team Lead встановлює priority | S-03/REF-01 | DOCUMENT MAPPED | NOT VERIFIABLE (current Figma) | T-04 |
| AC-05.1 | Поточний status issue | S-02/S-03 | DOCUMENT MAPPED | NOT VERIFIABLE (current Figma) | T-05 |
| AC-05.2 | Status на сторінці деталей | S-02/S-03 | DOCUMENT MAPPED | NOT VERIFIABLE (current Figma) | T-05 |
| AC-05.3 | Status у списку | S-02/S-03 | DOCUMENT MAPPED | NOT VERIFIABLE (current Figma) | T-05 |
| AC-06.1 | Comment не порожній | S-03 / REF-04 | DOCUMENT MAPPED | NOT VERIFIABLE (current Figma) | T-07 |
| AC-06.2 | Збережений comment видно | S-03 / REF-04 | DOCUMENT MAPPED | NOT VERIFIABLE (current Figma) | T-07 |
| AC-06.3 | Author comment | S-03 / REF-04 | DOCUMENT MAPPED | NOT VERIFIABLE (current Figma) | T-07 |
| AC-06.4 | Дата/час comment | S-03 / REF-04 | DOCUMENT MAPPED | NOT VERIFIABLE (current Figma) | T-07 |
| AC-06.5 | Save failure: error, немає comment | S-03 / REF-04 | DOCUMENT MAPPED | NOT VERIFIABLE (current Figma) | T-07 |
| AC-07.1 | Новий issue Open | S-03 / REF-01 / REF-02 | DOCUMENT MAPPED | NOT VERIFIABLE (current Figma) | T-05/T-06 |
| AC-07.2 | 4 статуси | S-03 / REF-01 / REF-02 | DOCUMENT MAPPED | NOT VERIFIABLE (current Figma) | T-05/T-06 |
| AC-07.3 | Збереження status і повторний перегляд | S-03 / REF-01 / REF-02 | DOCUMENT MAPPED | NOT VERIFIABLE (current Figma) | T-05/T-06 |
| AC-07.4 | Non-assignee не змінює status | S-03 / REF-01 / REF-02 | DOCUMENT MAPPED | NOT VERIFIABLE (current Figma) | T-05/T-06 |
| AC-07.5 | Інші status values заборонено | S-03 / REF-01 / REF-02 | DOCUMENT MAPPED | NOT VERIFIABLE (current Figma) | T-05/T-06 |
| AC-08.1 | High і не Closed включено | S-02-A / S-02-B / REF-03 | DOCUMENT MAPPED | NOT VERIFIABLE (current Figma) | T-08 |
| AC-08.2 | Critical і не Closed включено | S-02-A / S-02-B / REF-03 | DOCUMENT MAPPED | NOT VERIFIABLE (current Figma) | T-08 |
| AC-08.3 | Low/Normal виключено | S-02-A / S-02-B / REF-03 | DOCUMENT MAPPED | NOT VERIFIABLE (current Figma) | T-08 |
| AC-08.4 | Closed виключено | S-02-A / S-02-B / REF-03 | DOCUMENT MAPPED | NOT VERIFIABLE (current Figma) | T-08 |

## Додаткові UI-релевантні бізнес-правила

| Rule | Expected | Evidence/result |
|---|---|---|
| BR-01 | Authenticated 2 Member + 1 Lead | DOCUMENT MAPPED; real authentication IMPL |
| BR-03/04/05 | New Open, priority unset; only four selectable priorities | DOCUMENT MAPPED; current Figma NOT VERIFIABLE |
| BR-06 | Only Lead changes priority | DOCUMENT MAPPED; REF-01 NOT VERIFIABLE |
| BR-08/08.1 | Current assignee only; 4 transitions | DOCUMENT MAPPED; REF-01/02 NOT VERIFIABLE |
| BR-09/09.1 | High/Critical non-Closed; Resolved included | DOCUMENT MAPPED; T-08 not independently run |
| BR-10/11 | No delete/change history | DOCUMENT MAPPED; full-frame inspection pending |
| BR-12 | AI recommendation not in MVP | DOCUMENT MAPPED; full-frame inspection pending |

## Частина B — UX ризики, що потребують ручної перевірки

1. Чи `Open overlay` справді залишає викликавший All/Important список видимим позаду.
2. Чи validation не переміщує форму і помилки відповідають лише порожнім полям.
3. Чи disabled status не має success hotspot у Lead non-assignee.
4. Чи у довгих Title доступний повний текст на Details.
5. Чи всі label/error texts читабельні в режимі Present на типовому масштабі.

Це **перелік ризиків для перевірки**, а не підтверджені дефекти поточної версії.

## Частина C — підсумок

- **UI design coverage:** `DOCUMENT COMPLETE / FIGMA NOT INDEPENDENTLY VERIFIED`.
- **Prototype evidence:** `USER REPORTED`, без незалежного Present record.
- **Implementation tests outstanding:** authentication, server ACL, DB, unique ID, comment persistence, performance, HTTPS, backups.
- **Control D:** студент має підтвердити/відхилити знайдені дефекти і повторно перевірити змінені states. Не можна оголошувати повне PASS до цієї перевірки.
