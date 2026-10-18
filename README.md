# Frame-Clicker

[English instructions](#getting-started) · [Инструкция на русском](#инструкция-на-русском)

**A lightweight, browser-based video frame viewer. No installation, dependencies, or uploads required.**

Frame-Clicker lets you inspect a local video one frame at a time, see its frame number, and navigate through the recording. It attempts to detect the video’s frame rate (FPS) automatically and also lets you set the FPS manually.

## Features

- **Automatic FPS detection** from timing metadata in supported MP4/MOV files.
- **Frame-by-frame navigation** using the Previous / Next buttons or the `←` / `→` arrow keys.
- **Frame slider** for jumping to a specific position in the video.
- **Frame counter** showing the current frame number and estimated total, plus a timestamp.
- **Variable frame rate (VFR) support:** uses sample timing information when available; the displayed FPS is an average for VFR video.
- **Manual FPS override at any time,** even when automatic detection works. Use the restore-auto button to return to the detected rate when available.
- **Drag and drop** to open video files.
- **Single-file application:** plain HTML, CSS, and JavaScript. No build step or third-party libraries.

## Getting started

1. Download [`index.html`](./index.html).
2. Open it in a modern browser.
3. Click **Открыть видео** (Open video), or drag a video file into the window.
4. Use the buttons, arrow keys, or slider to navigate.
5. To override the frame rate, enter a value such as `240` in the manual FPS field and click **Применить** (Apply). Click **Вернуть авто** (Restore auto) to switch back to the detected rate, if available.

The application works locally and does not need an internet connection.

## How FPS detection works

Frame-Clicker reads timing metadata from supported MP4/MOV video tracks, including the `mdhd` media timescale and the `stts` sample timing table. For some variable-frame-rate files, it builds a frame timestamp sequence, accounting for `ctts` composition offsets when available and applicable.

When you enter FPS manually, the application estimates the total number of frames using the video duration and the rate you provided. Manual mode uses evenly spaced frame times, even for VFR video. Restoring automatic mode brings back the available metadata-based timing information.

## Limitations

- **Frame-accurate decoding is not guaranteed.** Frame-Clicker seeks to calculated timestamps via the browser's `HTMLMediaElement.currentTime` API. Depending on the video, codec, and browser, the displayed frame might not exactly match the frame number shown; frames may be repeated or skipped. The frame counter indicates the **requested frame**, not a verified decoded-frame index.
- **Codec support depends on your browser.** A `.mp4` extension alone does not guarantee playback.
- **FPS detection is not universal.** Unsupported formats or file structures may require manual FPS entry.
- **For VFR video, the displayed FPS is an average,** not a constant rate between frames.
- This is a manual video inspection tool, not an automatic input-lag measurement system.

## Privacy

Selected video files are processed locally in the browser. The application code does not upload the video to a server.

## Optional: Publish with GitHub Pages

To let others use Frame-Clicker through a link:

1. Upload `index.html`, `README.md`, and `LICENSE` to the root of a public GitHub repository.
2. Open **Settings → Pages**.
3. Under **Build and deployment**, select **Deploy from a branch**, choose `main`, and set the folder to `/ (root)`.
4. Save your settings and use the URL provided by GitHub Pages.

## Tech stack

HTML · CSS · Vanilla JavaScript · HTML5 Video · Canvas

## License

Distributed under the [MIT License](./LICENSE).


---

## Инструкция на русском

**Frame-Clicker** — простой инструмент для покадрового просмотра видео прямо в браузере. Устанавливать программы и загружать видео на сервер не требуется.

### Как запустить

1. Скачайте файл [`index.html`](./index.html) из репозитория.
2. Откройте его двойным щелчком в браузере (например, Chrome или Edge).
3. Нажмите **«Открыть видео»** и выберите запись. Также файл можно перетащить в окно приложения.
4. Подождите, пока браузер откроет видео, а программа попробует определить FPS.

### Как переключать кадры

- Нажимайте **«← Назад»** или **«Вперёд →»** для перехода на один расчётный кадр.
- Используйте клавиши **←** и **→** на клавиатуре.
- Перетаскивайте **ползунок** внизу, чтобы перейти к нужному месту.
- Счётчик показывает **номер выбранного кадра / общее количество кадров**, а ниже — время в видео.

### Как изменить FPS вручную

1. После открытия видео найдите поле **«FPS вручную»**.
2. Введите частоту кадров, например `30`, `60`, `120` или `240`.
3. Нажмите **«Применить»** — программа пересчитает шаг переключения и примерное количество кадров с указанным FPS.
4. Чтобы вернуться к автоматически обнаруженной частоте, нажмите **«Вернуть авто»** (кнопка доступна, если FPS удалось определить).

**Важно:** ручной ввод FPS не меняет само видео и не создаёт дополнительных кадров. Указывайте частоту **сохранённого видеофайла**, а не обязательно частоту, с которой камера снимала исходный материал. Если ролик был записан при 240 FPS, но сохранён с частотой 30 FPS, для просмотра кадров именно сохранённого файла обычно нужно ориентироваться на 30 FPS.

### Если что-то не работает

- **FPS не определился:** введите его вручную.
- **Видео не открывается:** возможно, браузер не поддерживает используемый кодек. Расширение `.mp4` само по себе не гарантирует поддержку.
- **Кадр визуально не меняется после нажатия:** браузер может показывать тот же декодированный кадр при переходе по временной метке. Точное покадровое декодирование этим способом не гарантируется. **Номер на счётчике — это запрошенная позиция, а не подтверждённый номер реально показанного кадра.**

Файл работает локально, без установки зависимостей и подключения к интернету. Приложение не отправляет выбранное видео на сервер.
