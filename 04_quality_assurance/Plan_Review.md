# G4 — незалежний документальний review плану (не Figma Present)

**Рецензент:** AI-асистент, 08.11.2026. **Обсяг:** SD_Spec + методичка + підготовлені Input Pack, Decision Log, Screen Map, Screen Contracts, Figma Brief. Це перевірка документів, не незалежна людська експертиза й не перевірка Figma.

## Результати

| Група | Кількість AC | Планова coverage | Підстава | UI/Prototype proof |
|---|---:|---|---|---|
| US-01 | 5 | COVERED | M-01-A..G, S-03-NEW, C-M01-* | USER REPORTED / NOT VERIFIED |
| US-02 | 5 | COVERED | S-02-A/B/C, S-03 | NOT VERIFIED |
| US-03 | 4 | COVERED | REF-01, S-03, role matrix | NOT VERIFIED |
| US-04 | 2 | COVERED | S-03, priority selector, REF-01 | NOT VERIFIED |
| US-05 | 3 | COVERED | S-02/S-03 status | NOT VERIFIED |
| US-06 | 5 | COVERED | S-03, REF-04 comment states | NOT VERIFIED |
| US-07 | 5 | COVERED | REF-01/02, status matrix | NOT VERIFIED |
| US-08 | 4 | COVERED | S-02-B, REF-03 predicate | NOT VERIFIED |
| **Разом** | **33** | **33/33 mapped in documents** | Traceability CSV | **не 33/33 виконаних тестів** |

## Критичні логічні перевірки

- `Lead non-assignee` **не** має статусної дії: контракт коректний.
- `Resolved + High` входить до Important, `Closed + Critical` ні: контракт коректний.
- `Not Set` не selectable priority: контракт коректний.
- `Closed` не має вихідних статусних переходів; comments не заборонені лише через Closed: контракт коректний.
- Create має лише Title/Description; error стани незалежні: контракт коректний.
- Deferred US-09 та Future SR-10/11 не додані до MVP: контракт коректний.

## Відкриті питання та рекомендації

- **Q-02/Q-03:** початкове призначення і reassignment — UX-рішення, потрібне погодження людиною.
- **G4 Control B:** другий учасник має перевірити план і записати власне рішення; AI-огляд не підміняє це.
- **G6 Control D:** відкрити поточний Figma файл і перевірити фактичні REF states та всі сценарії.
- **P1:** потрібен реальний протокол Present, а не твердження, що «все працює».

**Вердикт:** `PLAN READY FOR HUMAN SIGN-OFF` (документальний рівень); `FIGMA NOT INDEPENDENTLY VERIFIED`; повне `APPROVED` не встановлено.
