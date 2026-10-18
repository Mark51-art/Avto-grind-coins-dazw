*English description first, русское описание — ниже.*

## English

**Avto-grind-coins-dazw** is an AutoHotkey v2 script that farms coins with **Austin** in *Dead Ahead: Zombie Warfare* completely on its own. Tested on **Challenge 3, Location 1, Normal difficulty**, with the game running in **Google Play Games** on PC.

> [!IMPORTANT]
> Press **F1 at the exact moment the mission starts.** All of the script's timers (the ~10 s prep, the Pause → Retry cycle and, in Mode 2, the wait for the fuel to regenerate) are counted from the moment you press F1. Starting the script together with the mission keeps everything in sync.

### Which file do I need?

| File | Language | Cycle | Mode |
|---|---|---|---|
| `avto-grind-coins-dazw-200sec.EN.ahk` | English | 200 s (3 min 20 s) | Mode 1 |
| `avto-grind-coins-dazw-200sec.RU.ahk` | Русский | 200 s (3 min 20 s) | Mode 1 |
| `avto-grind-coins-dazw-1250sec.EN.ahk` | English | 1250 s (20 min 50 s) | Mode 2 |
| `avto-grind-coins-dazw-1250sec.RU.ahk` | Русский | 1250 s (20 min 50 s) | Mode 2 |

The EN and RU files do exactly the same thing. Only the comments and the on-screen popup text differ.

### Results (from my own runs)

- **Mode 1 (3:20):** ~10,000 coins per 10 missions (20 fuel). It runs until the fuel is gone.
- **Mode 2 (20:50):** ~3,000 coins per hour, which is **~72,000 coins per 24 h**, completely hands-off.

**Why 20 min 50 s?** One mission costs 2 fuel, and 20:50 is the time the game needs to regenerate those 2 fuel. By the time the script hits Retry, the fuel is already back, so the run restarts without any ads.

Coin drops are random, and my numbers were measured with the units from the screenshots below, so yours may differ.

### Requirements

