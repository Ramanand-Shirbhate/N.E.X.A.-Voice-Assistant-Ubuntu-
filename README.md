# N.E.X.A. (Neural Executive eXperience Assistant)

![Python](https://img.shields.io/badge/Python-3.8%2B-blue?style=for-the-badge&logo=python)
![Platform](https://img.shields.io/badge/Platform-Linux%20(Ubuntu/GNOME)-orange?style=for-the-badge&logo=linux)
![AI](https://img.shields.io/badge/AI-Google%20Gemini-green?style=for-the-badge&logo=google)
![Status](https://img.shields.io/badge/Status-Active-success?style=for-the-badge)

**N.E.X.A.** is a highly sophisticated, voice-activated desktop automation assistant built for Linux. Inspired by J.A.R.V.I.S., it combines offline wake-word detection with cloud-based generative AI to provide executive control over your operating system.

It bridges the gap between **local system control** (shell automation) and **large language models** (Google Gemini) to create a truly responsive assistant.

---

## ⚡ Key Features

* **🧠 Hybrid Intelligence:** Uses **Google Gemini** for complex queries/web search and local logic for instant system control.
* **🗣️ Natural Speech:** High-quality, neural text-to-speech output using **Edge-TTS**.
* **🔌 IPC Media Control:** Controls `mpv` media players seamlessly via Unix Sockets (Play, Pause, Skip, Vibe playlists).
* **🔄 Smart Session Restore:** Remembers which apps were running before shutdown and offers to restore them on the next boot.
* **💻 System Automation:**
    * Control Volume (`pactl`) and Brightness (`xrandr`).
    * Launch and Kill applications.
    * Perform graceful Shutdowns, Reboots, and Suspends.
* **✍️ Continuous Dictation:** "Start typing" mode injects speech-to-text directly into your active window.

---

## 🛠️ Prerequisites

N.E.X.A. is optimized for **Linux (Ubuntu/Debian)**. You need the following system packages:

```bash
sudo apt update
sudo apt install python3-venv mpv ffmpeg portaudio19-dev pulseaudio-utils xrandr libespeak1

mpv: Required for media playback.
xrandr: Required for brightness control.
pulseaudio-utils: Required for volume control.


Clone the RepositoryBashgit clone [https://github.com/yourusername/N.E.X.A.git](https://github.com/yourusername/N.E.X.A.git)
cd N.E.X.A
Set up Virtual EnvironmentBashpython3 -m venv venv
source venv/bin/activate
Install Python DependenciesBashpip install requests SpeechRecognition pynput pvporcupine pvrecorder edge-tts
⚙️ Configuration⚠️ Important: You must configure the main.py file before running the assistant.API Keys:Get a Porcupine Access Key from Picovoice Console.Get a Gemini API Key from Google AI Studio.Update Variables in main.py:Python# Set your keys
PICOVOICE_ACCESS_KEY = "YOUR_PICOVOICE_KEY"
API_KEY = "YOUR_GEMINI_KEY"

# Set your paths (Use absolute paths)
HOTWORD_MODEL_PATH = "/home/user/path/to/NEXA_model.ppn"
MUSIC_BASE_PATH = "/home/user/Music"
🚀 Usage
Activate your environment and run the script:
source venv/bin/activate
python main.py
Wait for the initialization message:
"All core systems are initialized. I am N.E.X.A..."
🗣️ Voice Command Examples
Category,Commands
Conversation,"""Hello"", ""How are you?"", ""Who are you?"""
System,"""Set volume to 50%"", ""Increase brightness"", ""Shutdown system"""
Apps,"""Open VS Code"", ""Launch Chrome"", ""Close Music"""
Web,"""Open youtube.com"", ""Search for [query]"""
Music,"""Play Vibe"", ""Play Happy"", ""Next song"", ""Pause music"""
Dictation,"""Start typing"" (activates dictation), ""Stop typing"" (exits)"
Session,"""Restore session"" (if prompted on startup)"
🔒 Security Note
Do not commit your API keys to GitHub.

It is recommended to use Environment Variables for your keys (os.getenv('GEMINI_API_KEY')) instead of hardcoding them in the script.
🤝 Contributing
Contributions are welcome! Please feel free to submit a Pull Request.

Fork the Project

Create your Feature Branch (git checkout -b feature/AmazingFeature)

Commit your Changes (git commit -m 'Add some AmazingFeature')

Push to the Branch (git push origin feature/AmazingFeature)

Open a Pull Request
