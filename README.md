# Frame-Clicker

**[English](#english) · [Русский](#русский)**

A lightweight, free browser-based tool for inspecting local videos frame by frame. **No installation, video uploads, or external libraries required.**

**[▶ Open Frame-Clicker online](https://v1titan.github.io/Frame-Clicker/)** · **[⬇ Download for offline use (Releases)](https://github.com/V1Titan/Frame-Clicker/releases/latest)**

The interface is available in **English and Russian**. Select `EN` or `RU` in the upper-right corner. The default follows your browser language; the app remembers your choice when browser storage is available.

---

## English

### How to start

**Option 1 — Online (recommended):** Open **[Frame-Clicker on GitHub Pages](https://v1titan.github.io/Frame-Clicker/)**. No download needed.

**Option 2 — Offline:**

1. Open **[the latest Release](https://github.com/V1Titan/Frame-Clicker/releases/latest)**.
2. Expand **Assets** and download **`Frame-Clicker.html`** (the standalone HTML file, **not** “Source code (zip)”).
3. Double-click the downloaded HTML file to open it in a modern browser. It works without an internet connection.

**Option 3 — Entire source repository:** On the [repository page](https://github.com/V1Titan/Frame-Clicker), choose **Code → Download ZIP**, extract it, and open `index.html`. This option is intended for those who want the source files.

### Using the viewer

1. Click **Open video** or drag a video into the viewer.
2. Use **← Previous** / **Next →**, the keyboard arrow keys, or the slider to navigate by requested frame positions.
3. The counter displays the requested frame number, estimated total frame count, and video timestamp.
4. If FPS detection fails or you want to override it, enter a value (e.g. `30`, `60`, `120`, or `240`) into **Manual FPS** and click **Apply**.
5. Click **Restore auto** to use the automatically detected FPS again, when available.

### Features

- Automatic frame-rate detection using timing metadata from supported MP4/MOV files.
- Frame-by-frame seeking with buttons, keyboard shortcuts, and slider.
- Support for variable frame rate (VFR) timing metadata when available; VFR FPS is shown as an average.
- Manual FPS override and restoration of automatic timing.
- Local drag-and-drop video playback; one HTML file and no third-party dependencies.
- English and Russian interface with a language switch.

### Important limitations

- **Exact decoded-frame accuracy is not guaranteed.** The tool seeks using the browser's video timestamp API. Some codecs, recordings, and browsers may repeat or skip displayed frames. **The counter shows a requested position, not a verified decoded-frame number.**
- FPS detection may not work with all formats or file structures. You can enter FPS manually; that assumes evenly spaced frame times even for VFR recordings.
- Use the FPS of the **saved video file**, which may differ from the camera's capture rate. Manually changing FPS here does not add frames to the file.
- Video playback and codec support depend on the browser.
- This is a frame-inspection viewer, not an automated input-lag measurement system.

### Privacy and technology

Videos are processed locally in your browser; the application does not upload them to a server. Built with HTML, CSS, vanilla JavaScript, HTML5 Video and Canvas.

Licensed under the [MIT License](./LICENSE).

---

## Русский

**Frame-Clicker** — бесплатный инструмент для покадрового просмотра видео в браузере. Ничего устанавливать и загружать на сервер не нужно.

### Как запустить

**Вариант 1 — Онлайн (рекомендуется):** откройте **[Frame-Clicker на GitHub Pages](https://v1titan.github.io/Frame-Clicker/)**. Скачивать ничего не нужно.

**Вариант 2 — Без интернета:**

1. Перейдите в **[последний релиз (Releases)](https://github.com/V1Titan/Frame-Clicker/releases/latest)**.
2. Раскройте **Assets** и скачайте **`Frame-Clicker.html`** (сам HTML-файл, **не** архив «Source code (zip)»).
3. Откройте скачанный HTML-файл двойным щелчком в браузере. Подключение к интернету не требуется.

**Вариант 3 — Исходники проекта:** на [странице репозитория](https://github.com/V1Titan/Frame-Clicker) нажмите **Code → Download ZIP**, распакуйте архив и откройте `index.html`. Это вариант для тех, кому нужен весь исходный код.

### Как пользоваться

1. Нажмите **«Открыть видео»** или перетащите видео в окно приложения.
2. Переключайте позиции кнопками **«← Назад»** / **«Вперёд →»**, стрелками на клавиатуре или ползунком.
3. Счётчик показывает номер запрошенного кадра, оценку общего количества кадров и время в видео.
4. Если FPS не определился или его нужно изменить, введите `30`, `60`, `120`, `240` или другое значение в поле **«FPS вручную»** и нажмите **«Применить»**.
5. Для возврата к автоматически определённому FPS нажмите **«Вернуть авто»** (если автоматическое определение удалось).
6. Чтобы переключить интерфейс, выберите **RU** или **EN** в правом верхнем углу.

### Возможности

- Определение FPS по временным меткам поддерживаемых MP4/MOV-файлов.
- Переход по расчётным кадрам кнопками, клавиатурой и ползунком.
- Частичная поддержка видео с переменным FPS (VFR): используются временные метки, когда они доступны; FPS отображается как среднее значение.
- Ручной ввод FPS с возможностью вернуться к автоматическому режиму.
- Перетаскивание видео в окно; всё приложение — один HTML-файл без библиотек.
- Русский и английский интерфейс.

### Ограничения — важно прочитать

- **Точность отображаемого кадра не гарантируется.** Переход выполняется по временным меткам через браузерный видеоплеер. Отдельные кадры могут повторяться или пропускаться. **Номер в счётчике — запрошенная позиция, а не проверенный номер декодированного кадра.**
- Автоматическое определение FPS работает не со всеми файлами. Ручной FPS предполагает равные интервалы между кадрами, даже если исходный файл записан с переменной частотой.
- Указывайте FPS **сохранённого файла**, а не обязательно частоту исходной съёмки. Ручной ввод FPS не создаёт дополнительных кадров.
- Если видео не открывается, возможно, браузер не поддерживает формат или кодек.
- Программа не выполняет автоматического измерения input lag.

### Конфиденциальность и технология

Выбранные видео обрабатываются локально в браузере и не отправляются на сервер. Используются HTML, CSS, обычный JavaScript, HTML5 Video и Canvas.

Лицензия — [MIT](./LICENSE).
