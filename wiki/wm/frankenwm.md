---
layout: default
title: Ctlos Linux FrankenWm
description: Описание конфигурации Ctlos Linux FrankenWm, горячие клавиши, утилиты.
menus:
  wm:
    title: FrankenWm
    weight: 2
---

> Текущий релиз 0.1.0

Исходники: [frankenwm v0.1.0](https://github.com/ctlos/ctlosiso/tree/v0.1.0-frankenwm).

![FrankenWm](/wiki/images/wm/frankenwm010.png)

## Скачать iso образ

- Скачать [Ctlos FrankenWm](/get)

Установка: `super+d` rofi, набрать `calamares` Enter.

> Рекомендации после установки [next-install](/wiki/install/next-install/).

## Конфигурационные файлы

Путь                             | Описание
--- | ---
~/.config/frankenwm/src/config.h | Основной конфиг.
~/.config/frankenwm/autostart    | Скрипт автостарта.
~/.config/polybar/               | Конфиг и скрипты.

> Данный `wm` необходимо перекомпилировать после изменения `config.h`.

```bash
cd ~/.config/frankenwm/src
sudo make clean install
```

Необходим restart(выйти и зайти) `killall frankenwm`.

> Изучите [оффициальный man](https://github.com/sulami/frankenwm/blob/master/frankenwm.1).

## Панели

- Верхний бар, polybar
- Нижний бар - трей, tint2

## Горячие клавиши

Конфиг `~/.config/polybar/src/config.h`.

- MOD4: Super/Windows
- MOD1: Alt
- XK_: воспринимайте как префикс, а дальше уже кнопка

## Режимы и управление окнами

Секция переключения режимов.

```c
/* mode selection */
{  MOD4|SHIFT,       XK_t,          switch_mode,       {.i = TILE}},
{  MOD4|SHIFT,       XK_m,          switch_mode,       {.i = MONOCLE}},
{  MOD4|SHIFT,       XK_b,          switch_mode,       {.i = BSTACK}},
{  MOD4|SHIFT,       XK_g,          switch_mode,       {.i = GRID}},
{  MOD4|SHIFT,       XK_f,          switch_mode,       {.i = FIBONACCI}},
{  MOD4|SHIFT,       XK_d,          switch_mode,       {.i = DUALSTACK}},
{  MOD4|SHIFT,       XK_e,          switch_mode,       {.i = EQUAL}},
```

Ключ            | Описание
--- | ---
`super+shift+t` | TILE: тайлинг режим.
`super+shift+m` | MONOCLE: окно развернуто.
`super+shift+b` | BSTACK: нижний стек.
`super+shift+g` | GRID: режим сетки.
`super+shift+f` | FIBONACCI: режим фибоначи(золотое сечение), как в Bspwm.
`super+shift+d` | DUALSTACK: двойной стек.
`super+shift+e` | EQUAL: ровное деление.

Зажатая `Super(win)` и клавиши мыши манипулируют окнами: резмер, положение. В плавающем режиме.

## Запуск утилит

Ключ                   | Описание
--- | ---
`alt + shift`          | Переключение раскладки(us,ru).
`super+shift+Enter`    | Terminal urxvt.
`super+r `             | Rofi - меню(лаунчер).
`super+q `             | Закрыть окно.

Комментарии приветствуются. Вступай в telegram чат: [t.me/ctlos](https://t.me/ctlos).