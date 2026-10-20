# Privacy Policy

> **NOTICE — DRAFT FOR INFORMATIONAL PURPOSES ONLY**  
> *This Privacy Policy is a draft prepared for public software distribution. It describes the data handling practices of the RG Launcher desktop application and is provided for transparency. It requires formal review and finalization by a qualified legal professional.*  
> **Effective Date**: October 20, 2026  
> **Application Version**: 1.0.0 and subsequent releases  

---

## 1. Introduction & Core Philosophy

**RG Studios** ("we", "our", or "us", lead developer Ripon Ghosh) respects your personal privacy. **RG Launcher** (the "Software") is designed to run locally on your computer with a privacy-first approach. 

We do **not** sell your personal data, we do **not** run user-tracking surveillance services, and we do **not** collect telemetry or keystroke data.

This Privacy Policy explains what information is processed locally on your device, what network calls the Software makes to third-party services, and how your data is handled.

---

## 2. Information Processed & Stored Locally

The Software operates primarily as a local desktop application. The following categories of data are created and stored directly on your computer's local drive (typically under `%APPDATA%\RG Launcher` and `%APPDATA%\.minecraft` or your configured instance directories):

1. **User Profiles & Game Settings**:
   - Profile configurations (profile name, selected Minecraft version, mod loader type, custom directory paths, resolution settings, allocated RAM heap sizes, and JVM arguments).
2. **Game Files & Downloaded Assets**:
   - Official Minecraft client `.jar` files, libraries, game assets (textures, sounds), fabric/forge loader files, and community mods/modpacks downloaded by your request.
3. **Local Server Hub Data**:
   - Local dedicated server configuration files, world files, server properties, and `.jar` server binaries.
4. **Application & Crash Logs**:
   - Diagnostic log files (`launcher.log`) recording launcher events, startup status, downloaded files, and Minecraft stdout/stderr console output. These logs remain strictly on your local computer unless you manually choose to copy and share them for support.

---

## 3. Microsoft Authentication & Account Tokens

To launch and play Minecraft: Java Edition, RG Launcher integrates with official Microsoft identity services:

1. **Authentication Flow**:
   - When you click "Login with Microsoft", authentication is processed through Microsoft's standard OAuth2 endpoints (`login.live.com` and Xbox Live identity services).
   - RG Launcher does **not** see, intercept, or store your Microsoft account password.
2. **Token Storage**:
   - Upon successful sign-in, the Software receives a time-limited Minecraft session access token and a refresh token directly from Microsoft/Mojang services.
   - These authentication tokens are stored **locally** in your secure application data directory so that you do not need to re-authenticate every time you open the launcher.
3. **Transmission**:
   - Authentication tokens are transmitted **only** to official Microsoft and Mojang authentication servers (`api.minecraftservices.com`, `user.auth.xboxlive.com`) to refresh your session or verify game ownership.
   - **Tokens are NEVER transmitted to RG Studios, third-party analytics services, or unverified servers.**

---

## 4. First-Party Telemetry & Analytics

**RG Studios does NOT collect telemetry or behavioral analytics.**
- We do not track your mouse clicks, play duration, or user habits.
- We do not operate telemetry servers that receive your IP address or session events.
- Crash logs are stored on your local disk only and are never uploaded automatically.

---

## 5. Third-Party Services & Network Communications

To provide Minecraft downloads, mod search, news, and updates, RG Launcher communicates directly with the following third-party services over encrypted HTTPS connections:

| Provider | Purpose | Data Exchanged | Provider Privacy Policy |
| :--- | :--- | :--- | :--- |
| **Mojang / Microsoft** | Game authentication, version manifests, client downloads, official asset downloads | Standard HTTP request headers, IP address, OAuth tokens (auth only) | [Microsoft Privacy Statement](https://privacy.microsoft.com/en-us/privacystatement) |
| **Fabric / Quilt / NeoForge / Forge** | Mod loader version manifests and library downloads | HTTP GET requests, IP address | Respective open-source project privacy policies |
| **Modrinth (Rinth, Inc.)** | Mod, modpack, and shader search, metadata, and file downloads | Search queries, downloaded project IDs, IP address | [Modrinth Privacy Policy](https://modrinth.com/legal/privacy) |
| **CurseForge (Overwolf Ltd.)** | Mod and modpack search, category browsing, and asset downloads | Search queries, downloaded mod IDs, IP address | [Overwolf Privacy Policy](https://www.overwolf.com/legal/privacy) |
| **GitHub (`iamrippon/rg-launcher-releases`)** | Checking for software updates, reading release changelogs | Anonymous HTTP GET request to public release API, IP address | [GitHub Privacy Statement](https://docs.github.com/en/site-policy/privacy-policies/github-general-privacy-statement) |
| **Discord (Local RPC)** | Discord Rich Presence (showing current game status) | Local IPC socket communication with your local Discord client (can be toggled in settings) | [Discord Privacy Policy](https://discord.com/privacy) |

---

## 6. Data Retention, Control & Deletion

Because all personal configurations and tokens reside on your local device:
- **Profile Deletion**: You can delete any profile, mod, or server configuration at any time from within the RG Launcher user interface.
- **Sign Out**: Signing out removes stored authentication tokens from your local storage.
- **Complete Erasure**: You can permanently remove all stored application data, caches, credentials, and settings by uninstalling RG Launcher and manually deleting the folder:
  `%APPDATA%\RG Launcher` (on Windows).

---

## 7. Data Security

We implement reasonable technical safeguards to protect your experience:
- All external network requests use transport-layer encryption (HTTPS/TLS).
- Authentication tokens are handled through standard Electron storage without exposing them in unencrypted logs or URLs.
- *Limitation*: No desktop software or Internet transmission is 100% invulnerable. You are responsible for maintaining the physical and digital security of your personal computer, avoiding untrusted malware, and safeguarding your Microsoft account credentials.

---

## 8. Children’s Privacy

RG Launcher is a general-audience utility for Minecraft players. We do not knowingly collect personal information from children under 13 (or under 16 in certain jurisdictions). Authentication and age-gating are managed directly by Microsoft in accordance with Microsoft Family Safety settings.

---

## 9. Changes to this Privacy Policy

We may update this Privacy Policy from time to time to reflect changes in our software, updates to external APIs, or legal requirements. Updated policies will be committed to this public releases repository with an updated effective date.

---

## 10. Contacting Us

If you have questions, privacy concerns, or data inquiries regarding RG Launcher, please reach out to us at:
- **Developer / Studio**: RG Studios (Ripon Ghosh)
- **Website**: [https://rg-studios.in/](https://rg-studios.in/)
- **Email**: [in.rgstudios@gmail.com](mailto:in.rgstudios@gmail.com)
- **Discord Community**: [https://discord.gg/GFGCn2mMrE](https://discord.gg/GFGCn2mMrE)
