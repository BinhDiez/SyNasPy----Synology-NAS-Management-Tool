# SyNasPy

**A modern macOS application for managing Synology NAS servers.**

Wake up your NAS, shut it down safely, mount SMB volumes, manage multiple servers, and automate common tasks — all from a clean and intuitive macOS interface.

---

## 📸 Screenshots

| Main Window | Settings |
|-------------|----------|
| <img width="420" alt="Server Offline" src="https://github.com/user-attachments/assets/2598c7c9-7256-4ea4-94f7-800d95f60989"> | <img width="420" alt="Settings" src="https://github.com/user-attachments/assets/514809e4-b9a4-48c7-bb67-4d7039fc147c"> |

---

# ✨ Features

## 🚀 NAS Management

- Wake-on-LAN (WOL) support
- Safe NAS shutdown
- Optional Mac shutdown after NAS shutdown
- Automatic startup and shutdown timers
- Configurable countdown delays
- Pause and resume active timers

---

## 💾 Volume Management

- Mount SMB network volumes
- Unmount selected volumes
- Individual volume selection
- Automatic volume handling after NAS startup

---

## 🖥️ Multi-Server Support

- Unlimited server profiles
- Fast profile switching
- Create new profiles
- Duplicate existing profiles
- Rename profiles
- Delete profiles
- Set default profile

---

## 🔐 Security

- SSH key authentication
- No passwords stored
- Secure SSH communication
- Optional SSH key generation assistant
- Open the local `.ssh` directory directly from the application

---

## 🌐 Network Features

- Automatic IP detection
- Bonjour / mDNS discovery
- DNS lookup
- ARP lookup
- Network scanning fallback
- Manual IP configuration

---

## 🌍 Languages

SyNasPy is available in **17 languages**:

- 🇸🇦 Arabic (العربية)
- 🇨🇿 Czech (Čeština)
- 🇳🇱 Dutch (Nederlands)
- 🇬🇧 English (English)
- 🇫🇮 Finnish (Suomi)
- 🇫🇷 French (Français)
- 🇩🇪 German (Deutsch)
- 🇬🇷 Greek (Ελληνικά)
- 🇮🇹 Italian (Italiano)
- 🇳🇴 Norwegian (Norsk)
- 🇵🇱 Polish (Polski)
- 🇵🇹 Portuguese (Português)
- 🇷🇺 Russian (Русский)
- 🇪🇸 Spanish (Español)
- 🇸🇪 Swedish (Svenska)
- 🇹🇷 Turkish (Türkçe)
- 🇻🇳 Vietnamese (Tiếng Việt)

---

## 🎨 User Experience

- Native macOS interface
- Modern dark appearance
- Voice feedback (macOS)
- Progress indicator with percentage
- Keyboard shortcuts
- Automatic update checker
- Background update notifications
- Responsive user interface

---

# ⌨️ Keyboard Shortcuts

| Shortcut | Action |
|----------|--------|
| ⌘ E | Open Settings |
| Enter | Confirm |
| Esc | Cancel |

---

# ⚙️ Requirements

- macOS
- Synology NAS
- SSH enabled on the NAS
- SMB file sharing enabled (for volume management)
- Wake-on-LAN enabled (recommended)

---

# 🔒 Privacy & Security

SyNasPy communicates directly with your Synology NAS.

The application:

- never stores your passwords
- uses SSH key authentication
- keeps private SSH keys on your Mac
- does not require cloud services
- performs all communication locally between your Mac and NAS

---

# 🚀 Typical Workflow

1. Launch SyNasPy.
2. Select your NAS profile.
3. Wake your NAS using Wake-on-LAN.
4. Wait until the NAS becomes available.
5. Automatically mount selected SMB volumes.
6. Work as usual.
7. Shut down the NAS safely when finished.
8. Optionally shut down your Mac afterwards.

---

# ⭐ Highlights

- Designed specifically for Synology NAS
- Native macOS experience
- Multiple NAS profiles
- Intelligent network detection
- SSH key authentication
- Automatic volume management
- Timer automation
- 17 interface languages
- No subscription
- No telemetry
- No cloud dependency

---

# 📦 Installation

1. Download the latest release.
2. Move **SyNasPy.app** to the **Applications** folder.
3. Launch the application. (follow the Instruction in the included manual)
4. Configure your NAS profile.
5. Enjoy.

