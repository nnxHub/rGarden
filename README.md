# rGarden — Гроу Гарден (Grow Garden) с ReallyWorld [1.21.x]

```
##############################################################################
#██████╗░░██╗░░░░░░░██╗██████╗░██╗░░░░░██╗░░░██╗░██████╗░██╗███╗░░██╗░██████╗#
#██╔══██╗░██║░░██╗░░██║██╔══██╗██║░░░░░██║░░░██║██╔════╝░██║████╗░██║██╔════╝#
#██████╔╝░╚██╗████╗██╔╝██████╔╝██║░░░░░██║░░░██║██║░░██╗░██║██╔██╗██║╚█████╗░#
#██╔══██╗░░████╔═████║░██╔═══╝░██║░░░░░██║░░░██║██║░░╚██╗██║██║╚████║░╚═══██╗#
#██║░░██║░░╚██╔╝░╚██╔╝░██║░░░░░███████╗╚██████╔╝╚██████╔╝██║██║░╚███║██████╔╝#
#╚═╝░░╚═╝░░░╚═╝░░░╚═╝░░╚═╝░░░░░╚══════╝░╚═════╝░░╚═════╝░╚═╝╚═╝░░╚══╝╚═════╝░#
#              Разработано студией RWPlugins                                 #
#               tgc:https://t.me/RWplugins                                   #
##############################################################################
```

[![Telegram](https://img.shields.io/badge/Telegram-RWPlugins-2CA5E0?style=for-the-badge&logo=telegram)](https://t.me/RWplugins)
[![Minecraft Version](https://img.shields.io/badge/Minecraft-1.21.x-brightgreen?style=for-the-badge&logo=minecraft)](https://papermc.io)
[![Release](https://img.shields.io/badge/Release-v1.0.0-blue?style=for-the-badge)](https://github.com/nnxHub/rGarden/releases/latest)
[![Downloads](https://img.shields.io/github/downloads/nnxHub/rGarden/total?style=for-the-badge&logo=github&color=orange&label=%D0%A1%D0%BA%D0%B0%D1%87%D0%B8%D0%B2%D0%B0%D0%BD%D0%B8%D0%B9)](https://github.com/nnxHub/rGarden/releases)

---

## О плагине
**rGarden** — качественный бесплатный аналог механики **Гроу Гардена (Grow Garden)** с сервера **ReallyWorld** для Minecraft **1.21.x** (Paper, Purpur, Gale, Leaf).

Игроки получают опыт за нахождение на сервере (награды за онлайн), повышают уровень сада и забирают случайные ценные призы через удобное GUI меню `/gg`.

> 📢 Все обновления, новые бесплатные плагины и эксклюзивные сливы публикуются в нашем официальном Telegram-канале: **[t.me/RWplugins](https://t.me/RWplugins)**.

---

## Основной функционал
- **Фарм опыта за онлайн**: начисление опыта за каждые N минут игры (по умолчанию 10 минут = +10 опыта).
- **Система уровней**: каждые 60 опыта повышают уровень сада на +1.
- **Интерактивные награды**: меню `/gg` генерирует 3 случайных предмета из пула наград.
- **Внутриигровой GUI редактор**: добавление любых предметов с чарами и NBT командой `/rgarden edit` прямо из инвентаря без редактирования файлов.
- **Поддержка ресурспака ReallyWorld**: в конфигурации уже прописаны оригинальные Юникод-символы для меню и заголовков.
- **Полная кастомизация (White-Label)**: в `config.yml` можно настроить любой префикс сообщений под стиль вашего сервера.

---

## Команды и права

| Команда | Описание | Право |
| :--- | :--- | :--- |
| `/gg` | Открыть меню Гроу Гардена | `rgarden.player` |
| `/rgarden edit` | Открыть GUI редактор пула наград | `rgarden.admin` |
| `/rgarden give <игрок> <кол-во>` | Выдать очки опыта игроку | `rgarden.admin` |
| `/rgarden reset <игрок>` | Сбросить прогресс опыта игрока | `rgarden.admin` |
| `/rgarden reload` | Перезагрузить конфиг и базу наград | `rgarden.admin` |

---

## Конфигурация (config.yml)

```yaml
prefix: "&b&lRWPlugins &8» &f"
garden-name: "&6&lГроу-Гарден"

# Юникод-символы под текстуры ReallyWorld
menu-title: "§fꈁꀀꈂꍉꈂꀁ§0ꈃꄥ&r"
rewards-menu-title: "§fꈁꀀꈂꌗꈂꀁ§0ꈃꄥ&r"

barrier-item:
  name: "&cЗаблокировано"
  lore:
    - "&7Награда откроется с 1 уровня"

messages:
  noPermissionUser: "{prefix}&cДля открытия необходима привилегия &2&lИгрок"
  noPermissionAdmin: "{prefix}&cНедостаточно прав (rgarden.admin)."
  onlyPlayer: "{prefix}&cКоманда только для игроков."
  reloaded: "{prefix}&aКонфигурация и награды успешно перезагружены!"
  gaveXp: "{prefix}&aВыдано &f{amount}&a опыта игроку &f{player}&a."
  gotXp: "{prefix}&fПолучен опыт: &e{amount}"
  rewardTaken: "{prefix}&aВы забрали награду!"
  notEnoughLevel: "{prefix}&cНедостаточный уровень для получения наград."
  editorSaved: "{prefix}&aНаграды сохранены в rewards.yml: &f{count}"
  badNumber: "{prefix}&cНекорректное число."
  playerNotFound: "{prefix}&cИгрок не найден."
  usage: "{prefix}&cИспользование: /rgarden <edit|give|reset|reload>"
```

---

## Установка
1. Скачайте **[rGarden.jar](https://github.com/nnxHub/rGarden/releases/latest/download/rGarden.jar)**.
2. Поместите файл в папку `plugins/` вашего сервера (Paper / Purpur 1.21.x).
3. Перезапустите сервер или используйте PlugMan / FastReload.
4. Откройте редактор `/rgarden edit` и положите нужные призы.
