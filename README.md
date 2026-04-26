# YT-Ripper
# 🎵 YT Ripper

> Made with love, caffeine, and zyns by **occult from ohio** ❤️

A free and open source YouTube audio ripper, playlist builder, and audio editor for Windows. Convert YouTube videos to MP3, FLAC, WAV, M4A, OGG, and OPUS — with a built-in theme engine, history tracker, and playlist combiner.

---

## Features

- **Convert YouTube audio** to MP3, FLAC, WAV, M4A, OGG, OPUS
- **Adjustable quality** — 128, 192, 256, or 320 kbps
- **Pitch and volume control** per track before converting
- **Playlist Builder** — queue YouTube tracks and export them as one combined file
- **Local File Merger** — drag and drop existing audio files and combine them
- **Normalize loudness** across tracks to streaming standard (−14 dBFS)
- **Crossfade** between tracks when building playlists
- **Library** — every converted track is saved and tracked automatically
- **History window** — browse, re-download, or delete past conversions
- **Output Folder** — set a custom save location with a native folder picker
- **Theme Engine** — full color wheel with presets (Cyberpunk, Anime, Retro, etc.)
- **Rainbow Mode** — cycles accent color continuously, persists after closing theme window
- **Windows installer** — auto-downloads ffmpeg, creates shortcuts, registers uninstaller

---

## Screenshots

> *(Add screenshots here)*

---

## Installation

### Option 1 — Windows Installer (recommended)

1. Download `YTRipper_Setup.exe` from the [Releases](../../releases) page
2. Run it and follow the wizard
3. ffmpeg is downloaded automatically during install
4. Launch from Desktop or Start Menu

### Option 2 — Run from source

**Requirements:**
- Python 3.11 or 3.12
- ffmpeg.exe + ffprobe.exe in the project folder (from [ffmpeg.org](https://ffmpeg.org))

```bash
git clone https://github.com/yourusername/yt-ripper.git
cd yt-ripper
pip install flask flask-cors yt-dlp pydub pywebview
python app.py
```

---

## Build the installer yourself

### Step 1 — Build EXE with PyInstaller
```bash
pip install pyinstaller
pyinstaller --onefile --windowed \
  --add-data "ytconv.html;." \
  --add-data "merge.html;." \
  --add-data "theme.html;." \
  --add-data "output.html;." \
  --add-data "history.html;." \
  --name "YTRipper" \
  app.py
```

### Step 2 — Compile installer
1. Download [Inno Setup](https://jrsoftware.org/isinfo.php)
2. Open `installer.iss` in Inno Setup
3. Press `Ctrl + F9` to compile
4. Your installer appears at `installer_output/YTRipper_Setup.exe`

---

## Project Structure

```
yt-ripper/
  app.py          — Flask backend (Python)
  ytconv.html     — Main convert window
  merge.html      — Playlist Builder + Local File Merger
  theme.html      — Color wheel / theme picker
  output.html     — Output folder settings
  history.html    — Conversion history
  installer.iss   — Inno Setup installer script
  ffmpeg.exe      — Audio engine (not included, auto-downloaded by installer)
  ffprobe.exe     — Audio probe tool (not included, auto-downloaded by installer)
```

---

## Dependencies

| Package | Purpose | License |
|---|---|---|
| [Flask](https://flask.palletsprojects.com) | Backend web server | BSD-3-Clause |
| [flask-cors](https://github.com/corydolphin/flask-cors) | Cross-origin support | MIT |
| [yt-dlp](https://github.com/yt-dlp/yt-dlp) | YouTube downloading | Unlicense |
| [pydub](https://github.com/jiaaro/pydub) | Audio processing | MIT |
| [pywebview](https://pywebview.flowrl.com) | Native desktop window | BSD-3-Clause |
| [iro.js](https://iro.colorjs.io) | Color wheel widget | MIT |
| [ffmpeg](https://ffmpeg.org) | Audio conversion engine | LGPL v2.1+ / GPL v2+ |

---

## License

This project is licensed under the **MIT License**.

```
MIT License

Copyright (c) 2026 occult from ohio

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

---

## FFmpeg Attribution (Required by License)

This software uses **FFmpeg** for audio conversion and processing.

> FFmpeg is a trademark of Fabrice Bellard.
> FFmpeg is licensed under the GNU Lesser General Public License (LGPL) version 2.1 or later.
> Some optional components of FFmpeg are licensed under the GNU General Public License (GPL) version 2 or later.
>
> The build of FFmpeg distributed with or downloaded by this installer is sourced from
> [BtbN/FFmpeg-Builds](https://github.com/BtbN/FFmpeg-Builds) and is compiled with GPL-enabled components,
> which means the distributed binary is subject to the **GPL v2 or later**.
>
> In accordance with the GPL, the source code for FFmpeg is available at:
> **https://ffmpeg.org/download.html**
> and
> **https://github.com/FFmpeg/FFmpeg**
>
> You are free to replace the bundled `ffmpeg.exe` and `ffprobe.exe` with your own build of FFmpeg.
>
> The full text of the LGPL v2.1 license is available at:
> https://www.gnu.org/licenses/old-licenses/lgpl-2.1.html
>
> The full text of the GPL v2 license is available at:
> https://www.gnu.org/licenses/old-licenses/gpl-2.0.html

### What this means for you as a user

- YT Ripper is free and open source — you can use, modify, and redistribute it
- ffmpeg is downloaded separately during install and is not bundled in the source code of this project
- Because this project links against GPL-licensed ffmpeg components, if you redistribute binaries built from this project that include ffmpeg, those binaries must also comply with the GPL
- The source code of this project (Python, HTML, JS) remains under the MIT license

---

## Disclaimer

YT Ripper is intended for personal use and for downloading content you have the legal right to download. Downloading copyrighted content without permission may violate YouTube's Terms of Service and applicable copyright laws. The developers are not responsible for how you use this software.

---

## Contributing

Pull requests are welcome. For major changes please open an issue first.

1. Fork the repo
2. Create your feature branch (`git checkout -b feature/my-feature`)
3. Commit your changes (`git commit -m 'Add my feature'`)
4. Push to the branch (`git push origin feature/my-feature`)
5. Open a Pull Request

---

## Acknowledgements

- [FFmpeg](https://ffmpeg.org) — the backbone of all audio processing
- [yt-dlp](https://github.com/yt-dlp/yt-dlp) — YouTube downloading engine
- [iro.js](https://iro.colorjs.io) by James Daniel — color wheel component
- [pywebview](https://pywebview.flowrl.com) — native window wrapper
- [Inno Setup](https://jrsoftware.org) by Jordan Russell — Windows installer compiler
