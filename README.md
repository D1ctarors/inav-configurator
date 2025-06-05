# INAV Configurator Mod

![Prev](https://github.com/user-attachments/assets/1d308bf2-8e15-4976-9a2a-907771421514)

INAV Configurator Mod — это модифицированный кроссплатформенный инструмент конфигурации, созданный на основе [INAV Configurator](https://github.com/iNavFlight/inav-configurator) для системы управления полётом [INAV](https://github.com/iNavFlight/inav).

Он работает как приложение внутри Google Chrome и позволяет настраивать прошивку INAV на любом поддерживаемом контроллере.

Программа поддерживает различные типы летательных аппаратов, такие как квадрокоптеры, гексакоптеры, октокоптеры и самолёты.

## ✨ Основные изменения мода

### 🌐 Локализация

-   Добавлена поддержка Русского языка

### 🎨 Интерфейс

-   Расширен сайдбар
-   Обновлён логотип
-   Изменена вёрстка и стили

## Windows

1. Перейдите на [страницу релизов](https://github.com/D1ctarors/inav-configurator/releases)
2. Скачайте конфигуратор для Windows (доступны win32 и win64)
3. Распакуйте ZIP-архив
4. Запустите приложение INAV Configurator из распакованной папки
5. Конфигуратор не подписан, поэтому Windows может запросить разрешение на запуск неподписанных приложений при первом запуске

Или:

1. Перейдите на [страницу релизов](https://github.com/D1ctarors/inav-configurator/releases)
2. Скачайте установщик `INAV-Configurator_win64_X.X.X.exe`

## Сборка и запуск INAV Configurator локально (для разработки)

Для локальной разработки используется система сборки **node.js**.

1. Установите [node.js](https://nodejs.org/en)
2. В корне проекта выполните команды:

```bash
yarn install
npm install
```

3. Чтобы собрать JS и CSS и запустить конфигуратор:

-   Через NW.js:

```bash
npm start
```

## Сборка установщика для Windows

Чтобы собрать установочный файл для Windows, необходимо установить [WiX Toolset V3](https://github.com/wixtoolset/wix3/releases) и добавить папку `bin` в переменную окружения `PATH`, например:  
`C:\Program Files (x86)\WiX Toolset v3.14\bin`

## Сборка deb и rpm пакетов для Linux

Для сборки пакетов deb и rpm в Linux необходимо установить следующие зависимости:

-   **Ubuntu/Debian**: `dpkg, fakeroot, rpm, build-essential, libudev-dev`
-   **OpenSuse/Fedora**: `dpkg, fakeroot, rpmbuild, systemd-devel, devel-basis (zypper install -t pattern devel_basis), zip`

Пример запуска сборки (обратите внимание на двойной `--`):  
`npm run make -- --arch="x64"`

---

### Запуск в режиме Отладки | Инспектор

Чтобы открыть Инспектор, установите переменную окружения `NODE_ENV` в значение `development`, либо укажите этот флаг при запуске `npm start`:

```bash
NODE_ENV=development npm start
```

или для Windows PowerShell:

```bash
$env:NODE_ENV="development" | npm start
```

Либо используйте VS Code и запустите отладочную сессию `Debug Configurator` (просто нажмите F5).

## Кастомизация шрифтов

INAV предоставляет изображения шрифтов, чтобы вы могли создать собственные стили — аналоговые и цифровые. Ресурсы находятся в [osd](/resources/osd). Внутри папок **analogue** и **digital** находятся инструкции по созданию. Также доступна [Карта символов INAV](/resources/osd/INAV%20Character%20Map.md) с визуализацией и переменными.

Инструменты сборки:

-   [Аналоговых](https://github.com/fiam/max7456tool)
-   [Цифровых](https://github.com/MrD-RC/hdosd-font-tool)

Новые шрифты можно отправлять через pull request.

## Примечания

### WebGL

Убедитесь, что в настройках Chrome включена опция:

**Настройки → Система → Использовать аппаратное ускорение (если доступно)**
