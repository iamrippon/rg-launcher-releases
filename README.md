# RG Launcher — Official Public Releases

[![Release](https://img.shields.io/badge/Release-v1.2.0-blue.svg)](https://github.com/iamrippon/rg-launcher-releases/releases/tag/v1.2.0)
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

## 🚀 Download RG Launcher (Latest: v1.2.0)

| Installer | Operating System | Architecture | Size | SHA-256 Checksum |
| :--- | :--- | :--- | :--- | :--- |
| [**RG-Launcher-Setup-1.2.0.exe**](https://github.com/iamrippon/rg-launcher-releases/releases/download/v1.2.0/RG-Launcher-Setup-1.2.0.exe) | Windows 10 / 11 | x64 (64-bit) | 119.91 MB (125,732,064 bytes) | `547A8D353D9AC4459CE45BD7CC4C28278AE0683B5EC7157F9A3DB186918753D0` |

*Release assets including update metadata ([`latest.yml`](https://github.com/iamrippon/rg-launcher-releases/releases/download/v1.2.0/latest.yml)), differential block map ([`RG-Launcher-Setup-1.2.0.exe.blockmap`](https://github.com/iamrippon/rg-launcher-releases/releases/download/v1.2.0/RG-Launcher-Setup-1.2.0.exe.blockmap)), and verified hashes ([`SHA256SUMS.txt`](https://github.com/iamrippon/rg-launcher-releases/releases/download/v1.2.0/SHA256SUMS.txt)) are available on the [v1.2.0 Release Page](https://github.com/iamrippon/rg-launcher-releases/releases/tag/v1.2.0).*

---

## ✨ What's New in v1.2.0

RG Launcher v1.2.0 brings major enhancements in reliability, stability, diagnostic tools, and player experience:

- 🛠️ **Intelligent Mod Compatibility Checker & Auto-Fix 2.0**: Detects missing dependencies, duplicate files, version mismatches, and mod conflicts. Resolves them with 1-click automated repairs, automatic dependency downloads from Modrinth/CurseForge, and rollback safety backups.
- ☕ **Automatic Java Runtime Detection & Dependency Auto-Installer**: Eliminates manual Java installation. Dynamically detects required Java major versions (Java 8, 17, 21, and 25 for Minecraft 26.x), automatically downloads lightweight Adoptium JRE packages (~38–47 MB) with SHA-256 validation, and handles pre-flight launch checks.
- 🌐 **User-Managed Minecraft Server Manager**: Manage your personal multiplayer servers with real-time Server List Ping (SLP) status, latency in milliseconds, player counts, MOTD preview, DNS SRV resolution, and direct-connect launching. Supports both Java Edition and Bedrock Edition with zero sponsored, featured, or default listings.
- 💾 **Standard ZIP Backup Center**: Backups now use standard `.zip` format (e.g. `Survival-Backup.zip`) with internal `backup_manifest.json` and SHA-256 integrity verification, openable with Windows File Explorer, 7-Zip, or WinRAR, along with support for custom backup storage folders and backward compatibility for `.rgbackup`.
- 🩺 **Intelligent Crash Log Analyzer**: Automatically parses crash reports in `crash-reports/` and `logs/latest.log`, detects root causes (OutOfMemoryError, Java version mismatch, missing dependencies, Mixin conflicts), and explains solutions in plain English with 1-click fixes.
- 📥 **Download Manager 2.0**: Active queue with 3 concurrent network requests, chunked HTTP range resume support via `.rgpart` staging files, live speed/ETA calculation, and cryptographic hash verification.
- 🎮 **Better Player Experience**: Visual screenshot lightbox gallery, singleplayer World Manager with NBT metadata inspection and 1-click world zip backups, and local playtime tracker.

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
- **Java**: Automatic installation handled by RG Launcher (Java 8, 17, 21, and 25 supported)

---

## 📥 Installation Guide

1. **Download**: Click [**RG-Launcher-Setup-1.2.0.exe**](https://github.com/iamrippon/rg-launcher-releases/releases/download/v1.2.0/RG-Launcher-Setup-1.2.0.exe) above.
2. **Launch Setup**: Double-click the downloaded executable.
   - *If Windows Defender SmartScreen displays an informational prompt, click **"More info"** and then **"Run anyway"**.*
3. **Choose Install Directory**: Follow the setup wizard instructions. By default, RG Launcher installs to your local user application folder and creates desktop and Start Menu shortcuts.
4. **Sign In**: Launch RG Launcher and click **Login with Microsoft**. Complete the sign-in with your Microsoft account that owns Minecraft: Java Edition.
5. **Create a Profile & Play**: Click **Create Profile**, select your desired Minecraft version (e.g. 1.21.4) and loader (Vanilla, Fabric, etc.), and click **Play**! Missing Java runtimes will be automatically installed if needed.

---

## 🔄 Updates & Maintenance

RG Launcher includes built-in update verification connected directly to this repository:
- **Automatic Background Check**: The launcher checks for newer stable releases upon startup.
- **Manual Check**: You can manually check for updates at any time by navigating to **Settings → Updates** or clicking the version badge in **About**.
- **Safe Installation**: If an update is downloaded, the launcher prompts you to restart. Installation is safely blocked if Minecraft is actively running.

---

## 🗑️ Uninstallation Instructions

If you wish to uninstall RG Launcher:
1. **Via Windows Settings**:
   - Open **Windows Settings → Apps → Installed apps** (or **Add or remove programs**).
   - Search for **RG Launcher**.
   - Click the three dots `...` and select **Uninstall**.
   - Follow the uninstallation wizard to remove the application files and shortcuts.
2. **Optional Complete Data Removal**:
   - The uninstaller removes application binaries. If you also wish to delete saved launcher configurations and caches, delete `%APPDATA%\RG Launcher`.
   - Your Minecraft worlds and screenshots remain in `%APPDATA%\.minecraft` (or your custom instance directories) unless manually deleted.

---

## 📜 Legal & Disclaimers

- **Minecraft** is a registered trademark of **Mojang Synergies AB** / **Microsoft Corporation**.
- **RG Launcher** and **RG Studios** are not affiliated with, endorsed by, or sponsored by Mojang Studios or Microsoft.
- All modding libraries, loaders (Fabric, Forge, NeoForge, Quilt), and API integrations (Modrinth, CurseForge) belong to their respective creators and organizations.
- For full licensing and terms, please review [LICENSE.md](LICENSE.md), [TERMS.md](TERMS.md), and [PRIVACY_POLICY.md](PRIVACY_POLICY.md).

---

© 2026 RG Studios. All rights reserved.
