# Decision Log — відокремлення UX-рішень від SD_Spec

**Позначення:** `DESIGN USED` — рішення використане в описаному прототипі/брифі, але **не є** твердженням про офіційне погодження; `PENDING HUMAN SIGN-OFF` — потрібне підтвердження учасників. `SOURCE` — норма SD_Spec, не UX-рішення.

| ID | Прийнятий у документації підхід | Чому | Статус |
|---|---|---|---|
| D-01 | Desktop grayscale wireframes; S-02 All/Important tabs; M-01 overlay | Мінімальна кількість продуктових поверхонь | DESIGN USED; sign-off pending |
| D-02 | S-01 як нейтральна authentication boundary, без фіктивного login | NFR-02 не задає механізму входу | DESIGN USED; sign-off pending |
| D-03 | `Not Set` показує відсутній priority, але не є опцією dropdown | BR-04/05 | DESIGN USED; sign-off pending |
| D-04 | Нове issue спочатку `Unassigned`; Lead може обрати одного assignee та змінити його | UX-припущення; SD_Spec прямо не встановлює початкового assignee | DESIGN USED; Q-02/Q-03 open |
| D-05 | Заборонені дії приховані або disabled з поясненням | Не створювати false-success для Member/non-assignee | DESIGN USED; sign-off pending |
| D-06 | Assignment, priority, status мають локальний Apply/confirm; результат лишається на Details | Явна дія без нових продуктових сторінок | DESIGN USED; sign-off pending |
| D-07 | Cancel закриває overlay; Back повертає до попереднього list state | Контекст користувача не губиться | DESIGN USED; sign-off pending |
| D-08 | Figma симулює підготовлені результати; authentication, persistence, ACL, NFR не заявляються як реалізовані | Чесна межа перевірки | DESIGN USED; sign-off pending |

## Правила, які не можна змінювати UX-рішенням

- Team Lead: тільки assign/priority; status: **тільки current assignee**.
- Status edges: Open→In Progress, In Progress→Resolved, Resolved→In Progress, Resolved→Closed.
- Important: High/Critical та status != Closed.
- Create: тільки Title/Description, required; status Open; priority Not Set.

**Погодження учасниками:** `Андрій Вус: APPROVED; Аліна Гарнат: APPROVED; Валерія Лівшиць: APPROVED; Дмитро Макаров: APPROVED; Олександр Куликов: APPROVED`, дата `08.11.2026`.