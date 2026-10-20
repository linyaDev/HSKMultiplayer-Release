# HSK Online Launcher — релизы

## Установка: лаунчер

**[Скачать лаунчер](../../releases/latest)**

Нужен [.NET 8 Desktop Runtime](https://dotnet.microsoft.com/download/dotnet/8.0/runtime) — без него
не запустится. Дальше:

1. Распакуйте архив в любую свою папку (пять файлов рядом) и запустите `HSKOnlineLauncher.exe`.
2. Укажите установленный RimWorld — лаунчер проверит версию и наличие DLC.
3. Нажмите установку и дождитесь конца. После этого играйте **только через лаунчер**.

Что он делает: копирует игру в отдельную папку, ставит туда Hardcore SK по закреплённому коммиту,
аддоны по их коммитам и наш `HSKMultiplayer` из последнего релиза, пишет порядок модов и запускает
игру со своей папкой сохранений.

**Вашу установку Steam он не трогает.** Её можно обновлять и играть в ваниль как раньше — сборка
живёт отдельной копией.

Раз в пять минут лаунчер сам проверяет, есть ли версия новее, и предлагает обновиться. Обновления
сборки — тоже он, кнопкой.

## Установка вручную

1. **Игра.** RimWorld **1.6** и пять DLC: Royalty, Ideology, Biotech, Anomaly, Odyssey.
   Рекомендуем сделать копию папки игры, а не ставить сборку поверх своей Steam-установки.
2. **Сборка Hardcore SK.** Скачайте архив репозитория:
   [https://github.com/HardcoreSK/Hardcore-SK/archive/98106a39b9eb055952e9163f2836c8f58c68e5e7.zip](https://github.com/HardcoreSK/Hardcore-SK/archive/98106a39b9eb055952e9163f2836c8f58c68e5e7.zip)
   и положите **только** содержимое его папки `Mods` в `Mods` вашей копии.
3. **Этот мод.** [Скачайте последний релиз](https://github.com/linyaDev/HSKOnlain-Release/releases/latest)
   из отдельного репозитория `HSKOnlain-Release` и распакуйте архив прямо в `Mods`.
4. **Порядок модов.** `ModsConfig.xml` уже лежит готовым прямо в архиве этого мода
   (`HSKMultiplayer/ModsConfig.xml`). Просто скопируйте его в папку настроек игры —
   дописывать ничего не нужно.
5. **Настройки модов (необязательно).** Скопируйте содержимое
   `HSKMultiplayer/Settings/Config/` из того же архива в `SaveData/Config/` вашей копии.
6. **Запуск** с отдельной папкой сохранений: `RimWorldWin64.exe -savedatafolder=SaveData`.

Если после этого лобби пишет, что моды не совпали, — оно и показывает, какие именно: `missing`,
`extra`, `different`, `switched`.

## Лицензия

Все права защищены, см. [LICENSE](LICENSE). Пользоваться можно; изменять, перезаливать,
распространять, включать в сборки и публиковать производные — только с разрешения автора.

---

# HSK Online Launcher — releases

## Install: the launcher

**[Download the launcher](../../releases/latest)**

It needs the [.NET 8 Desktop Runtime](https://dotnet.microsoft.com/download/dotnet/8.0/runtime).
Then:

1. Unpack the archive anywhere (five files side by side) and run `HSKOnlineLauncher.exe`.
2. Point it at your RimWorld install — it checks the version and the DLCs.
3. Press install and wait. From then on, play through the launcher.

What it does: copies the game into a folder of its own, installs Hardcore SK at a pinned commit, the
add-ons at their pinned commits and our `HSKMultiplayer` from the latest release, writes the mod
order and starts the game with its own save folder.

**Your Steam install is left alone** — the pack lives in a separate copy.

Every five minutes the launcher checks on its own whether a newer version exists and offers to
update. Pack updates are a button in the same window.

## Installing by hand

1. **The game.** RimWorld **1.6** with all five DLCs: Royalty, Ideology, Biotech, Anomaly, Odyssey.
   We recommend copying the game folder rather than installing the pack over your Steam copy.
2. **The Hardcore SK pack.** Download the repository archive:
   [https://github.com/HardcoreSK/Hardcore-SK/archive/98106a39b9eb055952e9163f2836c8f58c68e5e7.zip](https://github.com/HardcoreSK/Hardcore-SK/archive/98106a39b9eb055952e9163f2836c8f58c68e5e7.zip)
   and put **only** the contents of its `Mods` folder into your copy's `Mods`.
3. **This mod.** [Download the latest release](https://github.com/linyaDev/HSKOnlain-Release/releases/latest)
   from the separate `HSKOnlain-Release` repo and unpack the archive straight into `Mods`.
4. **Mod order.** `ModsConfig.xml` already comes ready-made inside this mod's own archive
   (`HSKMultiplayer/ModsConfig.xml`). Just copy it into the game's config folder - nothing
   to append.
5. **Mod settings (optional).** Copy the contents of `HSKMultiplayer/Settings/Config/` from the
   same archive into your copy's `SaveData/Config/`.
6. **Run** with a save folder of its own: `RimWorldWin64.exe -savedatafolder=SaveData`.

If the lobby then says the mods do not match, it also says which ones: `missing`, `extra`,
`different`, `switched`.

## License

All rights reserved, see [LICENSE](LICENSE). Use is fine; modifying, re-uploading, redistributing,
bundling it or publishing derivatives needs the author's permission.
