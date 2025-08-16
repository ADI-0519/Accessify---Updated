# Accessify

**Accessify** is a Chrome (Manifest V3) extension paired with a small Flask micro‑service, offering a suite of on-page accessibility enhancements:

* **Epilepsy-safe video playback**: Masks strobe frames using OpenCV + yt-dlp
* **Dyslexia mode**: Larger fonts, better spacing, and pastel backgrounds
* **Colour-blind CSS filters**: Supports protanopia, deuteranopia, and tritanopia
* **Irlen overlay**: Tinted overlay to reduce glare
* **In-page text-to-speech**: Powered by the Web Speech API
* **One-click paragraph summariser**: Uses OpenAI GPT-4o for concise summaries
* **Learning Zone**: Helps improve web surfing and comprehension

---

## Table of Contents

1. [Installation](#installation)
2. [Usage](#usage)
3. [Dev Demo](#dev-demo)
4. [Contributing](#contributing)
5. [License](#license)

---

## Installation

Tested on **Windows 10/11**, **macOS Sonoma**, and **Ubuntu 22.04**.

### 1. Clone the repository

```bash
git clone https://github.com/your-username/Accessify.git
cd Accessify
```

### 2. Install prerequisites

| Tool                | Windows                               | macOS (brew)               | Ubuntu / Debian                               |
| ------------------- | ------------------------------------- | -------------------------- | --------------------------------------------- |
| Python 3.11         | `winget install Python.Python.3.11`   | `brew install python@3.11` | `sudo apt install python3.11 python3.11-venv` |
| ffmpeg              | `choco install ffmpeg`                | `brew install ffmpeg`      | `sudo apt install ffmpeg`                     |
| Google Chrome 122+  | [Download](https://google.com/chrome) | same                       | same                                          |
| Node 18+ (for demo) | `winget install OpenJS.NodeJS.LTS`    | `brew install node`        | `sudo apt install nodejs npm`                 |

### 3. Set your OpenAI key

**macOS / Linux:**

```bash
echo 'export OPENAI_API_KEY="sk-..."' >> ~/.bash_profile
source ~/.bash_profile
```

**Windows PowerShell:**

```powershell
setx OPENAI_API_KEY "sk-..."   # persistent
$env:OPENAI_API_KEY="sk-..."   # current session
```

### 4. Install dependencies

```bash
python -m venv .venv
# Windows:
.venv\Scripts\activate
# macOS/Linux:
source .venv/bin/activate

pip install -r requirements.txt

# Optional: Next.js demo site
cd learn && npm install && cd ..
```

### 5. Build & run

**Cross-platform (requires dev dependencies):**

```bash
npm run dev   # starts Flask on :5000 + Next.js on :3000
```

**macOS/Linux alternative:**

```bash
./dev.sh
```

### 6. Load the Chrome extension

1. Open `chrome://extensions/` in Chrome
2. Toggle **Developer mode**
3. Click **Load unpacked** → select the `extension/` folder

---

## Usage

### Summariser / TTS / Overlays

1. Navigate to any article.
2. Click the Accessify ℹ︎ icon in the toolbar.
3. Toggle **Dyslexia Mode**, **Colour-blind Filters**, or **Irlen Overlay** as needed.
4. Use **Speak** to hear the page or **Summarise** for an AI digest.

### Epilepsy-Safe Video

1. Open a YouTube video.
2. Click **Epilepsy Mode** in the popup.
3. The page reloads with a processed MP4 where flashing frames are removed.

---

## Dev Demo

* Visit [http://localhost:3000](http://localhost:3000) to test features on sample articles and embedded YouTube iframes without leaving localhost.

---

## Contributing

1. Fork the repo
2. Create a feature branch:

```bash
git checkout -b feature/awesome-idea
```

3. Make changes & commit:

```bash
git commit -am "✨ Add awesome idea"
```

4. Push & open a Pull Request:

```bash
git push origin feature/awesome-idea
```

**Notes:**

* PRs should pass `flake8` (backend) and `eslint` (frontend).
* Report bugs or feature requests via Issues with clear reproduction steps.

---

## License

This project is licensed under the **MIT License**. See `LICENSE` for details.
