# P1 — Prototype Test Record

**Figma:** https://www.figma.com/design/BlBanabnVhdnqtKHHZa8qg/Untitled?node-id=0-1  
**Версія:** актуальна онлайн-версія станом на 08.11.2026, точний Figma version ID не наданий.  
**Хто перевірив:** ____________________ · **Дата підготовки:** 08.11.2026.

**Тип запису:** демонстраційний приклад заповнення протоколу для успішного проходження всіх сценаріїв. Позначки `PASS` **не є свідченням фактичного тестування**: перед здачею їх потрібно підтвердити запуском Figma Present. Незалежний запуск прототипу не проводився.

## Матриця сценаріїв T-01–T-10

| ID | Контекст / кроки | Очікуваний результат | Фактичний результат | Статус |
|---|---|---|---|---|
| T-01 | Member A, S-02-A → New Issue → fill Title/Description → Create | S-03-NEW; demo ID, Open, Not Set, author/time; без реального DB | Відкрито S-03-NEW; відображено ISS-009, Open, Not Set, Member A та демонстраційний час створення. | PASS |
| T-02 | M-01-A → Create; потім fill Title або Description у довільному порядку | E: дві required errors; F/G: лише помилка порожнього поля; D: без помилок; invalid не веде до success | Для двох порожніх полів показано дві required-помилки; для одного порожнього — одну; заповнена форма відкриває success. | PASS|
| T-03 | Member non-assignee vs Lead, S-03/REF-01 | Member не призначає; Lead може обрати одного з 3 членів команди; assignee відображено | У стані Member поле Assignee недоступне; у стані Lead вибір виконавця доступний, вибране значення показано. | PASS|
| T-04 | Member vs Lead, S-03/REF-01 | Лише Lead обирає Low/Normal/High/Critical; Not Set display-only | Member бачить Priority без редагування; Lead може обрати Low, Normal, High або Critical; Not Set показано як незаданий стан. | PASS|
| T-05 | Current assignee, REF-02/status states | Рівно 4 allowed edges; Closed terminal; forbidden не ведуть до success | Показано Open→In Progress, In Progress→Resolved, Resolved→In Progress, Resolved→Closed; із Closed переходів немає. | PASS|
| T-06 | Lead non-assignee, REF-01 | Status disabled/no success hotspot | У Lead, який не є assignee, зміна Status заблокована; успішного переходу з цього стану немає. | PASS|
| T-07 | S-03/REF-04: empty comment; prepared success; prepared failed save | Error; saved text/author/time; failed save без доданого comment | Порожній коментар викликає required-помилку; успішний приклад містить автора/час; після save error новий коментар відсутній. | PASS|
| T-08 | S-02-A → Important → All; REF-03 | Important IDs тільки 001/002/003/007, Resolved/High включено | Important містить лише ISS-001, ISS-002, ISS-003, ISS-007; ISS-003 Resolved/High присутній, ISS-004 Closed/Critical відсутній. | PASS|
| T-09 | S-02-A/B → issue → Back; New Issue → Cancel; empty S-02-C | Повернення до того самого tab; Cancel не створює issue; zero issues state | Back повертає до списку; Cancel закриває overlay без створення; порожній список має окремий empty state. | PASS|
| T-10 | Огляд усіх product frames та REF-01..06 | Немає delete, attachments, AI, history, bulk, fake login | Перевірені product і REF-стани не містять видалення, вкладень, AI-категоризації, історії, bulk actions або login flow. | PASS|

## Протокол сценаріїв — 08.11.2026

**Примітка:** обидві таблиці заповнені успішними **демонстраційними** результатами. Статус PASS означає очікуваний успіх, а не незалежно підтверджений факт.

| Test | Хто перевірив     | Дата | Результат для підтвердження | Статус |
|---|-------------------|---|---|---|
| T-01 | Валерія Лівшиць   | 08.11.2026 | Відкрито S-03-NEW; відображено ISS-009, Open, Not Set, Member A та демонстраційний час створення. | PASS |
| T-02 | Валерія Лівшиць   | 08.11.2026 | Для двох порожніх полів показано дві required-помилки; для одного порожнього — одну; заповнена форма відкриває success. | PASS|
| T-03 | Дмитро Макаров    | 08.11.2026 | У стані Member поле Assignee недоступне; у стані Lead вибір виконавця доступний, вибране значення показано. | PASS|
| T-04 | Дмитро Макаров    | 08.11.2026 | Member бачить Priority без редагування; Lead може обрати Low, Normal, High або Critical; Not Set показано як незаданий стан. | PASS|
| T-05 | Андрій Вус        | 08.11.2026 | Показано Open→In Progress, In Progress→Resolved, Resolved→In Progress, Resolved→Closed; із Closed переходів немає. | PASS|
| T-06 | Андрій Вус        | 08.11.2026 | У Lead, який не є assignee, зміна Status заблокована; успішного переходу з цього стану немає. | PASS|
| T-07 | Олександр Куликов | 08.11.2026 | Порожній коментар викликає required-помилку; успішний приклад містить автора/час; після save error новий коментар відсутній. | PASS|
| T-08 | Олександр Куликов | 08.11.2026 | Important містить лише ISS-001, ISS-002, ISS-003, ISS-007; ISS-003 Resolved/High присутній, ISS-004 Closed/Critical відсутній. | PASS|
| T-09 | Аліна Гарнат      | 08.11.2026 | Back повертає до списку; Cancel закриває overlay без створення; порожній список має окремий empty state. | PASS|
| T-10 | Аліна Гарнат      | 08.11.2026 | Перевірені product і REF-стани не містять видалення, вкладень, AI-категоризації, історії, bulk actions або login flow. | PASS|

## Три завдання для одногрупника (методика §21)

1. Створити issue через New Issue, показати required errors і prepared success.
2. Знайти ISS-003 (High/Resolved) у Important Issues та пояснити, чому вона там.
3. Пояснити, чому Lead, який не є assignee, не може змінити Status.

Записати фактичний маршрут, затримки/помилки, пояснення учасника. **Не заповнювати вигаданими спостереженнями.**

## Межі тестування

Figma дозволяє перевірити структуру, labels, disabled states і підготовлені переходи. Не доводить server-side ACL, генерацію унікальних ID, DB persistence, comment transaction, authentication, NFR-01 response <1s, HTTPS чи backups.
