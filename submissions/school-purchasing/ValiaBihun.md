# Здача WS6

## Дані

- Роль: pm
- Команда: school-purchasing
- GitHub-логін: ValiaBihun
- Ваше репо: https://github.com/ValiaBihun/2026-quitcode-dream-team
- SHA: 8f0fee554e7d6c50ba62e995aefda3eab7156eaa
- Репо вимог PM: https://github.com/ValiaBihun/2026-quitcode-dream-team
- Прод-URL: —

Назва репо вимог відрізняється від шаблону `school-purchasing-spec` (`2026-quitcode-dream-team`); перейменування не планується, бо SHA й усі посилання нижче вказують на цю назву.

## PM

- Сховище вимог: issues
- Продукт: https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/1
- Вимоги першого зрізу: https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/2
- Самоперевірка за чеклістом: https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/2#issuecomment-6219038941
- Питання, на які ви відповіли: https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/9, https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/10, https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/11, https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/12, https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/13, https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/14
- Зміни вимог із журналом змін: https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/2#issuecomment-6291063389

### Нотатка PM — порівняння реалізацій (трек D)

Порівняно репо трьох розробників: @YarynaPankivv (знімок вимог 2026-10-20), @mvorobets-blip (2026-10-21), @kdeineko-tech (2026-10-22). Знімки різні, тому в кожному пункті розробники читали один і той самий текст AC: у пункті 1 це вимога https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/40 (її обидва розробники мали на знімках 10-21 і 10-22), у пунктах 2 і 3 — текст AC-ORG-12 і AC-ORG-13 до відповідей на питання #43 і #45 (22.10). Посилання на файли — на `main` розробників на 22.10: @YarynaPankivv `538d041d6e3ef5696808b56b4b0216042ef2e537`, @mvorobets-blip `8e051726a2aed0909a72571970b85fdc4f5ce69e`, @kdeineko-tech `1b4e00f1807229c31e7ef82a252cb3a426fb0a25`.

1. **AC / вимога:** AC-ORG-25 і AC-ORG-27 — «У списку дозволених типів заявок є «Витрата карткою»» та «У профілі серед типів закупівлі лише «Відділ закупівель»» (https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/40)
   **Як прочитали чи реалізували:** @mvorobets-blip — один список «дозволених типів заявок і типів закупівлі»: «Витрата карткою», «Запит на чек», «Рахунок постачальника» і «Самостійна закупівля» разом, кожен лише з дозволом (https://github.com/mvorobets-blip/school-purchasing/blob/8e051726a2aed0909a72571970b85fdc4f5ce69e/openspec/specs/permissions-access/spec.md#L22; припущення в https://github.com/mvorobets-blip/school-purchasing/blob/8e051726a2aed0909a72571970b85fdc4f5ce69e/docs/spec-reading.md#L61-L63). @kdeineko-tech — два окремі списки: типи заявок (три, з дозволом) і типи закупівлі («Відділ закупівель» завжди, «Самостійна закупівля» з дозволом) (https://github.com/kdeineko-tech/school-purchasing/blob/1b4e00f1807229c31e7ef82a252cb3a426fb0a25/openspec/specs/access-permissions/spec.md#L17-L24 і https://github.com/kdeineko-tech/school-purchasing/blob/1b4e00f1807229c31e7ef82a252cb3a426fb0a25/openspec/specs/access-permissions/spec.md#L48-L53; припущення в https://github.com/kdeineko-tech/school-purchasing/blob/1b4e00f1807229c31e7ef82a252cb3a426fb0a25/docs/spec-reading.md#L68-L70).
   **Чому:** у #40 і в матриці прав слова «тип заявки» і «тип закупівлі» не розведені, а дозвіл і тип називаються однаково — «Самостійна закупівля»; категорія «Термінологія».
   **Що зробив PM:** відповів на питання https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/44 (варіант A, рівно два типи закупівлі), обидва типи визначено в глосарії «Продукту»; тексти AC-ORG-23 і AC-ORG-27 залишив без змін.
2. **AC / вимога:** AC-ORG-12 — «він не може увійти в систему» (https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/39)
   **Як прочитали чи реалізували:** @YarynaPankivv — те саме повідомлення, що й при хибному паролі, щоб не розкривати стан акаунта (https://github.com/YarynaPankivv/school-purchasing/blob/538d041d6e3ef5696808b56b4b0216042ef2e537/src/app/login/actions.ts#L28-L35, коментар «стан облікового запису не розкриваємо»; статус `реалізовано` у https://github.com/YarynaPankivv/school-purchasing/blob/538d041d6e3ef5696808b56b4b0216042ef2e537/docs/conformance.md#L56). @kdeineko-tech — окреме повідомлення про деактивацію, щоб працівник одразу знав, що звернутися треба до адміністратора (рекомендація в https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/45).
   **Чому:** AC не задав, що бачить користувач після відмови, хоча в сусідніх AC є точні тексти повідомлень; категорії «Потік взаємодії (UX)» і «Заглушки й розмиті слова».
   **Що зробив PM:** відповів у питанні https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/45 (варіант A), додав текст «Обліковий запис деактивовано. Зверніться до адміністратора.» до AC-ORG-12; реалізація @YarynaPankivv зроблена на знімку до відповіді, тож їй потрібне оновлення.
3. **AC / вимога:** AC-ORG-12 і AC-ORG-13 — працівник із поданими заявками й чернетками, адмін видаляє чернетку деактивованого (https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/39), хоча створення й подання заявок — наступний зріз, а форма заявки є заглушкою
   **Як прочитали чи реалізували:** @YarynaPankivv — AC-ORG-13 `реалізовано`: у неї вже є реальні чернетки, видалення чернетки деактивованого зроблене (https://github.com/YarynaPankivv/school-purchasing/blob/538d041d6e3ef5696808b56b4b0216042ef2e537/docs/conformance.md#L57). @mvorobets-blip — AC-ORG-13 `відкладено`, бо чернеток у зрізі немає (https://github.com/mvorobets-blip/school-purchasing/blob/8e051726a2aed0909a72571970b85fdc4f5ce69e/docs/conformance.md#L46). @kdeineko-tech — поставила питання, як прийняти AC без даних, і запропонувала прийняти лише відмову у вході (варіант B) (https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/43).
   **Чому:** AC посилався на дані, яких за межами зрізу ще немає; категорії «Функціональний обсяг» і «Граничні випадки й збої».
   **Що зробив PM:** відповів у питанні https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/43 (варіант B): AC-ORG-13 прибрано зі зрізу, з AC-ORG-12 прибрано умову про подані заявки.

## Розробник

—

## Бонус E

—
