# HSK Multiplayer — релизы

Здесь лежат только собранные версии: сборка мода (теги `v*`) и лаунчер (теги `launcher-*`).
Исходники не публикуются.

## Установка: лаунчер

**[Скачать лаунчер — HSKLauncher-0.2.0.zip](../../releases/download/launcher-v0.2.0/HSKLauncher-0.2.0.zip)**

Нужен [.NET 8 Desktop Runtime](https://dotnet.microsoft.com/download/dotnet/8.0/runtime) — без него
не запустится. Дальше:

1. Распакуйте архив в любую свою папку (пять файлов рядом) и запустите `HSKLauncher.exe`.
2. Укажите установленный RimWorld — лаунчер проверит версию и наличие DLC.
3. Нажмите установку и дождитесь конца. После этого играйте **только через лаунчер**.

Что он делает: копирует игру в отдельную папку, ставит туда Hardcore SK по закреплённому коммиту,
аддоны по их коммитам и наш `HSKMultiplayer` из последнего релиза, пишет порядок модов и запускает
игру со своей папкой сохранений.

**Вашу установку Steam он не трогает.** Её можно обновлять и играть в ваниль как раньше — сборка
живёт отдельной копией.

Обновления лаунчер ставит сам: раз в пять минут спрашивает сервер, есть ли версия новее, и
предлагает обновиться. Обновления сборки — тоже он, кнопкой.

## Зачем лаунчер вообще нужен

Сервер сверяет набор модов побайтово и не пустит в онлайн того, у кого он отличается хоть одним
файлом. Официальный лаунчер HSK всегда тянет последний коммит, поэтому двое игроков, обновившихся
с разницей в час, получают разные файлы и вместе играть уже не смогут. Наш ставит **закреплённые
коммиты** из манифеста сервера — у всех выходит один и тот же набор.

## Установка вручную

Так тоже можно, но набор обязан совпасть с эталоном сервера до файла, поэтому порядок строгий.
Актуальные коммиты и теги лежат в манифесте сборки — сервер отдаёт его по пути `/pack`, а его адрес
уже прописан в моде и в лаунчере.

1. **Игра.** RimWorld **1.6** и пять DLC: Royalty, Ideology, Biotech, Anomaly, Odyssey.
   Сделайте копию папки игры — ставить сборку в Steam-установку не стоит.
2. **Сборка Hardcore SK.** Скачайте архив репозитория по SHA из манифеста
   (`https://codeload.github.com/HardcoreSK/Hardcore-SK/zip/<sha>`) и положите **только** содержимое
   его папки `Mods` в `Mods` вашей копии.
3. **Аддоны.** Каждый из списка `addons` манифеста — своим архивом по своему SHA; из архива берётся
   только папка самого мода.
4. **Наш мод.** Возьмите архив из верхнего релиза с тегом `v*` и распакуйте так, чтобы папка
   `HSKMultiplayer` оказалась в `Mods`. В том же архиве едут ещё семь папок, которых нет в сборке, —
   `Multiplayer`, `Multiplayer-Compatibility`, `RimHUD`, `EPrimeReadouts`, `MAZ-UI`, `QualColor`,
   `TraitRarityColors`: их тоже нужно положить рядом.
5. **Порядок модов.** Возьмите `ModsConfig.xml` из репозитория сборки (того же коммита), допишите в
   конец аддоны и `linya.hskmultiplayer`, положите в папку настроек игры.
6. **Запуск** с отдельной папкой сохранений: `RimWorldWin64.exe -savedatafolder=SaveData`.

Если после этого лобби пишет, что моды не совпали, — оно и показывает, какие именно: `missing`,
`extra`, `different`, `switched`.

## Что нужно

| | |
|---|---|
| RimWorld | 1.6 + Royalty, Ideology, Biotech, Anomaly, Odyssey |
| Multiplayer и Multiplayer Compatibility | уже в архиве, отдельно ставить не нужно |
| Prepatcher, HugsLib, Harmony | входят в сборку Hardcore SK |

## Лицензия

Все права защищены, см. [LICENSE](LICENSE). Пользоваться можно; перезаливать, распространять,
включать в сборки и публиковать производные — только с разрешения автора.

---

# HSK Multiplayer — releases

Built versions only: the mod bundle (`v*` tags) and the launcher (`launcher-*` tags). The source is
not published here.

## Install: the launcher

**[Download the launcher — HSKLauncher-0.2.0.zip](../../releases/download/launcher-v0.2.0/HSKLauncher-0.2.0.zip)**

It needs the [.NET 8 Desktop Runtime](https://dotnet.microsoft.com/download/dotnet/8.0/runtime).
Then:

1. Unpack the archive anywhere (five files side by side) and run `HSKLauncher.exe`.
2. Point it at your RimWorld install — it checks the version and the DLCs.
3. Press install and wait. From then on, play through the launcher.

What it does: copies the game into a folder of its own, installs Hardcore SK at a pinned commit, the
add-ons at their pinned commits and our `HSKMultiplayer` from the latest release, writes the mod
order and starts the game with its own save folder.

**Your Steam install is left alone** — the pack lives in a separate copy.

The launcher updates itself: every five minutes it asks the server whether a newer version exists
and offers to update. Pack updates are a button in the same window.

## Why a launcher at all

The server compares mod sets byte for byte and refuses anyone whose set differs by a single file.
The official HSK launcher always pulls the latest commit, so two players who update an hour apart
end up with different files and can no longer play together. Ours installs **pinned commits** from
the server's manifest, so everyone ends up with the same set.

## Installing by hand

Possible, but the set has to match the server's reference exactly, so the order matters. The current
commits and tags live in the pack manifest, which the server serves at `/pack`; its address is
already built into the mod and the launcher.

1. **The game.** RimWorld **1.6** with all five DLCs: Royalty, Ideology, Biotech, Anomaly, Odyssey.
   Copy the game folder — do not install the pack over your Steam copy.
2. **The Hardcore SK pack.** Download the repository archive at the SHA from the manifest
   (`https://codeload.github.com/HardcoreSK/Hardcore-SK/zip/<sha>`) and put **only** the contents of
   its `Mods` folder into your copy's `Mods`.
3. **Add-ons.** Each entry of the manifest's `addons`, from its own archive at its own SHA; take only
   that mod's folder out of each.
4. **This mod.** Take the archive from the topmost `v*` release and unpack it so that
   `HSKMultiplayer` lands in `Mods`. The same archive carries seven more folders the pack does not
   include — `Multiplayer`, `Multiplayer-Compatibility`, `RimHUD`, `EPrimeReadouts`, `MAZ-UI`,
   `QualColor`, `TraitRarityColors` — those go in beside it.
5. **Mod order.** Take `ModsConfig.xml` from the pack repository at the same commit, append the
   add-ons and `linya.hskmultiplayer`, and put it in the game's config folder.
6. **Run** with a save folder of its own: `RimWorldWin64.exe -savedatafolder=SaveData`.

If the lobby then says the mods do not match, it also says which ones: `missing`, `extra`,
`different`, `switched`.

## Requirements

| | |
|---|---|
| RimWorld | 1.6 + Royalty, Ideology, Biotech, Anomaly, Odyssey |
| Multiplayer and Multiplayer Compatibility | already in the archive, no separate install |
| Prepatcher, HugsLib, Harmony | come with the Hardcore SK pack |

## License

All rights reserved, see [LICENSE](LICENSE). Use is fine; re-uploading, redistributing, bundling it
or publishing derivatives needs the author's permission.
