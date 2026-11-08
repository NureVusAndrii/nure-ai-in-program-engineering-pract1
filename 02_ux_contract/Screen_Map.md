# Screen Map — продуктові поверхні та reference states

Основний продукт має **S-01, S-02, M-01, S-03**. Інші позначення — стани/приклади тих самих поверхонь, не додаткові функції.

| ID | Тип | Призначення / дані | Дії |
|---|---|---|---|
| S-01 | boundary | Authentication required; mechanism TBD | Не симулювати login |
| S-02-A | list state | All Issues: 8 fixture rows, ID/Title/Status/Priority/Assignee | Important, New Issue, issue details |
| S-02-B | list state | Important Issues: 001/002/003/007 | All, New Issue, issue details |
| S-02-C | list state | Zero registered issues; No issues yet | New Issue |
| M-01-A | overlay | Title empty, Description empty, no errors | fill either, Create, Cancel |
| M-01-B | overlay | Title filled, Description empty, no errors | fill Description, Create, Cancel |
| M-01-C | overlay | Title empty, Description filled, no errors | fill Title, Create, Cancel |
| M-01-D | overlay | Both filled, valid | Create success, Cancel |
| M-01-E | overlay | Both empty, both required errors | fill either, Cancel |
| M-01-F | overlay | Title filled, Description required error | fill Description, Cancel |
| M-01-G | overlay | Description filled, Title required error | fill Title, Cancel |
| S-03 | details | ID, Title, Description, Status, Priority, Assignee, Author, Created at, Comments | Back; permitted edit actions |
| S-03-NEW | prepared details | Newly created issue Open/Not Set, author/time | Back |
| REF-01 | service examples | role × assignee permissions | Not in main navigation |
| REF-02 | service examples | 4 allowed status edges; Closed terminal | Not in main navigation |
| REF-03 | service examples | Important filtering comparison | Not in main navigation |
| REF-04 | service examples | comment validation/success/save error | Not in main navigation |
| REF-05 | service examples | zero issues, no important, initial issue | Not in main navigation |
| REF-06 | service examples | components and interaction states | Not in main navigation |

## Переходи — контракт (не підтверджений незалежним Present)

| T-ID | Звідки → куди | Trigger / дія | Результат |
|---|---|---|---|
| NAV-01 | S-02-A → S-02-B | Important tab / Navigate to | Тільки High/Critical не Closed |
| NAV-02 | S-02-B → S-02-A | All tab / Navigate to | Усі 8 fixture issues |
| NAV-03 | S-02-A/B → M-01-A | New Issue / Open overlay | Позаду лишається викликавший list |
| NAV-04 | M-01-A/B/C/E/F/G → M-01-… | Click field / Swap overlay | Підготовлене заповнення, попередній list не змінюється |
| NAV-05 | M-01-A/B/C → M-01-E/F/G | Invalid Create / Swap overlay | Помилки лише для порожніх полів |
| NAV-06 | M-01-D → S-03-NEW | Valid Create / Navigate to | Підготовлений новий issue, не DB insert |
| NAV-07 | M-01-A..G → previous S-02 | Cancel / X / Close overlay | Без створення |
| NAV-08 | S-02-A/B → S-03 | Click issue Title / Navigate to | Деталі того самого ID |
| NAV-09 | S-03 → calling S-02 | Back | Попередній таб збережено (D-07) |
| NAV-10 | S-03 → prepared S-03 state | Lead Apply assignee/priority | Один assignee; priority з 4 значень |
| NAV-11 | S-03 → prepared S-03 state | Current assignee Apply status | Лише 4 дозволені переходи |
| NAV-12 | S-03 → prepared comment state | Add Comment | Success/empty/error відповідно до fixture |

**Заборонені дії:** жодного hotspot, що веде до успішного стану. REF-01–06 не підключаються до основного user flow.

## Модальна форма: таблиця станів

| From | Click Title | Click Description | Click Create |
|---|---|---|---|
| A | B | C | E |
| B | B | D | F |
| C | D | C | G |
| D | D | D | S-03-NEW |
| E | F | G | E (без success) |
| F | F | D | F (без success) |
| G | D | G | G (без success) |

Це сценарна симуляція кліками, **не справжнє введення тексту**. У Figma для зміни стану використовувати `Swap overlay`, для початкового відкриття — `Open overlay`, для Cancel — `Close overlay`.