- **Windows PC** with the game running in **Google Play Games**. This is the only setup I tested. I have not tried other emulators, so I can't say whether it works there.
- **AutoHotkey v2.** Get it from the [official website](https://www.autohotkey.com/download/) or from the **Microsoft Store** (search for "AutoHotkey v2").
- **Key mapping** (each key = a tap on the screen), placed on the same buttons as in the screenshot: `1` = Austin's slot · `5` = Private Rodriguez's slot · `2` = Pause (top-left corner) · `3` = Retry · `4` = backup tap next to Retry.
- **Deck:** Austin in the first slot and Private Rodriguez in the second. Only these two are deployed. The other four units are there just for the passive synergies (2 Police + 2 Rescue).

### Screenshots (attached to this release)

| File | What it shows |
|---|---|
| `2026-10-11.092000.png` | How the controls should look: keys 1–5 mapped to taps on the screen (Challenge 3, Location 1, Normal) |
| `2026-10-11.091405.png` | The deck |
| `2026-10-11.091455.png` | Austin's stats |
| `2026-10-11.091515.png` | Private Rodriguez's stats |

### Quick start

1. Install AutoHotkey v2 (see Requirements).
2. Set up the key mapping and the deck as in the screenshots.
3. Download the `.ahk` file you need and put it into the **`AutoHotkey` folder inside your Documents** (`Documents\AutoHotkey`, it appears after you install AutoHotkey). It's just a convenient place to keep all your scripts together. If you don't see the folder, create it yourself or use any other folder, because the script works from anywhere.
4. Double-click the script. A "Script PAUSED" popup appears in the top-left corner.
5. Start the mission and press **F1 at the same moment**. You'll hear a high beep and the popup will say "Script RUNNING".
6. Press **F1** again to pause. After a pause the timers start from zero, so resume only when a new mission starts. To close the script, right-click its tray icon → Exit.

### How it works

1. **F1** starts the script (high beep, popup in the top-left corner).
2. **Prep (~10 s):** nothing is pressed. Then key `5` deploys Private Rodriguez once, so he builds up the Rage Austin needs.
3. **Spam:** key `1` taps Austin's slot every ~80 ms. Each key is held for 40 ms so the game registers it reliably.
4. **End of each cycle:** the spam stops and the script presses `2` → `3` → `4`, 0.5 s apart: Pause → Retry → backup tap.
5. Back to step 2, forever. The popup shows the countdown to the next restart.

### Settings (top of each file)

| Setting | Default | What it does |
|---|---|---|
| `cycleInterval` | 200000 / 1250000 | Time between restarts, ms |
| `prepDelay` | 10000 | Wait before pressing `5`, ms |
| `repeatPrep` | true | Repeat the prep after every restart |
| `startWith23` | false | true = restart right on F1 instead of after a full cycle |
| `spamDelay` | 80 | Delay between taps of `1`, ms |
| `holdTime` | 40 | How long each key is held, ms |

Other settings (`keyGap`, `startOnLaunch`, `popupX`/`popupY`) are explained in the comments at the top of each file.

### Tips

- The game window has to stay active, because the script sends keys to the active window.
- If the game ignores the keys, try running the script as administrator.

Use at your own risk: automating inputs may go against the game's rules. Unofficial fan tool, not affiliated with the game's developers.

---

## Русский

**Avto-grind-coins-dazw** — скрипт AutoHotkey v2, который полностью автоматически фармит монеты через **Аустина (Austin)** в игре *Dead Ahead: Zombie Warfare*. Проверен на миссии **Испытание 3 (Challenge 3), Локация 1, Нормальная сложность**; игра запущена в **Google Play Games** на ПК.

> [!IMPORTANT]
> Нажимайте **F1 в тот же момент, когда начинается миссия.** Все таймеры скрипта (подготовка ~10 с, цикл Пауза → Retry и, в режиме 2, ожидание восстановления топлива) отсчитываются от нажатия F1. Если запустить скрипт одновременно с миссией, всё работает синхронно.

### Какой файл выбрать?

| Файл | Язык | Цикл | Режим |
|---|---|---|---|
| `avto-grind-coins-dazw-200sec.EN.ahk` | English | 200 с (3 мин 20 с) | Режим 1 |
| `avto-grind-coins-dazw-200sec.RU.ahk` | Русский | 200 с (3 мин 20 с) | Режим 1 |
| `avto-grind-coins-dazw-1250sec.EN.ahk` | English | 1250 с (20 мин 50 с) | Режим 2 |
| `avto-grind-coins-dazw-1250sec.RU.ahk` | Русский | 1250 с (20 мин 50 с) | Режим 2 |

Файлы EN и RU работают одинаково. Отличаются только комментарии в коде и текст всплывающего окошка.

### Результаты (мои запуски)

- **Режим 1 (3:20):** ~10 000 монет за 10 миссий (20 топлива). Работает, пока не закончится топливо.
- **Режим 2 (20:50):** ~3 000 монет в час, то есть **~72 000 монет за 24 часа**, полностью без участия человека.

**Почему 20 мин 50 сек?** Миссия стоит 2 топлива, и за 20:50 игра как раз восстанавливает эти 2 топлива. К моменту нажатия Retry топливо уже вернулось, поэтому миссия перезапускается без рекламы.

Выпадение монет случайно, а мои цифры получены с юнитами со скриншотов ниже, поэтому у вас результаты могут отличаться.

### Требования

- **ПК с Windows** и игра, запущенная через **Google Play Games**. Только эту связку я проверял. На других эмуляторах не пробовал, поэтому не могу сказать, будет ли там работать.
- **AutoHotkey v2.** Скачайте на [официальном сайте](https://www.autohotkey.com/download/) или установите из **Microsoft Store** (найдите «AutoHotkey v2»).
- **Раскладка клавиш** (каждая клавиша = нажатие в точку экрана), точки стоят на тех же кнопках, что на скриншоте: `1` = слот Аустина · `5` = слот Private Rodriguez · `2` = Пауза (левый верхний угол) · `3` = Retry · `4` = запасное нажатие рядом с Retry.
- **Колода:** Аустин в первом слоте, Private Rodriguez во втором. Выпускаются только эти двое. Остальные четыре юнита нужны лишь ради пассивных синергий (2 полицейских + 2 спасателя).

### Скриншоты (приложены к релизу)

| Файл | Что на нём |
|---|---|
| `2026-10-11.092000.png` | Как должно выглядеть управление: клавиши 1–5 привязаны к нажатиям на экране (Challenge 3, Location 1, Normal) |
| `2026-10-11.091405.png` | Колода |
| `2026-10-11.091455.png` | Характеристики Аустина |
| `2026-10-11.091515.png` | Характеристики Private Rodriguez |

### Быстрый старт

1. Установите AutoHotkey v2 (см. «Требования»).
2. Настройте раскладку клавиш и колоду, как на скриншотах.
3. Скачайте нужный `.ahk` файл и поместите его в папку **`AutoHotkey` внутри «Документов»** (`Документы\AutoHotkey`, она появляется после установки AutoHotkey). Это просто удобное место, чтобы хранить все скрипты вместе. Если такой папки нет, создайте её сами или возьмите любую другую, потому что скрипт работает из любой папки.
4. Запустите скрипт двойным кликом. В левом верхнем углу появится окошко «Скрипт на ПАУЗЕ».
5. Начните миссию и **в тот же момент** нажмите **F1**. Прозвучит высокий сигнал, а в окошке будет «Скрипт ЗАПУЩЕН».
6. **F1** ещё раз — пауза. После паузы таймеры начинаются с нуля, поэтому возобновляйте только с началом новой миссии. Чтобы закрыть скрипт, щёлкните правой кнопкой по его значку в трее → Exit.

### Как это работает

1. **F1** запускает скрипт (высокий сигнал, окошко в левом верхнем углу).
2. **Подготовка (~10 с):** ничего не нажимается. Затем клавиша `5` один раз выпускает Private Rodriguez, чтобы он набрал ярость для Аустина.
3. **Закликивание:** клавиша `1` нажимает слот Аустина каждые ~80 мс. Каждая клавиша удерживается 40 мс, чтобы игра надёжно её засчитывала.
4. **Конец каждого цикла:** закликивание прекращается, и скрипт нажимает `2` → `3` → `4` с паузой 0,5 с: Пауза → Retry → запасное нажатие.
5. Снова шаг 2, и так по кругу. В окошке виден отсчёт до следующего перезапуска.

### Настройки (в начале каждого файла)

| Параметр | По умолчанию | Что делает |
|---|---|---|
| `cycleInterval` | 200000 / 1250000 | Время между перезапусками, мс |
| `prepDelay` | 10000 | Ожидание перед нажатием `5`, мс |
| `repeatPrep` | true | Повторять подготовку после каждого перезапуска |
| `startWith23` | false | true = перезапуск сразу по F1, а не через полный цикл |
| `spamDelay` | 80 | Пауза между нажатиями `1`, мс |
| `holdTime` | 40 | Сколько мс удерживается каждая клавиша |

Остальные параметры (`keyGap`, `startOnLaunch`, `popupX`/`popupY`) описаны в комментариях в начале каждого файла.

### Советы

- Окно игры должно оставаться активным, потому что скрипт отправляет клавиши в активное окно.
- Если игра не реагирует на клавиши, попробуйте запустить скрипт от имени администратора.
- Файлы сохранены в UTF-8 с BOM. Если будете править RU-файл, сохраняйте в той же кодировке, иначе русский текст в окошке может превратиться в «кракозябры».

Используйте на свой риск: автоматизация нажатий может нарушать правила игры. Неофициальный фанатский инструмент, не связан с разработчиками игры.
