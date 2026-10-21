# Здача WS6

## Дані

- Роль: pm
- Команда: school-purchasing
- GitHub-логін: ValiaBihun
- Ваше репо: https://github.com/ValiaBihun/2026-quitcode-dream-team
- SHA: 8f0fee554e7d6c50ba62e995aefda3eab7156eaa
- Репо вимог PM: https://github.com/ValiaBihun/2026-quitcode-dream-team
- Прод-URL: —

## PM

- Сховище вимог: issues
- Продукт: https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/1
- Вимоги першого зрізу: https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/2, https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/39, https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/40
- Самоперевірка за чеклістом: https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/2#issuecomment-6219038941, https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/39#issuecomment-6320868861, https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/40#issuecomment-6320882948
- Питання, на які ви відповіли: https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/9, https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/10, https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/11, https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/12, https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/13, https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/14, https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/16, https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/17, https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/18, https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/19, https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/20, https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/21, https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/22, https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/23, https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/24, https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/25, https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/26, https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/27, https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/28, https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/29, https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/30, https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/31
- Зміни вимог із журналом змін: https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/2#issuecomment-6291063389, https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/2#issuecomment-6320341923, https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/2#issuecomment-6320739796, https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/2#issuecomment-6322804364, https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/39#issuecomment-6322804959, https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/40#issuecomment-6322805529

### Нотатка PM — порівняння реалізацій (трек D)

Реалізацію порівнюю з версією issue #2 зі знімка 2026-10-17 (у репо @YarynaPankivv це коміт
https://github.com/YarynaPankivv/school-purchasing/commit/20f5effc876065ef7e978c0896fd024bc0a8f432). Усі посилання на її
репо — на коміт `7f5f5738d7d0b21802d355505423640b9f1c4799`.