---

# ⚙️ Configuration

Settings Dialog Tabs

Tab Content
General Language selection, NAS credentials, SSH key path (with folder open and key creation buttons).
Volumes List of SMB volumes (one per line). The first volume is the main volume and cannot be unchecked.
Timing Auto‑shutdown delay, auto‑start delay, WOL wait, SMB wait, mount retries, and delay between NAS‑ and Mac‑shutdown (0–30 seconds).
Server Profiles Manage all profiles: create, duplicate, rename, delete, and set the active profile.

Configuration Files

All settings are stored in ~/Library/Application Support/SyNasPy/:

- synaspy_config.json – global settings (language, logo, etc.).
- server_profiles.json – all server profiles (including the active profile ID).

Log Files

Logs are written to ~/Library/Application Support/SyNasPy/Logs/ with automatic rotation (max 5 files).

---

# 🐛 Troubleshooting

NAS Not Found

- Use the 🔍 Find IP button in settings.
- Verify the NAS is powered on and connected to the network.

WOL Not Working

- Check the MAC address in settings.
- Ensure the NAS supports WOL and it is enabled.
- Try different WOL methods (the app tries Python‑based, wakeonlan, and etherwake).

Volume Mount Fails

- Confirm the NAS is online and SMB service is running.
- Increase the Mount Retries value in settings.
- Verify volume names are correct (case‑sensitive).

SSH Connection / Shutdown Issues

- If the app asks for a password or fails, run ssh-add ~/.ssh/id_rsa once (or use the 🔑 Create button to create a dedicated key).
- Make sure your SSH key is copied to the NAS (ssh‑copy‑id).
- For sudo shutdown, ensure the user has NOPASSWD for /sbin/shutdown, /sbin/poweroff, and /usr/syno/bin/synopoweroff in /etc/sudoers.

---

# 🏗️ Architecture

```
SyNasPy/
├── SyNasPy.py             # Main application
├── requirements.txt       # Dependencies
├── README.md              # This file
├── LICENSE                # MIT License
├── BinhDiez.png           # Application logo
├── SyNasPy.png            # Application icon
└── .gitignore
```

Key Components

- LanguageManager – Multi‑language support (11 languages).
- ServerProfile / ServerProfileManager – Profile data and persistence.
- Config – Central configuration (merges global and profile settings).
- SyNasPy – Main window and core logic.
- ConfigDialog – Settings interface (with profile management).
- InfoDialog – About window with version, licenses, and update checker.
- AppLogger – Logging with buffering and rotation.

--

# 🙏 Acknowledgments

- Synology – For their excellent NAS hardware and DSM.
- PyQt Team – For the amazing Qt bindings.
- macOS Community – For helpful system integration tips.

---

# 🔄 Changelog

Version 2.0.0 (Current)

- Multi‑Server Profiles: Manage any number of NAS devices.
- 17 Languages: Full UI translation.
- Profile Management: Create, duplicate, rename, delete, activate.
- SSH Key Assistant: Open folder, create new key (does not overwrite id_rsa) with optional passphrase.
- Configurable Shutdown Delay: Adjustable delay between NAS‑ and Mac‑shutdown (0‑30 s).
- Update Checker: Integrated manual and background update notifications.
- Improved Shutdown Logic: More reliable NAS shutdown with fallback methods.
- Removed Obsolete Status File: The boQuitNASapp.txt workaround is no longer used.
- Enhanced Progress Bar: Shows percentage outside the bar.

Version 1.0.0 (Legacy)

- Single NAS management.
- Basic WOL, shutdown, volume mounting.
- Initial settings dialog.

# 🤝 Contributing

Contributions, bug reports, feature requests, and pull requests are welcome.

If you find a bug or have an idea for improving SyNasPy, please open an issue.

---

# 📄 License

This project is licensed under the MIT License.
Copyright (c) 2026 BinhDiez64.

PyQt5 Notice: This application uses PyQt5, which is licensed under the GNU General Public License v3 (GPLv3).
Copyright (c) Riverbank Computing Limited.
Full license text: https://www.gnu.org/licenses/gpl-3.0.html

---

Made with ❤️ for the NAS community.

**SyNasPy makes managing your Synology NAS on macOS simple, secure, and efficient.**
---


