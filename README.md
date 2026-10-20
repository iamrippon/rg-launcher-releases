# RG Launcher — Official Public Releases

[![Release](https://img.shields.io/badge/Release-v1.0.0-blue.svg)](https://github.com/iamrippon/rg-launcher-releases/releases/tag/v1.0.0)
[![Platform](https://img.shields.io/badge/Platform-Windows%2010%20%7C%2011-brightgreen.svg)](https://github.com/iamrippon/rg-launcher-releases)
[![Status](https://img.shields.io/badge/Build-Stable-success.svg)](https://github.com/iamrippon/rg-launcher-releases)
[![Discord](https://img.shields.io/badge/Discord-Join%20Community-5865F2?logo=discord&logoColor=white)](https://discord.gg/GFGCn2mMrE)
[![Website](https://img.shields.io/badge/Website-rg--studios.in-00C49F)](https://rg-studios.in/)

Welcome to the official public distribution repository for **RG Launcher**.

**RG Launcher is a personal project developed by RixStonGamer and released, managed, and maintained under RG Studios** (an unregistered, personally operated studio/project in India).

> [!NOTE]
> **RG Launcher is an independent Minecraft launcher and is NOT an official Minecraft product. It is NOT approved by or associated with Mojang or Microsoft.**

This repository is dedicated solely to distributing official releases, installers, update feeds, and user-facing documentation for RG Launcher. It does **not** contain the private application source code.

---

## 📥 Download RG Launcher v1.0.0

| Installer | Operating System | Architecture | Size | SHA-256 Checksum |
| :--- | :--- | :--- | :--- | :--- |
| [**RG-Launcher-Setup-1.0.0.exe**](https://github.com/iamrippon/rg-launcher-releases/releases/download/v1.0.0/RG-Launcher-Setup-1.0.0.exe) | Windows 10 / 11 | x64 (64-bit) | 123.18 MB | `d689a14ddbe0d8e1d52509bd0bed22716bde810e1eda2b291d402c99bdc9b706` |

*Release assets including update metadata ([`latest.yml`](https://github.com/iamrippon/rg-launcher-releases/releases/download/v1.0.0/latest.yml)), differential block map ([`RG Launcher-Setup-1.0.0.exe.blockmap`](https://github.com/iamrippon/rg-launcher-releases/releases/download/v1.0.0/RG.Launcher-Setup-1.0.0.exe.blockmap)), and verified hashes ([`checksums.txt`](https://github.com/iamrippon/rg-launcher-releases/releases/download/v1.0.0/checksums.txt)) are available on the [v1.0.0 Release Page](https://github.com/iamrippon/rg-launcher-releases/releases/tag/v1.0.0).*

---

## ✨ Overview & Features

RG Launcher is a modern, lightweight, and high-performance Minecraft launcher built for players, modders, and server administrators.

- 🚀 **Multi-Loader Support**: Create, manage, and launch instances for **Vanilla**, **Fabric**, **Quilt**, **NeoForge**, and **Minecraft Forge**.
- 🧩 **Integrated Mod & Modpack Browser**: Search, inspect, and install community mods, resource packs, and modpacks directly from **Modrinth** and **CurseForge** without leaving the launcher.
- 🖥️ **Local Server Hub**: Download, configure, and operate dedicated local Minecraft server instances directly on your machine.
- ⚙️ **Custom Profile Workspace**: Tailor RAM allocation (minimum and maximum heap), custom Java runtime paths, JVM arguments, and directory isolation per profile.
- 🔄 **Safe Auto-Updater**: Built-in update checking that queries this public distribution repository with active-game guards that prevent updates while Minecraft or local servers are running.
- 🩺 **Integrated Diagnostics & Logs**: View live launcher and game logs, inspect crash reports, and export diagnostics safely.
- 🎨 **Polished Modern UI**: Dark glassmorphic interface with responsive layout, dynamic background art, and quick-launch controls.

> [!IMPORTANT]
> **Authentication Notice**: Offline / local username login is temporarily disabled in v1.0.0 while security enhancements are being completed. A legitimate **Microsoft Account** with Minecraft: Java Edition ownership is required to sign in and play.

---

## 💻 System Requirements

### Minimum Requirements
- **Operating System**: Windows 10 (64-bit) or Windows 11 (64-bit)
- **Processor**: Intel Core i3-3210 3.2 GHz / AMD A8-7600 APU 3.1 GHz or equivalent
- **Memory (RAM)**: 4 GB
- **Graphics**: Intel HD Graphics 4000 / AMD Radeon R5 series / NVIDIA GeForce 400 series with OpenGL 4.4 support
- **Storage**: 2 GB free disk space for launcher assets (additional storage required for Minecraft instances, mods, and worlds)
- **Network**: Broadband Internet connection for authentication, downloading manifests, and multiplayer

### Recommended Requirements
- **Operating System**: Windows 11 (64-bit, latest version)
- **Processor**: Intel Core i5-4690 3.5 GHz / AMD FX-8370 4.0 GHz or modern multi-core CPU
- **Memory (RAM)**: 8 GB or higher (16 GB for heavy modpacks)
- **Graphics**: NVIDIA GeForce 900 series / AMD Radeon RX 400 series or newer with updated drivers
- **Storage**: Solid State Drive (SSD) with 10 GB+ free disk space
- **Java**: Java 17 or Java 21 (RG Launcher can detect and configure installed Java runtimes)

---

## 🚀 Installation & First Launch

1. **Download**: Download [**RG-Launcher-Setup-1.0.0.exe**](https://github.com/iamrippon/rg-launcher-releases/releases/download/v1.0.0/RG-Launcher-Setup-1.0.0.exe).
2. **Run Installer**: Open the downloaded installer file.
   - *Windows SmartScreen Note*: If you encounter a Windows Defender SmartScreen prompt ("Windows protected your PC"), click **"More info"** followed by **"Run anyway"**.
3. **Select Install Directory**: Follow the setup wizard instructions. By default, RG Launcher installs to your local user application folder and creates a desktop shortcut.
4. **Sign In**: Launch RG Launcher and click **Login with Microsoft**. A secure Microsoft authentication window will open. Complete the sign-in with your Microsoft account that owns Minecraft: Java Edition.
5. **Create a Profile & Play**: Click **Create Profile**, select your desired Minecraft version (e.g. 1.21.x) and loader (Vanilla, Fabric, Forge, etc.), allocate RAM, and click **Play**!

---

## 🔄 Updates & Maintenance

RG Launcher includes built-in update verification connected directly to this repository:
- **Automatic Background Check**: The launcher checks for newer stable releases upon startup.
- **Manual Check**: You can manually check for updates at any time by navigating to **Settings** ➡️ **Update Center** or clicking the version badge in **About**.
- **Safe Installation**: If an update is downloaded, the launcher prompts you to restart. Installation is safely blocked if Minecraft or any local server is actively running.

---

## 🗑️ Uninstallation Instructions

If you wish to uninstall RG Launcher:
1. **Via Windows Settings**:
   - Open **Windows Settings** ➡️ **Apps** ➡️ **Installed apps** (or **Add or remove programs**).
   - Search for **RG Launcher**.
   - Click the three dots `...` and select **Uninstall**.
   - Follow the uninstallation wizard to remove the launcher application files and desktop shortcuts.
2. **Optional Complete Data Removal**:
   - The uninstaller removes the application binaries. If you also wish to permanently delete your saved launcher profiles, configurations, and downloaded cache, delete the following directory:
     `%APPDATA%\RG Launcher` (press `Win + R`, paste `%APPDATA%\RG Launcher`, and delete the folder).
   - Your Minecraft worlds and screenshots remain in `%APPDATA%\.minecraft` (or your chosen custom profile directory) unless manually deleted.

---

## ⚠️ Known Limitations in v1.0.0

- **Platform Availability**: v1.0.0 is packaged and verified for **Windows (x64)**. Linux and macOS packages are planned for upcoming releases.
- **Offline Login**: Offline username mode is temporarily unavailable in this release.
- **Server Hub**: Local Server Hub currently manages Java-based `.jar` server instances; bedrock dedicated server management is not included in v1.0.0.

---

## 🛠️ Diagnostics & Troubleshooting

If you encounter an issue or game crash:
1. Open **Settings** or **Logs** in the launcher navigation sidebar.
2. Review the game crash output or launcher log.
3. To share a log for assistance:
   - Copy the log content.
   - **Sanitize Personal Information**: Before sharing logs on community forums, redact your Windows username, local file paths, personal IP addresses, or any other sensitive identifying details.
4. Join our community Discord or reach out via official support channels below.

---

## 🤝 Community & Official Support

RG Launcher is developed by **RixStonGamer** and released, managed, and maintained under **RG Studios** in India.

- 🌐 **Official Website**: [https://rg-studios.in/](https://rg-studios.in/)
- 💬 **Discord Community**: [https://discord.gg/GFGCn2mMrE](https://discord.gg/GFGCn2mMrE)
- ✉️ **Support Email**: [in.rgstudios@gmail.com](mailto:in.rgstudios@gmail.com)

*Note: Technical assistance is offered on a voluntary, best-effort basis without guaranteed response times. For community help, join our Discord server.*

---

## 📄 Legal & Documentation Package

Please review our user-facing legal and transparency documentation:
- 📜 [**Terms of Service & Use**](TERMS.md) — Acceptable use rules, service conditions, non-affiliation disclaimers, warranty disclaimers, and limitation of liability.
- ⚖️ [**Software License & End User Agreement**](LICENSE.md) — Freeware binary license grant, personal non-commercial gaming permissions, and reservation of rights.
- 🔒 [**Privacy Policy**](PRIVACY_POLICY.md) — Factual breakdown of local storage, DPAPI token encryption, voluntary support tickets, zero telemetry, and network transparency.
- 📦 [**Third-Party Software & Open-Source Notices**](THIRD_PARTY_NOTICES.md) — Full inventory of bundled open-source components and complete license texts (MIT, ISC, Apache 2.0).

---

## ⚖️ Legal Disclaimers

- **Minecraft**: **NOT AN OFFICIAL MINECRAFT PRODUCT. NOT APPROVED BY OR ASSOCIATED WITH MOJANG OR MICROSOFT.** Minecraft is a registered trademark of **Mojang AB** and **Microsoft Corporation**.
- **CurseForge**: CurseForge is a registered trademark of **Overwolf Ltd**. Neither RixStonGamer nor RG Studios is affiliated with or endorsed by Overwolf Ltd.
- **Modrinth**: Modrinth is a trademark of **Rinth, Inc**. Neither RixStonGamer nor RG Studios is affiliated with or endorsed by Rinth, Inc.
- All other trademarks, trade names, and service marks are the property of their respective owners.