1. **AC / вимога:** AC-ORG-07 — «Дано працівник без дозволу на «Витрату карткою». Коли він відкриває вибір типу заявки. Тоді типу «Витрата карткою» там немає.» (https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/2, версія 2026-10-17); так само AC-ORG-17.
   **Як прочитали чи реалізували:** @YarynaPankivv — слово «працівник» не охоплює адміністратора, бо матриця прав каже, що йому дозвіл не потрібен, тому для `admin` типи видно без дозволу; крім того, правило поширено на всі три типи («Витрата карткою», «Запит на чек», «Рахунок постачальника»), хоча AC каже лише про першу (https://github.com/YarynaPankivv/school-purchasing/blob/7f5f5738d7d0b21802d355505423640b9f1c4799/docs/spec-reading.md#L68-L72; сценарії в специфікації — https://github.com/YarynaPankivv/school-purchasing/blob/7f5f5738d7d0b21802d355505423640b9f1c4799/openspec/changes/archive/2026-10-17-add-org/specs/request-permissions/spec.md#L15-L23). Якщо читати AC буквально, він ховає тип і від адміністратора.
   **Чому:** слово «працівник» без уточнення ролі: AC про «працівника» охоплює й `admin`, хоча матриця каже інше (категорія «Ролі й доступ»); AC названо лише «Витрату карткою» — прогалина в обсязі.
   **Що зробив PM:** залишив читання розробниці як правильне й вписав у текст: 21.10 AC-ORG-07 і AC-ORG-08 прибрано з вимоги (https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/2#issuecomment-6320341923), а в новій вимозі https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/40 додано AC-ORG-25 (адміністратор без дозволу бачить тип), AC-ORG-26 і AC-ORG-27 (без ролі `admin` і без дозволу типу немає), AC-ORG-17 обмежено «без ролі `admin`»; результат сформульовано через профіль працівника (рядки журналу змін у #40 і #2). Правило ролей і рядки матриці — в «Продукті» https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/1.

2. **AC / вимога:** AC-ORG-01 — «Тоді працівник може створювати заявки лише від імені відділу «Початкова школа» і не бачить інших відділів у виборі.» (https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/2, версія 2026-10-17); на нього спирається AC-ORG-11 про адміністратора без відділів.
   **Як прочитали чи реалізували:** @YarynaPankivv — тимчасово «адміністратор без відділів заявок не створює» (рядок Q1: https://github.com/YarynaPankivv/school-purchasing/blob/7f5f5738d7d0b21802d355505423640b9f1c4799/docs/spec-reading.md#L50); у моєму питанні https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/9 я відповіла інакше — адміністратор обирає будь-який відділ, і розробниця звузила AC-ORG-01 до працівника без ролі `admin` (https://github.com/YarynaPankivv/school-purchasing/blob/7f5f5738d7d0b21802d355505423640b9f1c4799/docs/spec-reading.md#L73-L75).
   **Чому:** AC не каже, чи стосується він адміністратора, а матриця прав дозволяє адміністратору «Закупівлю» й «Відшкодування» (категорія «Граничні випадки й збої» і «Ролі й доступ»).
   **Що зробив PM:** відповідь у питанні https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/9, AC-ORG-22 (19.10); 21.10 додано AC-ORG-29 (адміністратор із відділом обирає будь-який відділ), AC-ORG-01 переформульовано через профіль працівника (рядки журналу в https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/2 і https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/40), у матрицю додано «Обирати відділ заявки».

3. **AC / вимога:** AC-ORG-05 — «Дано працівник, якого адміністратор призначає схвалювачем відділу, де він заявник. Коли призначення збережено. Тоді його роль стає `approver`.» (https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/2, версія 2026-10-17).
   **Як прочитали чи реалізували:** @YarynaPankivv — за буквою AC адміністратор, якого призначили схвалювачем, мав би стати `approver`; вона це не прийняла мовчки, а поставила питання Q4 і в реалізації лишила йому роль `admin` (https://github.com/YarynaPankivv/school-purchasing/blob/7f5f5738d7d0b21802d355505423640b9f1c4799/docs/spec-reading.md#L53). Тобто текст AC і реалізація розходяться, поки PM не відповів.
   **Чому:** AC не каже «лише для працівника без ролі `admin`»; «Продукт» не мав єдиного правила ролей (категорія «Ролі й доступ»).
   **Що зробив PM:** відповідь у питанні https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/12 — AC-ORG-05 стосується працівників без ролі `admin`, додано AC-ORG-20 (коментар «Зміна» https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/2#issuecomment-6291063389); 21.10 в «Продукт» записано єдине правило ролей, а AC-ORG-04 і AC-ORG-24 доповнено «без ролі `admin`». Лишається відкритим https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/36 — яка роль у працівника, з якого інший адміністратор зняв роль адміністратора.

4. **AC / вимога:** AC-ORG-06 — «Дано заявник відділів «Початкова школа» й «Офіс». Коли адміністратор вмикає йому автосхвалення лише у відділі «Офіс». Тоді …» (https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/2).
   **Як прочитали чи реалізували:** @mvorobets-blip — не знає, що буде, коли автосхвалення вмикають працівнику, який не є заявником відділу, і запитав у https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/37 (варіанти: відхилити, зберегти «про запас», додати як заявника); його специфікації ще немає, тож це прогноз розбіжності, а не код.
   **Чому:** AC-ORG-06 і AC-ORG-15 описують лише наслідки для заявника відділу (категорія «Граничні випадки й збої»).
   **Що зробив PM:** питання лишається відкритим; додано в розділ «Відкриті питання» вимоги https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/2.

## Розробник

—

## Бонус E

Чернетка вимог другого зрізу поза знімком розробників: https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/3 (WS7, закупівля й рішення схвалювача; issue без мітки `requirement`).

Прогін чекліста на цій вимозі: https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/3#issuecomment-6292296232. Що знайшов: багатонаслідкові AC-PUR-14, 17, 18, 21 і 23 (в одному критерії по кілька «Тоді»); у AC-PUR-29 і 31 бракувало статусів. Що змінила: розбила їх на AC-PUR-37…45 і доповнила статуси, а ID початкових критеріїв лишила (запис у «Журналі змін» вимоги від 2026-10-20). Що відклала: нові статуси («Очікує схвалення», «Частково схвалено», «Скасовано», «В обробці», «Оброблено») для глосарія «Продукту» — на WS7. Висновок: розбивати критерії треба одразу під час написання, інакше розробники по-різному читають, який із наслідків перевіряє тест.
