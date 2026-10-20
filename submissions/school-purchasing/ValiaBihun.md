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

Станом на здачу специфікацію першого зрізу має один розробник (@YarynaPankivv): у репо @mvorobets-blip вимоги синхронізовано 19.10, але специфікації й коду ще немає. Тому пункти нижче — розбіжності між текстом #2 зі знімка 2026-10-17 і реалізацією @YarynaPankivv; другим читанням у кожному пункті є буквальний текст AC зі знімка (посилання в пункті). Знімок вимог: https://github.com/YarynaPankivv/school-purchasing/blob/20f5effc876065ef7e978c0896fd024bc0a8f432/requirements/2-administrator-nalashtovuie-viddily.md

1. **AC / вимога:** AC-ORG-05 — «Дано працівник, якого адміністратор призначає схвалювачем відділу, де він заявник. Коли призначення збережено. Тоді його роль стає `approver`» (https://github.com/YarynaPankivv/school-purchasing/blob/20f5effc876065ef7e978c0896fd024bc0a8f432/requirements/2-administrator-nalashtovuie-viddily.md#L29)
   **Як прочитали чи реалізували:** @YarynaPankivv — адміністратор лишається `admin`, а `approver` отримують лише працівники без цієї ролі (https://github.com/YarynaPankivv/school-purchasing/blob/12bf680c2acc04aa719b98b508866c2baa736784/supabase/migrations/20261018182200_org_departments.sql#L127-L141, умова `p.role <> 'admin'`); буквальне читання тексту AC ([AC-ORG-05](https://github.com/YarynaPankivv/school-purchasing/blob/20f5effc876065ef7e978c0896fd024bc0a8f432/requirements/2-administrator-nalashtovuie-viddily.md#L29)) — роль змінюється будь-кому, зокрема адміністратору; ще не реалізоване, друге прочитання дає сам текст.
   **Чому:** слово «працівник» охоплює й адміністратора, а AC-ORG-11 каже, що роль `admin` не залежить від відділів; категорія «Ролі й доступ».
   **Що зробив PM:** відповів у питанні https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/12 (варіант A, адміністратор лишається `admin` і схвалює відділ); у AC-ORG-05 додано «без ролі `admin`», додано AC-ORG-20, рядок у журналі змін.
2. **AC / вимога:** AC-ORG-07 і AC-ORG-17 — «Дано працівник без дозволу на «Витрату карткою». Коли він відкриває вибір типу заявки. Тоді типу «Витрата карткою» там немає» (https://github.com/YarynaPankivv/school-purchasing/blob/20f5effc876065ef7e978c0896fd024bc0a8f432/requirements/2-administrator-nalashtovuie-viddily.md#L31), а також AC-ORG-08 (https://github.com/YarynaPankivv/school-purchasing/blob/20f5effc876065ef7e978c0896fd024bc0a8f432/requirements/2-administrator-nalashtovuie-viddily.md#L32)
   **Як прочитали чи реалізували:** @YarynaPankivv — звичайним працівникам тип доступний лише з дозволом, а адміністратор отримує «Витрату карткою», «Запит на чек», «Рахунок постачальника» і «Самостійну закупівлю» без дозволу, за матрицею прав (https://github.com/YarynaPankivv/school-purchasing/blob/12bf680c2acc04aa719b98b508866c2baa736784/supabase/migrations/20261018200633_org_permissions.sql#L103-L107); буквальне читання тексту AC ([AC-ORG-07](https://github.com/YarynaPankivv/school-purchasing/blob/20f5effc876065ef7e978c0896fd024bc0a8f432/requirements/2-administrator-nalashtovuie-viddily.md#L31), [AC-ORG-08](https://github.com/YarynaPankivv/school-purchasing/blob/20f5effc876065ef7e978c0896fd024bc0a8f432/requirements/2-administrator-nalashtovuie-viddily.md#L32)) — дозвіл потрібен і адміністратору; ще не реалізоване, друге прочитання дає сам текст.
   **Чому:** AC каже «працівник», а матриця прав у «Продукті» для адміністратора дозволів не вимагає; категорія «Ролі й доступ».
   **Що зробив PM:** відповів у питанні https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/13 (варіант A); AC-ORG-08 стосується лише тих, хто без ролі `admin`, додано AC-ORG-23 і рядок у журналі змін; правки в AC-ORG-07 і AC-ORG-17 заплановано в коментарі «У наступному оновленні (WS7)» у https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/2.
3. **AC / вимога:** AC-ORG-01 і AC-ORG-11 — заявки створюються лише від імені відділів, де людина заявник; адміністратора без відділів прибрано з усіх відділів, а матриця прав дозволяє йому «Закупівлю» й «Відшкодування» (https://github.com/YarynaPankivv/school-purchasing/blob/20f5effc876065ef7e978c0896fd024bc0a8f432/requirements/2-administrator-nalashtovuie-viddily.md#L25)
   **Як прочитали чи реалізували:** @YarynaPankivv — адміністратор без відділів заявок не створює, це тимчасове рішення з питання (https://github.com/YarynaPankivv/school-purchasing/blob/12bf680c2acc04aa719b98b508866c2baa736784/supabase/migrations/20261018182200_org_departments.sql#L337, умова `private.is_member(department_id)`); буквальне читання матриці прав у [«Продукті»](https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/1) і [AC-ORG-01](https://github.com/YarynaPankivv/school-purchasing/blob/20f5effc876065ef7e978c0896fd024bc0a8f432/requirements/2-administrator-nalashtovuie-viddily.md#L25) — адміністратор подає від імені будь-якого відділу; ще не реалізоване, друге прочитання дає сам текст.
   **Чому:** AC-ORG-01 не казав, що адміністратор подає від імені будь-якого відділу; категорія «Граничні випадки й збої».
   **Що зробив PM:** відповів у питанні https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/9 (варіант B, адміністратор обирає будь-який відділ); додано AC-ORG-22, рядок у журналі змін; Ярина зафіксувала своє рішення як тимчасове (D10 у https://github.com/YarynaPankivv/school-purchasing/blob/12bf680c2acc04aa719b98b508866c2baa736784/openspec/changes/impl-org/design.md).
4. **AC / вимога:** AC-ORG-04 — «Дано працівник, який був схвалювачем лише одного відділу…» (https://github.com/YarynaPankivv/school-purchasing/blob/20f5effc876065ef7e978c0896fd024bc0a8f432/requirements/2-administrator-nalashtovuie-viddily.md#L28)
   **Як прочитали чи реалізували:** @YarynaPankivv — для схвалювача кількох відділів роль лишається `approver`, поки він схвалює хоча б один (https://github.com/YarynaPankivv/school-purchasing/blob/12bf680c2acc04aa719b98b508866c2baa736784/supabase/migrations/20261018182200_org_departments.sql#L135-L137); буквальне читання тексту [AC-ORG-04](https://github.com/YarynaPankivv/school-purchasing/blob/20f5effc876065ef7e978c0896fd024bc0a8f432/requirements/2-administrator-nalashtovuie-viddily.md#L28) — роль `requester` одразу після зняття з будь-якого відділу; ще не реалізоване, друге прочитання дає сам текст.
   **Чому:** критерій описував лише випадок одного відділу, а правило для кількох відділів був пропуск; категорія «Домен і модель даних».
   **Що зробив PM:** відповів у питанні https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/11 (варіант A); додано AC-ORG-19 і рядок у журналі змін.

## Розробник

—

## Бонус E

—
