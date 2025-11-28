# 🖧 BridgeNet

**A Graphical Interface for Reverse Tethering (Gnirehtet)**

BridgeNet is a desktop tool I built to make reverse tethering easier. It creates a simple GUI around [Gnirehtet](https://github.com/Genymobile/gnirehtet), allowing you to share your PC's internet connection with your Android device via USB.

I mainly built this because using the command line (CLI) every time I wanted to connect my phone was annoying. This tool is super useful if you are in a college campus or office where the Wi-Fi is weak/restricted, but you have a stable ethernet connection on your laptop.

**No Root required.**

---

## 🚀 Key Features

- **No CLI Needed:** Start and stop the connection with a single button.
- **Auto-Reconnect:** If the USB cable gets bumped or disconnected, the app tries to reconnect automatically.
- **Configurable:** You can change the DNS server and MTU size directly from the settings if you need to bypass some network filters.
- **Live Logs:** Shows real-time logs in the app window so you can see if the connection is actually sending data.
- **Platform:** Currently fully functional on **Windows**. (I'm working on Linux support).

---

## 🛠️ How it's Built

This project is written in **Python** using **PyQt5** for the interface.

- **GUI:** PyQt5
- **Backend Logic:** Python `subprocess` (to handle ADB commands).
- **Core Utility:** Wraps the original `gnirehtet` binary (Rust/Java) by Genymobile.
- **Packaging:** PyInstaller (to create the standalone `.exe`).

---

## 🧰 Getting Started

Before running the app, you just need to make sure your phone allows your PC to talk to it.

### 1. Enable USB Debugging

You need to unlock Developer Options on your phone:

1. Navigate to `Settings > About phone`.
2. Tap **Build number** 7 times until it says "You are a developer".

   ![Enable Developer Options](assets/enable_developer_options.jpg)

3. Go back to `Settings > System > Developer Options`.
4. Turn on **USB debugging**.

   ![Enable USB Debugging](assets/enable_usb_debugging.jpg)

> **Important:** When you plug your phone in, you will get a popup asking to "Allow USB debugging?". Check the box that says **"Always allow from this computer"** and hit OK.

![Allow USB Debugging Prompt](assets/prompt.jpg)

### 2. (Optional) Disable Permission Monitor

If you use a Samsung device or certain other brands, they sometimes kill background processes to save battery. If the connection keeps dropping, try this:

1. Go to `Settings > Apps` (or Security settings).
2. Look for "App Permission Monitor" or "Battery Optimization" and disable it for the tool.

![Disable App Permission Monitor](assets/disable_permission_monitor.jpg)

---

## 🔧 Installation & Usage

You can download the latest `.exe` from the Releases tab, or run it from the source code:

```bash
# Clone the repo
git clone [https://github.com/your-username/bridgenet-gnirehtet-gui.git](https://github.com/your-username/bridgenet-gnirehtet-gui.git)
cd bridgenet-gnirehtet-gui

# Install the python libraries
pip install -r requirements.txt

# Run the app
python main.py
