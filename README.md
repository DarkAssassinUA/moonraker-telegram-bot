# moonraker-telegram-bot (Reworked Edition)

![image](https://user-images.githubusercontent.com/51682059/140623765-3b839b4b-40c2-4f87-8969-6cb609f2c5f1.png)

[English](#english) | [Русский](#русский)

---

<a name="english"></a>
## English

The general idea of this project is to provide you with a way to control and monitor your printer without having to setup a VPN, opening your home network, or doing any sort of other network-related voodoo.
In addition, you get the benefits of push-style notifications always in your pocket, and a bandwidth-friendly way to check up on your print progress, when not near the printer.

> [!WARNING]
> As always with solutions like these, we kindly remind you not to print unattended, and always to take all necessary precautions against fire hazards.

---

### 🌟 Features & Differences from the Original Bot
This fork is a heavily reworked version of the original `nlef/moonraker-telegram-bot`, introducing a brand new interactive UI, power management, and chat-cleanliness features:

*   **Interactive Control Menu (`/menu` or `/start`)**: A complete inline-keyboard-driven control dashboard.
    *   📊 **Real-time Status**: Displays current printer state, temperatures, and connection state.
    *   📂 **G-code Browser**: Navigate your upload directory and start prints directly from Telegram.
    *   🤖 **Paginated Macros List**: Lists all G-code macros configured in Klipper with pagination (`Back` / `Next` buttons). No more typing command names manually!
    *   🔌 **Power & 💡 Light Control**: Dedicated buttons to turn on/off smart plugs (PSU) and toggle lights configured in your Moonraker config.
    *   ⏸️ / ▶️ / ⏹️ **Print Controls**: Instantly pause, resume, or cancel prints.
    *   🛠️ **Service Control**: Restart the bot or Klipper firmware directly from the interface.
    *   ⚙️ **System Actions**: Reboot or safely shut down the host machine (e.g. Raspberry Pi / Orange Pi).
*   **Auto-Updating Menu State**: The menu automatically refreshes the status and IP address every 10 seconds to show up-to-date print stats.
*   **Automatic Greeting Deletion**: Keeps the Telegram chat clean by deleting connection greeting messages once Klippy successfully connects.

#### 📊 Comparison Table

| Feature | Original Bot (`nlef`) | This Reworked Fork |
| :--- | :--- | :--- |
| **G-code Execution** | Raw text command input | Raw input + Interactive Paginated Macros list |
| **Print Management** | Chat commands only | Direct Pause, Resume, Cancel buttons |
| **Smart Plugs & Light** | Configuration dependent | Dedicated visual buttons with state toggles |
| **System Operations** | Not supported | Reboot host, Shut down host, Restart firmware, Restart bot |
| **Menu Interface** | Simple list | Multi-level inline keyboard menu |
| **Real-time Refresh** | Manual commands only | Periodic automatic menu refreshing (10s interval) |
| **Chat Cleanliness** | Retains all system greetings | Automatically removes obsolete greetings on connection |

---

### ⚙️ One-Click Installation

To clone the repository and run the interactive installation script on your host, run this single command in your terminal:

```bash
cd ~ && git clone https://github.com/DarkAssassinUA/moonraker-telegram-bot.git && ./moonraker-telegram-bot/scripts/install.sh
```

During installation, the script will guide you through:
1. Selecting the path for the configuration directory (recommended to keep together with Klipper config).
2. Setting the number of printer instances (for multi-printer setups).
3. Automatically installing system dependencies and setting up the systemd service.

---

<a name="русский"></a>
## Русский

Основная идея проекта — предоставить способ управления и мониторинга 3D-принтера без необходимости настраивать VPN, открывать порты в домашней сети или заниматься другими сложными сетевыми настройками.
Вы получаете мгновенные push-уведомления и экономичный способ проверки прогресса печати, когда находитесь вдали от принтера.

> [!WARNING]
> Пожалуйста, не оставляйте принтер во время печати без присмотра и соблюдайте все меры пожарной безопасности.

---

### 🌟 Возможности и отличия от оригинального бота
Этот форк является переработанной версией оригинального бота `nlef/moonraker-telegram-bot`, предлагающей новый интерактивный UI, управление питанием и инструменты поддержания чистоты чата:

*   **Интерактивное меню управления (`/menu` или `/start`)**: Полноценный пульт управления на инлайн-кнопках в Telegram.
    *   📊 **Статус в реальном времени**: Отображает состояние принтера, температуры и готовность.
    *   📂 **Файловый менеджер**: Позволяет просматривать список загруженных G-code файлов и запускать печать.
    *   🤖 **Интерактивные макросы**: Выводит список всех G-code макросов принтера с кнопками пагинации (перелистывания страниц). Больше не нужно вводить имена макросов вручную!
    *   🔌 **Питание и 💡 Свет**: Быстрое включение/выключение управляемых розеток (PSU) и подсветки принтера, настроенных в Moonraker.
    *   ⏸️ / ▶️ / ⏹️ **Управление печатью**: Быстрый доступ к кнопкам паузы, продолжения и отмены печати.
    *   🛠️ **Управление службами**: Возможность перезапустить прошивку Klipper или службу самого бота.
    *   ⚙️ **Системные команды хоста**: Безопасное выключение или перезагрузка одноплатного компьютера (Raspberry Pi / Orange Pi).
*   **Автообновление статуса**: Текст меню автоматически обновляет IP-адрес и текущее состояние печати каждые 10 секунд.
*   **Удаление приветствий**: Бот автоматически удаляет устаревшие приветственные сообщения при подключении к Klipper, сохраняя историю чата чистой.

#### 📊 Таблица сравнения функций

| Функция | Оригинальный бот (`nlef`) | Этот переработанный форк |
| :--- | :--- | :--- |
| **Выполнение G-кода** | Только текстовый ввод | Текстовый ввод + интерактивный постраничный список макросов |
| **Управление печатью** | Только текстовые команды | Кнопки «Пауза», «Продолжить», «Отмена» на экране |
| **Питание и свет** | Зависит от конфигурации | Отдельное меню управления питанием розеток и подсветки |
| **Системные действия** | Не поддерживаются | Перезапуск хоста, выключение хоста, рестарт прошивки и бота |
| **Интерфейс меню** | Простой список кнопок | Многоуровневое меню на инлайн-кнопках |
| **Автообновление меню** | Отсутствует | Автоматическое обновление раз в 10 секунд |
| **Чистота чата** | Сохраняет все приветствия | Автоматически стирает приветствия после коннекта |

---

### ⚙️ Установка в один клик

Чтобы клонировать репозиторий и запустить интерактивный скрипт установки на хосте принтера, выполните одну команду в терминале:

```bash
cd ~ && git clone https://github.com/DarkAssassinUA/moonraker-telegram-bot.git && ./moonraker-telegram-bot/scripts/install.sh
```

В процессе установки скрипт предложит:
1. Выбрать путь для конфигурационного файла (рекомендуется хранить в папке с конфигурацией Klipper).
2. Задать количество инстансов (для ферм или систем с несколькими принтерами).
3. Автоматически установит зависимости и настроит службу в systemd.

---

### Happy Printing!
[![Donate](https://img.shields.io/badge/Donate-PayPal-green.svg)](https://www.paypal.com/donate/?hosted_button_id=KCKKK5WLXNEFE)

---

**Klipper** by [KevinOConnor](https://github.com/KevinOConnor) :
https://github.com/KevinOConnor/klipper

---
**Moonraker** by [Arksine](https://github.com/Arksine) :
https://github.com/Arksine/moonraker

---
**KIAUH - Klipper Installation And Update Helper** by [th33xitus](https://github.com/th33xitus) :
https://github.com/th33xitus/KIAUH

---
**Mainsail Webinterface** by [meteyou](https://github.com/meteyou) :
https://github.com/meteyou/mainsail

---
**Fluidd Webinterface** by [cadriel](https://github.com/cadriel) :
https://github.com/cadriel/fluidd
