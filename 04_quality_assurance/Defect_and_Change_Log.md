# Defect / Change Log — простежувані виправлення

**Правило:** `REPORTED FIX` ≠ `VERIFIED FIX`. Жоден дефект не позначається CLOSED без фактичного повторного тесту. Посилання на фінальну Figma — `../03_figma/Figma_Link_and_Version.md`.

| ID | Етап | Спостереження / джерело | Severity | Виконавець / метод | Зміна | Доказ / retest | Стан |
|---|---|---|---|---|---|---|---|
| DFX-01 | F1 | Старий AI-результат — одне довге полотно; старий звіт | Major | Студент, ручне розділення (за старим звітом) | Виділено окремі продуктні frames | Старий звіт; актуальний ретест не надано | REPORTED FIX |
| DFX-02 | F1/P1 | Create показувався як окремий frame, не modal; попередні скриншоти | Major | Студент, Figma Prototype `Open overlay` (за листуванням) | Налаштовано modal поверх списку | Скриншот налаштувань; поточний Present не перевірено | REPORTED FIX |
| DFX-03 | P1 | Потрібна незалежна required validation для обох полів; вимоги AC-01.2/3 | Major | Студент + Figma Agent, state variants M-01-A..G (за листуванням) | 7 підготовлених станів і Swap overlay | Попередній скриншот станів; фактичний Present потрібен | REPORTED FIX |
| DFX-04 | G1 | Старий звіт не мав повної 33-AC traceability | Major | AI-асистент, документальне доповнення | Source Check + Traceability_33AC.csv | `../01_requirements/Traceability_33AC.csv` | DOCUMENT FIXED |
| DFX-05 | G3 | Не було повного контролю non-assignee Lead та 4 transitions у старому звіті | Critical risk | AI-асистент, контракти/матриці | REF-01/02 та тестові очікування документовані | `../02_ux_contract/Screen_Contracts.md`; Figma не перевірено | DOCUMENT FIXED / UI OPEN |
| DFX-06 | G5 | Початковий короткий Figma prompt не містив errors, rights, filtering | Major | AI-асистент, новий самодостатній brief | Повний англомовний brief | `../02_ux_contract/Figma_Brief_EN.md` | DOCUMENT FIXED |
| DFX-07 | F2 | Додаткові REF-01..06 для handoff/verification | Improvement | Студент + Figma Agent (за повідомленням) | Додано reference examples | Поточна Figma, ручна перевірка потрібна | USER REPORTED |
| DFX-08 | P1 | Потрібен доказ фактичного проходження T-01..T-10 | Evidence gap | Учасники; Figma Present і відео | Ще не зафіксовано у протоколі | `Prototype_Test_Record.md`, відео/timecodes | OPEN |

## Формат запису наступного реального виправлення

`ID | stage | reviewer | artifact/version | method | expected vs actual | defect | severity | owner | correction (manual / exact AI prompt) | corrected artifact link | retest actor/date | PASS/FAIL`.

Не стирати невиправлені дефекти, не замінювати їх заявою «все працює» без протоколу. Якщо студент у відео продемонструє PASS, заповнити дату/виконавця/timecode і змінити статус відповідного запису.
