# Privacy Policy

> **NOTICE — DRAFT DOCUMENT FOR QUALIFIED LEGAL REVIEW**  
> *This Privacy Policy is a comprehensive draft prepared specifically for RG Launcher. It reflects the verified data handling, local storage, cryptographic practices, and network communications of the actual application. It is provided for transparency and public documentation, and must be reviewed, finalized, and approved by a qualified legal professional before being treated as final.*  
> **Effective Date**: October 20, 2026  
> **Applies to**: RG Launcher v1.0.0 and subsequent official releases  
> **Developer / Publisher**: RG Studios (Lead Developer: Ripon Ghosh)  
> **Contact**: [in.rgstudios@gmail.com](mailto:in.rgstudios@gmail.com) | [https://rg-studios.in/](https://rg-studios.in/)  

---

## 1. Introduction & Privacy Philosophy

**RG Studios** ("we", "us", "our") develops **RG Launcher** (the "Software") with a strict privacy-first architecture. 

Unlike many commercial gaming utilities, RG Launcher is designed to process and retain your data **locally on your own device**. We do not operate user-surveillance platforms, we do not monetize your personal information, and we do not collect telemetry without your knowledge.

This Privacy Policy explains in precise, factual terms:
- What information is stored on your device;
- How your Microsoft authentication credentials and session tokens are encrypted and handled;
- What network calls the launcher makes to external third-party services;
- How voluntary support tickets are processed;
- Your choices and controls for deleting your data.

---

## 2. Information Stored Locally on Your Computer

RG Launcher operates primarily as a local client. The following categories of data are created and stored directly on your personal computer (by default under `%APPDATA%\RG Launcher` and `%APPDATA%\.minecraft` or your designated instance directories):

| Data Category | File Location / Mechanism | Purpose & Content |
| :--- | :--- | :--- |
| **Profile Configurations** | `%APPDATA%\RG Launcher\profiles.json` | Stores your custom profile names, selected Minecraft version, mod loader (Fabric, Quilt, NeoForge, Forge, Vanilla), custom game directory paths, allocated RAM (heap sizes), JVM arguments, and window resolution. |
| **Encrypted Auth Session** | `%APPDATA%\RG Launcher\secure_session.dat` | Stores your Microsoft refresh token, encrypted with Windows DPAPI (see Section 3), along with your Minecraft username, UUID, and skin URL. |
| **Custom Skins Library** | `%APPDATA%\RG Launcher\skins\` | Stores skin PNG image files and local metadata (`skins.json`) that you have imported or chosen to apply to your character. |
| **Server Hub Configurations** | `%APPDATA%\RG Launcher\servers.json` | Stores your local dedicated server configurations, server jar references, allocated ports, and memory settings. |
| **Client Feature Settings** | Game directory `config\rg-companion.json` | Stores your preferences for HUD overlay elements (FPS counter, keystrokes, armor status, coordinates) synced with the bundled companion mod. |
| **Application & Crash Logs** | `%APPDATA%\RG Launcher\logs\launcher.log` | Records local application lifecycle events, version download statuses, and game process output (stdout/stderr). Diagnostic logs remain on your local drive and are never uploaded automatically. |
| **Local Game Cache** | `%APPDATA%\RG Launcher\cache\` | Caches version manifests, asset indexes, and server status metadata to accelerate startup times and reduce redundant network traffic. |

---

## 3. Microsoft Account Authentication & Token Security

RG Launcher connects to official Microsoft identity services to verify your game ownership and launch Minecraft: Java Edition:

### A. The Authentication Flow (PKCE)
1. When you initiate login, RG Launcher generates a secure, random cryptographic code verifier and code challenge using industry-standard **PKCE (Proof Key for Code Exchange)**.
2. The login window directs you to official Microsoft identity servers (`login.live.com`).
3. You authenticate directly with Microsoft. **RG Launcher never sees, intercepts, logs, or stores your Microsoft account password.**

### B. Token Encryption at Rest (Windows DPAPI)
- Upon successful authentication, Microsoft returns an authorization code, which the launcher exchanges for Xbox Live and Minecraft access/refresh tokens.
- To prevent needing to log in every time you open the launcher, the refresh token is encrypted at rest using the **Windows Data Protection API (DPAPI)** via Electron's `safeStorage` API.
- This encryption is hardware- and user-account-bound: only your Windows user profile can decrypt the token.
- The active in-memory session token is held strictly in the main process memory and is **never sent to the unprivileged renderer interface or written to unencrypted logs**.

### C. Transmission Guarantee
- Authentication tokens are transmitted **only** to official Microsoft and Mojang authentication endpoints (`login.live.com`, `user.auth.xboxlive.com`, `api.minecraftservices.com`).
- **Authentication tokens are NEVER transmitted to RG Studios, third-party analytics services, or any unverified server.**

---

## 4. Telemetry, Analytics & Crash Reporting

- **No First-Party Telemetry**: RG Launcher contains **zero** embedded analytics or tracking SDKs (e.g. no Google Analytics, Sentry, Mixpanel, PostHog, or Segment).
- **No Background Surveillance**: We do not monitor your mouse movements, playtime duration, computer hardware telemetry, or browsing behavior.
- **No Automated Crash Transmission**: When a game or launcher crash occurs, crash dumps and log files remain solely on your hard drive. They are never transmitted across the network unless you explicitly and manually choose to share them for troubleshooting.

---

## 5. Voluntary User-Initiated Support Tickets

RG Launcher includes a voluntary **Support View** that allows users to report bugs or suggest ideas directly from the app:

1. **Information Collected**: Only the information you enter in the form is transmitted:
   - Request type (Bug report, Idea suggestion, Something else);
   - Summary and detailed description;
   - Up to three (3) optional user-selected image attachments/screenshots (maximum 5 MB each);
   - Sanitized basic system information: RG Launcher version and operating system platform (e.g. "Windows 10.0 (x64)").
2. **Transmission & Storage**: Ticket payloads are transmitted via encrypted HTTPS directly to our Supabase Edge Function (`/functions/v1/submit-support-ticket`) for review by RG Studios developers.
3. **User Control**: Submitting a ticket is entirely voluntary. You should never include passwords, financial data, or sensitive personal information in support submissions.

---

## 6. External Third-Party Network Communications

To perform essential functions—such as downloading Minecraft files, searching community mods, checking for updates, and displaying public announcements—RG Launcher communicates with external third-party services over encrypted HTTPS connections:

| Service / Provider | Purpose | Data Exchanged | Provider Privacy Policy |
| :--- | :--- | :--- | :--- |
| **Mojang / Microsoft** | Game authentication, version manifests, client/server jars, assets, skins | OAuth tokens, standard HTTP headers, IP address | [Microsoft Privacy Statement](https://privacy.microsoft.com/en-us/privacystatement) |
| **Mod Loaders** (Fabric, Quilt, NeoForge, Forge) | Loader version manifests and installer libraries | HTTP GET requests, IP address | Respective open-source project policies |
| **Modrinth** (Rinth, Inc.) | Community mod/modpack search and file downloads | Search queries, project IDs, IP address | [Modrinth Privacy Policy](https://modrinth.com/legal/privacy) |
| **CurseForge** (Overwolf Ltd.) | Community mod/modpack search and file downloads | Search queries, class IDs, IP address | [Overwolf Privacy Policy](https://www.overwolf.com/legal/privacy) |
| **GitHub Releases** (`iamrippon/rg-launcher-releases`) | Automatic and manual software update verification | Anonymous HTTP GET requests to release API, IP address | [GitHub Privacy Statement](https://docs.github.com/en/site-policy/privacy-policies/github-general-privacy-statement) |
| **Supabase** | Fetching public community announcements | Anonymous HTTP GET requests using public anon key, IP address | [Supabase Privacy Policy](https://supabase.com/privacy) |
| **Discord** (Local IPC) | Optional Discord Rich Presence (game activity status) | Local IPC named pipe communication with your local Discord client | [Discord Privacy Policy](https://discord.com/privacy) |
| **Tunneling Providers** (Playit.gg / ngrok) | Optional local multiplayer port-forwarding | Only used if explicitly configured by the user | Respective provider privacy policies |

---

## 7. Data Retention, Control & Deletion

Because all personal configurations and tokens reside on your local storage, you have complete sovereignty over your data:

1. **Removing Saved Profiles**: You can delete any profile directly from the launcher interface, which permanently removes the profile metadata and its isolated configuration.
2. **Signing Out**: Clicking "Sign Out" in the launcher immediately purges the DPAPI-encrypted `secure_session.dat` file and clears the active session token from memory.
3. **Complete Local Erasure**: You can permanently and completely delete all RG Launcher data from your computer at any time by:
   - Uninstalling RG Launcher via Windows Settings; and
   - Deleting the directory: `%APPDATA%\RG Launcher`.
4. **Support Ticket Retention**: Voluntary support tickets submitted through the launcher are retained in our secure support database for bug tracking and resolution, after which resolved tickets are periodically purged.

---

## 8. Technical Security Safeguards & Limits

We employ reasonable industry-standard technical safeguards:
- **Encryption in Transit**: All external network communications use TLS/HTTPS encryption.
- **Encryption at Rest**: Stored Microsoft authentication tokens are encrypted using Windows DPAPI.
- **URL Sanitization**: News feeds and announcement links are strictly validated to prevent opening dangerous executable files (`.exe`, `.bat`, `.cmd`, `.ps1`).
- **Update Integrity**: Built-in updates verify file hashes and block execution while game processes are active.

*Security Limitations*: No desktop software or Internet transmission is 100% immune from compromise. Your privacy and security also depend on maintaining the physical security of your computer, keeping your operating system updated, using reputable antivirus protection, and protecting your Microsoft Account credentials.

---

## 9. Children’s Privacy

RG Launcher is a general-audience utility for Minecraft players. We do not knowingly solicit, collect, or process personal data from children under the age of 13 (or under the age of 16 in certain jurisdictions). User authentication is managed directly by Microsoft, which enforces parental consent and Family Safety settings.

---

## 10. Changes to this Privacy Policy

We may update this Privacy Policy from time to time to reflect software enhancements, updates to external APIs, or legal developments. When changes are made, the updated document will be published in this public repository with a revised effective date.

---

## 11. Privacy Contact Information

If you have questions, feedback, or concerns regarding your privacy or data practices in RG Launcher, please contact:
- **Developer / Publisher**: RG Studios (Ripon Ghosh)
- **Email**: [in.rgstudios@gmail.com](mailto:in.rgstudios@gmail.com)
- **Website**: [https://rg-studios.in/](https://rg-studios.in/)
- **Community Discord**: [https://discord.gg/GFGCn2mMrE](https://discord.gg/GFGCn2mMrE)
