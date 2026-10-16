# HSK Multiplayer — релизы

Здесь лежат только собранные версии мода. Исходники не публикуются.

**Скачать:** вкладка [Releases](../../releases) — берите архив из самого верхнего выпуска.

## Что это

Онлайн-слой для сборки Hardcore SK: своё меню входа, лобби со списком игроков и выбором роли —
хост создаёт мир и держит сервер, наёмник приходит в уже начатый.

Вместе с этим мод чинит рассинхрон, из-за которого игра вдвоём на HSK разъезжалась при входе
в сессию: `Verse.Rand` держит состояние в статических полях, и фоновый поток, который грузит карту,
тратил числа из того же потока, которым главный считает симуляцию. Фоновым потокам выдаётся свой
поток чисел, главный не затронут. Отдельно синхронизируются действия `CE Quick Loadout`, которых нет
в MP Compat.

## Что нужно

| | |
|---|---|
| RimWorld | 1.6 |
| [Harmony](https://steamcommunity.com/sharedfiles/filedetails/?id=2009463077) | обязательно |
| [Multiplayer](https://steamcommunity.com/sharedfiles/filedetails/?id=2606448745) | для онлайна; без него работают только исправления рассинхрона |

Для входа в онлайн нужен сервер авторизации HSK Online. В сборке адрес по умолчанию —
`http://127.0.0.1:5080`, то есть локальный; поменять можно в настройках мода.

## Установка

1. Скачайте архив из [Releases](../../releases).
2. Распакуйте так, чтобы папка `HSKMultiplayer` оказалась в `RimWorld/Mods`.
3. Включите мод в списке и перезапустите игру.

**У всех игроков должен стоять одинаковый набор модов.** Сервер сверяет хеши и не пустит в онлайн
того, у кого набор отличается.

## Лицензия

Все права защищены, см. [LICENSE](LICENSE). Пользоваться можно; перезаливать, распространять,
включать в сборки и публиковать производные — только с разрешения автора.

---

# HSK Multiplayer — releases

Built versions only. The source is not published here.

**Download:** the [Releases](../../releases) tab — take the archive from the topmost entry.

## What it is

An online layer for the Hardcore SK modpack: its own sign-in window and a lobby that lists who is
online and offers a role — a host makes the world and runs the server, a mercenary walks into one
already under way.

It also fixes the desync that pulled a two-player HSK session apart on join. `Verse.Rand` keeps its
state in static fields, so the background thread that loads the map was spending numbers from the
same stream the main thread runs the simulation on. Background threads now get their own stream and
the main thread is untouched. `CE Quick Loadout`'s actions, which MP Compat does not cover, are
synced separately.

## Requirements

| | |
|---|---|
| RimWorld | 1.6 |
| [Harmony](https://steamcommunity.com/sharedfiles/filedetails/?id=2009463077) | required |
| [Multiplayer](https://steamcommunity.com/sharedfiles/filedetails/?id=2606448745) | for the online part; without it only the desync fixes apply |

Signing in needs an HSK Online authentication server. The shipped default is
`http://127.0.0.1:5080`, i.e. local — change it in the mod settings.

## Installing

1. Download the archive from [Releases](../../releases).
2. Unpack it so that the `HSKMultiplayer` folder lands in `RimWorld/Mods`.
3. Enable the mod in the list and restart the game.

**Every player needs the same set of mods.** The server compares hashes and refuses online access to
anyone whose set differs.

## License

All rights reserved, see [LICENSE](LICENSE). Use is fine; re-uploading, redistributing, bundling it
or publishing derivatives needs the author's permission.
