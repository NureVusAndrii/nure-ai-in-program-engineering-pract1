# P1 — Prototype Test Record: покроковий протокол

**Figma:** https://www.figma.com/design/BlBanabnVhdnqtKHHZa8qg/Untitled?node-id=0-1  
**Дата підготовки:** 08.11.2026.  
**Обсяг:** клікабельні маршрути S-02-A/B, M-01-A–G, S-03 і окремі REF-стани.  
**Підстава:** користувач повідомив, що налаштовані переходи працюють; незалежного запуску Present не було.

> **Як читати статуси.** `REPORTED PASS` — автор повідомив про роботу переходів загалом, але конкретний клік цього рядка не засвідчено. `READY TO VERIFY` — покроковий сценарій із підготовленим *очікуваним*, а не вигаданим фактичним результатом. `DOC PASS` — логічну вимогу перевірено за документацією, не в інтерактивному прототипі. Ці позначки не слід підміняти `PASS` до реального виконання.

## Клікабельні маршрути та демонстраційні стани

| ID | Сценарій | Початок | Точні дії | Результат, який має бути на екрані | Тип | Відповідальний за перевірку | Статус |
|---|---|---|---|---|---|---|---|
| P-01 | All → Important | S-02-A | Натиснути вкладку Important Issues | S-02-B; вкладка Important активна; ISS-001/002/003/007 | навігація | Андрій Вус | REPORTED PASS — група переходів |
| P-02 | Important → All | S-02-B | Натиснути вкладку All Issues | S-02-A; вкладка All активна; усі 8 тестових заявок | навігація | Аліна Гарнат | REPORTED PASS — група переходів |
| P-03 | Відкриття Create з All | S-02-A | Натиснути New Issue | M-01-A як overlay поверх All Issues | навігація | Валерія Лівшиць | REPORTED PASS — група переходів |
| P-04 | Відкриття Create з Important | S-02-B | Натиснути New Issue | M-01-A як overlay поверх Important Issues | навігація | Дмитро Макаров | REPORTED PASS — група переходів |
| P-05 | Cancel | S-02-A → M-01-A | Натиснути Cancel | Overlay закривається; All Issues залишається відкритим | навігація | Олександр Куликов | REPORTED PASS — група переходів |
| P-06 | Закриття X | S-02-B → M-01-A | Натиснути X | Overlay закривається; Important Issues залишається відкритим | навігація | Андрій Вус | REPORTED PASS — група переходів |
| P-07 | Порожня форма | M-01-A | Натиснути Create, не заповнюючи поля | M-01-E; показано дві помилки Title/Description | навігація | Аліна Гарнат | REPORTED PASS — група переходів |
| P-08 | Title → заповнений | M-01-A | Натиснути Title | M-01-B; Title = Login fails; Description порожній | навігація | Валерія Лівшиць | REPORTED PASS — група переходів |
| P-09 | Description → заповнений | M-01-A | Натиснути Description | M-01-C; Description = Application crashes after login. | навігація | Дмитро Макаров | REPORTED PASS — група переходів |
| P-10 | Title-only submit | M-01-B | Натиснути Create | M-01-F; помилка тільки для Description | навігація | Олександр Куликов | REPORTED PASS — група переходів |
| P-11 | Description-only submit | M-01-C | Натиснути Create | M-01-G; помилка тільки для Title | навігація | Андрій Вус | REPORTED PASS — група переходів |
| P-12 | Title → Description | M-01-B | Натиснути Description | M-01-D; обидва поля заповнені; помилок немає | навігація | Аліна Гарнат | REPORTED PASS — група переходів |
| P-13 | Description → Title | M-01-C | Натиснути Title | M-01-D; обидва поля заповнені; помилок немає | навігація | Валерія Лівшиць | REPORTED PASS — група переходів |
| P-14 | Виправити Title error | M-01-G | Натиснути Title | M-01-D; помилка Title зникає | навігація | Дмитро Макаров | REPORTED PASS — група переходів |
| P-15 | Виправити Description error | M-01-F | Натиснути Description | M-01-D; помилка Description зникає | навігація | Олександр Куликов | REPORTED PASS — група переходів |
| P-16 | Виправити обидві: Title першим | M-01-E | Натиснути Title | M-01-F; залишається тільки Description error | навігація | Андрій Вус | REPORTED PASS — група переходів |
| P-17 | Виправити обидві: Description першим | M-01-E | Натиснути Description | M-01-G; залишається тільки Title error | навігація | Аліна Гарнат | REPORTED PASS — група переходів |
| P-18 | Повтор invalid submit | M-01-E | Натиснути Create ще раз | Лишається M-01-E; success не відкривається | навігація | Валерія Лівшиць | REPORTED PASS — група переходів |
| P-19 | Повтор Title-only submit | M-01-F | Натиснути Create ще раз | Лишається M-01-F; success не відкривається | навігація | Дмитро Макаров | REPORTED PASS — група переходів |
| P-20 | Повтор Description-only submit | M-01-G | Натиснути Create ще раз | Лишається M-01-G; success не відкривається | навігація | Олександр Куликов | REPORTED PASS — група переходів |
| P-21 | Успішне Create | M-01-D | Натиснути Create | S-03-NEW; ISS-009, Open, Not Set, Unassigned, Member A | навігація | Андрій Вус | REPORTED PASS — група переходів |
| P-22 | Issue row → Details | S-02-A | Натиснути рядок ISS-003 | S-03; дані саме ISS-003 | навігація | Аліна Гарнат | REPORTED PASS — група переходів |
| P-23 | Back → All | S-03 з All | Натиснути Back | S-02-A, All Issues | навігація | Валерія Лівшиць | REPORTED PASS — група переходів |
| P-24 | Important row → Details | S-02-B | Натиснути ISS-003 | S-03; ISS-003 з Resolved/High | навігація | Дмитро Макаров | REPORTED PASS — група переходів |
| P-25 | Back → Important | S-03 з Important | Натиснути Back | S-02-B, Important Issues | навігація | Олександр Куликов | REPORTED PASS — група переходів |
| P-26 | Фільтр Resolved High | S-02-B | Знайти ISS-003 | ISS-003 присутня, бо Resolved != Closed | візуальна звірка | Андрій Вус | READY TO VERIFY |
| P-27 | Фільтр Closed Critical | S-02-B | Перевірити ISS-004 | ISS-004 відсутня попри Critical | візуальна звірка | Аліна Гарнат | READY TO VERIFY |
| P-28 | Фільтр Low/Normal/Not Set | S-02-B | Перевірити ISS-005/006/008 | Усі три відсутні | візуальна звірка | Валерія Лівшиць | READY TO VERIFY |
| P-29 | Empty All | S-02-C | Відкрити окремий reference frame | No issues yet; New Issue видимий | статичний стан | Дмитро Макаров | READY TO VERIFY |
| P-30 | Empty Important | REF-05-B | Оглянути reference frame | No important issues found; All Issues доступний | статичний стан | Олександр Куликов | READY TO VERIFY |
| P-31 | Роль Member non-assignee | REF-01-A | Оглянути Assignee/Priority/Status | Недоступні дії призначення, пріоритету та зміни чужого статусу | статичний стан | Андрій Вус | READY TO VERIFY |
| P-32 | Роль Lead non-assignee | REF-01-C | Оглянути Assignee/Priority/Status | Assignee/Priority доступні, Status недоступний | статичний стан | Аліна Гарнат | READY TO VERIFY |
| P-33 | Статусні переходи | REF-02 | Оглянути 4 allowed edges та Closed | Є тільки Open→In Progress, In Progress→Resolved, Resolved→In Progress/Closed | статичний стан | Валерія Лівшиць | READY TO VERIFY |
| P-34 | Коментарі | REF-04 | Оглянути empty/success/failure examples | Required error; success з автором/часом; failure без нового коментаря | статичний стан | Дмитро Макаров | READY TO VERIFY |

## Три сценарії для незалежного мінітесту (§21 методички)

| ID | Учасник, відповідальний за організацію | Завдання без підказок | Критерій успіху | Стан |
|---|---|---|---|---|
| U-01 | Андрій Вус | Створити заявку; спочатку навмисно залишити поля порожніми | Дві помилки, після заповнення обох — ISS-009 | READY TO VERIFY |
| U-02 | Аліна Гарнат | Знайти Resolved/High заявку у Important Issues | ISS-003 знайдено, ISS-004 Closed/Critical виключено | READY TO VERIFY |
| U-03 | Валерія Лівшиць | Пояснити, чи може Lead змінювати статус чужої заявки | Правильно названо обмеження; REF-01-C | READY TO VERIFY |

## Межі

Це прототип із підготовленими екранами та переходами, а не функціональна система. Не тестуються реальні ролі/авторизація, зміна даних у БД, збереження коментарів, серверні права, швидкодія чи HTTPS. Окремі REF-екрани є демонстраційними, тому для них не вигадуються клікабельні дії.
