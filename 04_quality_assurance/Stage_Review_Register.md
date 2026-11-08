# Поетапний журнал перевірок G1–G6 / F1–F2 / P1

Методичка §22 вимагає: **хто**, **який документ**, **як**, **результат**, **де дефект**, **хто і як виправив**, **доказ виправлення або відкритий стан**. Нижче зафіксовано тільки відомі події.

| Stage | Reviewer / date | Artifact | How checked | Outcome | Correction / link | Retest |
|---|---|---|---|---|---|---|
| G1 / Control A | AI-асистент, 08.11.2026 | SD_Spec → Source Check / Input Pack | Звірка §§1,3,5,8 та 33 AC | DOCUMENT CHECKED | `../01_requirements/Source_Check.md` | Human source sign-off pending |
| G2 | AI-асистент, 08.11.2026 | Screen Map / Decision Log | Контроль scope, states, routes | DOCUMENT REVIEW | `../02_ux_contract/Screen_Map.md` | D-04 sign-off pending |
| G3 | AI-асистент, 08.11.2026 | Screen Contracts / Traceability | Permission/status matrix, all AC IDs | DOCUMENT REVIEW | `../02_ux_contract/Screen_Contracts.md` | Figma review pending |
| G4 / Control B | AI-асистент, 08.11.2026 | План/контракти | Критичний документальний review | PLAN READY FOR HUMAN SIGN-OFF | `Plan_Review.md` | Independent peer pending |
| G5 / Control C | AI-асистент, 08.11.2026 | Figma Brief | Самодостатність і exclusions | DOCUMENT READY | `../02_ux_contract/Figma_Brief_EN.md` | Human sign-off pending |
| F1 | Студент, раніше (за старим звітом) | Initial Figma | Повідомлено про ручне розділення полотна | REPORTED | `Defect_and_Change_Log.md` DFX-01 | Latest version unverified |
| F2 | Студент + Figma Agent (за листуванням) | M-01 states, REF examples | Зміни за промптами; скриншоти частини станів | USER REPORTED | Figma URL; DFX-02/03/07 | Present pending |
| P1 | Студент, 08.11.2026 (повідомлення) | Figma prototype | Студент повідомив, що переходи працюють | USER REPORTED | `Prototype_Test_Record.md` | T-01..T-10 NOT RUN independently |
| G6 / Control D | AI-асистент, 08.11.2026 | Доступні документи/старі screenshots | 33-AC document mapping; evidence limitations | DOCUMENT REVIEW; FIGMA NOT VERIFIED | `Final_Review_Report.md` | Human Present + video pending |

**Розподіл обов'язків учасників і погодження:** вписати справжні імена/дати після особистої перевірки; не приписувати незалежну перевірку AI іншій людині.
