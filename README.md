# 🎮 Multichat Ultra Final - Presentation

## What is Multichat?

**Multichat Ultra Final** is a desktop application developed in Python that allows streamers to unify the chats from **Twitch, YouTube, TikTok, and Kick** into a single web interface, ideal for use as a **Browser Source in OBS Studio**.

<img width="1916" height="973" alt="SCR-20260424-pnkt" src="https://github.com/user-attachments/assets/f2746faf-28c9-4988-a836-66bf20a6afe6" />

---

## 🎯 What does the application do?

### 1. **Multi-Platform Aggregation**
- Simultaneously connects chats from the 4 most popular streaming platforms
- Displays all messages in real time in a single window
- Ideal for streamers broadcasting on multiple platforms simultaneously

### 2. **Customizable Web Interface**
- **Control Panel** with a two-column layout (minimalist and attractive)
- **10 different bubble styles**:
  - Classic, Messaging, Minimalist, Glassmorphism, With Avatars
  - **New**: Neon Cyan, Gradient, Outline, Bottom Glow, Pill Modern
- **Real-time customization**:
  - Font size (12–32px)
  - Background opacity (transparent for OBS)
  - Typography (Segoe UI, Arial, Mono, Comic Sans)
  - Text colors and Rainbow mode
  - Pause on mouse hover

### 3. **Multiple Layouts for OBS**
| Mode | Description | Recommended Use |
|------|-------------|-----------------|
| **Vertical** | Messages stacked upward | Side panel 400×800px |
| **Horizontal** | Cards in a row, up to 20 messages | Wide bar 1920×80px |
| **Ticker** | Messages scroll from right to left | Narrow bar 1920×64px |
| **Scroll** | Movie credits effect (pure CSS) | Vertical panel 400×800px |

### 4. **Intelligent Message Balancing**
- Separate queues per platform (Twitch, YouTube, TikTok, Kick)
- **Round-robin** algorithm that prevents a very active platform from flooding the chat
- All messages are displayed equitably

<img width="1239" height="764" alt="SCR-20260424-pnpe" src="https://github.com/user-attachments/assets/50995ed7-796d-4392-b67a-65edddbe856c" />

---

## 🛠 Why this application?

### **Problem**
Streamers broadcasting on multiple platforms (Twitch + YouTube + TikTok + Kick) must monitor each chat separately, which is inefficient and error-prone.

### **Solution**
Multichat Ultra Final centralizes all chats in a single window, enabling:
- ✅ **Efficiency**: One place to read all messages
- ✅ **Visibility**: Viewers from all platforms feel integrated
- ✅ **Customization**: Adapt the design to your personal brand
- ✅ **Ease of use**: One click to start, no complex configurations

---

## 🚀 Technologies Used

### Backend
- **Python 3.12+** with:
  - **FastAPI** – Asynchronous web server
  - **Socket.IO** – Real-time communication
  - **httpx** – Asynchronous HTTP client
  - **TikTokLive** – Native TikTok connection
  - **websockets** – Direct connection to Pusher (Kick)
  - **python-socketio** – FastAPI integration

### Frontend
- **HTML5 + CSS3** (Tailwind CSS via CDN)
- **Vanilla JavaScript** with:
  - Socket.IO client
  - CSS Animations (for ticker and scroll modes)
  - LocalStorage (configuration persistence)

### Technical Features
- ✅ **No token dependencies**: Twitch uses anonymous IRC
- ✅ **Robust error handling**: Automatic reconnection on all platforms
- ✅ **Emote proxy**: Avoids CORS blocks in browsers
- ✅ **Per-platform queues**: Prevents visual saturation
- ✅ **Compatibility**: macOS (`.command`) and Windows (`.bat`)

---

## 📦 Quick Installation

### Option 1: Double Click (Recommended)
- **macOS**: Run `start_mac.command`
- **Windows**: Run `start_windows.bat`

### Option 2: Manual
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
pip install -r requirements.txt
python gui.py
```

Then open `http://localhost:8000` in your browser.

---

## 🎨 Available Bubble Styles

| Style | Description |
|-------|-------------|
| **Classic** | Left border in platform color |
| **Messaging** | WhatsApp/Telegram style with triangular "tail" |
| **Minimalist** | Text only with shadow, no borders |
| **Glassmorphism** | Frosted glass effect |
| **With Avatars** | Circular profile picture extending outward |
| **Neon Cyan** | Pulsating neon effect (new) |
| **Gradient** | Pink-yellow-cyan gradient (new) |
| **Outline** | Thin outline only (new) |
| **Bottom Glow** | Glowing bottom border (new) |
| **Pill Modern** | Modern pill shape (new) |

---

## 🔧 Troubleshooting

### TikTok won't connect
- Make sure the streamer is **LIVE**
- If `DEVICE_BLOCKED` appears, wait a few minutes or change your IP

### Kick won't connect
- Verify that the channel exists
- Kick uses Pusher WebSocket (does not require the channel to be live)
- Check the logs at `/tmp/multichat_start.log` (macOS)

### The chat appears cut off
- Adjust the font size in the Control Panel
- Check the dimensions in OBS

### Missing modules error
- Run `start_mac.command` or `start_windows.bat` again
- Missing dependencies will be installed automatically

---

## 📄 Project Structure

```
Multichat Ultra Final/
├── main.py                 # FastAPI + Socket.IO server
├── gui.py                  # Graphical interface (Tkinter)
├── shared_state.py         # Global data store
├── chat_managers/          # Per-platform managers
│   ├── twitch.py           # Twitch IRC connection
│   ├── youtube.py          # YouTube internal API
│   ├── tiktok.py           # TikTokLive
│   ├── kick.py             # Pusher WebSocket
│   └── emoji_utils.py      # Emoji conversion
├── templates/              # HTML templates
│   ├── index.html          # Control Panel
│   └── chat.html           # Chat View (OBS)
├── start_mac.command        # Quick start macOS
├── start_windows.bat        # Quick start Windows
├── requirements.txt         # Python dependencies
├── README.md                # Technical documentation
├── MANUAL_USUARIO.md        # User manual
└── PRESENTACION.md          # This file
```

---

## 👤 Credits

**Developed by:** Tony Reel  
**Contact:**
- Twitch: [tonyreel](https://twitch.tv/tonyreel)
- YouTube: [@tonyreel](https://youtube.com/@tonyreel)
- TikTok: [@tonyreel](https://tiktok.com/@tonyreel)
- Kick: [tonyreel](https://kick.com/tonyreel)

---

## 📜 License

This project is open source. If you use it, please give credit to the original developer.

**Thank you for using Multichat Ultra Final!** 🎉

If you can, buy me a coffee

[![Buy Me A Coffee](https://img.shields.io/badge/Buy%20Me%20a%20Coffee-ffdd00?style=for-the-badge&logo=buy-me-a-coffee&logoColor=black)](https://paypal.me/yaba09)
