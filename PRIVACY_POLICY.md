# Privacy Policy

> **NOTICE — OWNER REVIEWED AND APPROVED**  
> *Owner reviewed and approved. This Privacy Policy reflects the verified data handling, local storage, cryptographic practices, and network communications of the RG Launcher desktop application, and has been accepted by the project owner/operator, RixStonGamer (SHIPHARUJ). This document has not been reviewed or approved by a qualified lawyer. See [LEGAL_OWNER_REVIEW.md](LEGAL_OWNER_REVIEW.md).*  
> **Effective Date**: October 20, 2026  
> **Applies to**: RG Launcher v1.0.0 and subsequent official releases  
> **Developer & Data Operator**: RixStonGamer (SHIPHARUJ), operating personally as RG Studios (India)  
> **Official Website**: [https://rg-studios.in/](https://rg-studios.in/)  
> **Contact Email**: [in.rgstudios@gmail.com](mailto:in.rgstudios@gmail.com)  
> **Community Discord**: [https://discord.gg/GFGCn2mMrE](https://discord.gg/GFGCn2mMrE)  

---

## 1. Introduction & Operator Identity

1. **Operator Identity**: **RG Launcher is a personal project developed by RixStonGamer (SHIPHARUJ) and released, managed, and maintained under RG Studios.** RG Studios is an **unregistered, personally operated studio and independent project in India, owned and operated solely by RixStonGamer (SHIPHARUJ)** ("Developer", "Operator", "we", "us", "our"). RG Studios is not an incorporated company, Limited Liability Partnership (LLP), or separate legal entity; all operations and software development are conducted by RixStonGamer as an individual developer.
2. **Privacy Philosophy**: RG Launcher (the "Software") is engineered with a privacy-focused, local-first architecture. We do not operate user-surveillance platforms, we do not sell or monetize personal data, and we do not bundle background user tracking or telemetry SDKs.
3. **Purpose of this Policy**: This Privacy Policy explains in clear, plain language:
   - What information is created and stored locally on your personal computer;
   - How your Microsoft authentication credentials and session tokens are protected;
   - What external network requests the launcher performs, why they occur, and what data third-party services receive;
   - How voluntary support tickets are processed;
   - Your choices and controls for deleting your data;
   - The technical security safeguards implemented and their practical limitations.

---

## 2. Information Stored Locally on Your Computer

RG Launcher operates primarily as a local desktop client. The following categories of data are created and stored directly on your personal computer (under `%APPDATA%\RG Launcher` and `%APPDATA%\.minecraft` or your custom instance directories on Windows):

| Data Category | Purpose & Content | Local Storage Mechanism |
| :--- | :--- | :--- |
| **Profile Configurations** | Stores custom profile names, selected Minecraft version, mod loader (Fabric, Quilt, NeoForge, Forge, Vanilla), custom game directory paths, allocated RAM heap sizes, JVM arguments, and window resolution. | Plain JSON configuration files in `%APPDATA%\RG Launcher\profiles.json`. |
| **Authentication Session** | Stores the Microsoft refresh token and basic user identity (username, UUID, skin URL) required to maintain your login session across restarts. | Encrypted at rest in `%APPDATA%\RG Launcher\secure_session.dat` using Windows DPAPI (see Section 3). |
| **Custom Skins Library** | Stores skin PNG image files and local metadata (`skins.json`) that you have imported or chosen to apply to your character. | Local image files in `%APPDATA%\RG Launcher\skins\`. |
| **Server Hub Configurations** | Stores your local dedicated server configurations, server jar references, allocated ports, and memory settings. | Plain JSON configuration files in `%APPDATA%\RG Launcher\servers.json`. |
| **Client Feature Preferences** | Stores your preferences for HUD overlay elements (FPS counter, keystrokes, armor status, coordinates) synced with the bundled companion mod. | Configuration file `config\rg-companion.json` inside each instance directory. |
| **Application & Crash Logs** | Records application events, version download progress, process arguments, and Minecraft game output (`stdout`/`stderr`). | Local text log files in `%APPDATA%\RG Launcher\logs\launcher.log`. Logs remain strictly on your local disk and are never uploaded automatically. |
| **Local Game Cache** | Caches official version manifests, asset indexes, and server status metadata to accelerate launch times and reduce redundant downloads. | Local cache directory `%APPDATA%\RG Launcher\cache\`. |

---

## 3. Microsoft Account Authentication & Token Security

To verify game ownership and launch Minecraft: Java Edition, RG Launcher connects directly to official Microsoft identity services:

### A. The Authentication Flow (PKCE)
1. When you initiate login, RG Launcher generates a secure, random cryptographic code verifier and code challenge using **PKCE (Proof Key for Code Exchange)**.
2. The login window directs you to official Microsoft identity servers (`login.live.com`).
3. You authenticate directly with Microsoft. **RG Launcher never sees, intercepts, logs, or stores your Microsoft account password.**

### B. Token Encryption at Rest
- Upon successful authentication, Microsoft returns an authorization code, which the launcher exchanges for Xbox Live and Minecraft access and refresh tokens.
- To prevent needing to re-authenticate every time you open the launcher, the refresh token is encrypted at rest using the **Windows Data Protection API (DPAPI)** via Electron's `safeStorage` API.
- This encryption is bound to your Windows user account: only your local Windows profile can decrypt the token. In environments where DPAPI is unavailable, the token is stored encoded in local app storage.
- The active in-memory session token is held strictly in the main process memory and is **never sent to the unprivileged renderer interface or written to unencrypted logs**.

### C. Transmission Guarantee
- Authentication tokens are transmitted **only** to official Microsoft and Mojang authentication endpoints (`login.live.com`, `user.auth.xboxlive.com`, `api.minecraftservices.com`) to refresh your session or verify game ownership.
- **Authentication tokens are NEVER transmitted to RixStonGamer, RG Studios, third-party analytics services, or any unverified server.**

---

## 4. Telemetry, Analytics & Crash Reporting

- **No First-Party Telemetry**: RG Launcher contains **zero** embedded analytics, user-tracking, or telemetry SDKs (e.g. no Google Analytics, Sentry, Mixpanel, PostHog, or Segment).
- **No Background Monitoring**: We do not track your gameplay duration, mouse movements, computer hardware telemetry, or browsing behavior.
- **No Automated Crash Transmission**: When a game or launcher crash occurs, crash dumps and log files remain solely on your hard drive. They are never transmitted across the network unless you explicitly and manually choose to share them for troubleshooting.

---

## 5. Voluntary User-Initiated Support Tickets

RG Launcher includes a voluntary **Support View** that allows users to report bugs or suggest ideas directly from the app:

1. **Information Collected**: Only the information you explicitly enter into the support form is transmitted:
   - Request type (Bug report, Idea suggestion, Something else);
   - Summary and detailed description;
   - Up to three (3) optional user-selected image attachments/screenshots (maximum 5 MB each);
   - Basic system diagnostic information: RG Launcher version and operating system platform (e.g. "Windows 10.0 (x64)").
2. **Transmission & Destination**: Support payloads are transmitted over encrypted HTTPS directly to our Supabase Edge Function (`/functions/v1/submit-support-ticket`) for review by RixStonGamer / RG Studios.
3. **User Control**: Submitting a ticket is entirely voluntary. You should never include passwords, financial data, or sensitive personal information in support submissions.

---

## 6. External Third-Party Network Communications

To perform essential functions—such as downloading Minecraft files, searching community mods, checking for updates, and displaying public announcements—RG Launcher communicates with external third-party services over encrypted HTTPS connections.

*Note: As an inherent technical property of all Internet communications, connecting to any external server transmits your IP address and standard HTTP request headers to that server.*

| Service / Provider | Purpose | Data Exchanged | Provider Privacy Policy |
| :--- | :--- | :--- | :--- |
| **Mojang / Microsoft** | Game authentication, version manifests, client/server JARs, assets, skins | OAuth tokens (auth only), standard HTTP headers, IP address | [Microsoft Privacy Statement](https://privacy.microsoft.com/en-us/privacystatement) |
| **Mod Loaders** (Fabric, Quilt, NeoForge, Forge) | Loader version manifests and installer libraries | HTTP GET requests, IP address | Respective open-source project policies |
| **Modrinth** (Rinth, Inc.) | Community mod/modpack search and file downloads | Search queries, project IDs, IP address | [Modrinth Privacy Policy](https://modrinth.com/legal/privacy) |
| **CurseForge** (Overwolf Ltd.) | Community mod/modpack search and file downloads | Search queries, class IDs, IP address | [Overwolf Privacy Policy](https://www.overwolf.com/legal/privacy) |
| **GitHub Releases** (`iamrippon/rg-launcher-releases`) | Automatic and manual software update verification | Anonymous HTTP GET requests to release API, IP address | [GitHub Privacy Statement](https://docs.github.com/en/site-policy/privacy-policies/github-general-privacy-statement) |
| **Supabase** | Fetching public community announcements | Anonymous HTTP GET requests using public anon key, IP address | [Supabase Privacy Policy](https://supabase.com/privacy) |
| **Discord** (Local IPC) | Optional Discord Rich Presence (game activity status) | Local IPC named pipe communication with your local Discord client | [Discord Privacy Policy](https://discord.com/privacy) |
| **Tunneling Providers** (Playit.gg / ngrok) | Optional local multiplayer port-forwarding | Only used if explicitly configured by the user | Respective provider privacy policies |

### Executable Download Protections
When displaying community news or announcements, the launcher validates all announcement links to ensure they use encrypted HTTPS and blocks opening dangerous executable file extensions (`.exe`, `.bat`, `.cmd`, `.msi`, `.ps1`, `.vbs`, `.js`, `.scr`).

---

## 7. Data Retention, Control & Deletion

Because all personal configurations and tokens reside on your local storage, you have complete control over your data:

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
- **URL Sanitization**: News feeds and announcement links are strictly validated to prevent opening dangerous executable files.
- **Update Integrity**: Built-in updates verify file hashes and block execution while game processes are active.

*Security Limitations*: No desktop software or Internet transmission is 100% immune from compromise. Your privacy and security also depend on maintaining the physical security of your computer, keeping your operating system updated, using reputable antivirus protection, and protecting your Microsoft Account credentials.

---

## 9. Children’s Privacy

RG Launcher is a general-audience utility for Minecraft players. We do not knowingly solicit, collect, or process personal data from children under the age of 13 (or under the age of 16 in certain jurisdictions). User authentication is managed directly by Microsoft, which enforces parental consent and Family Safety settings.

---

## 10. Data Protection & Indian Legal Context

> **[LEGAL COUNSEL NOTICE — INDIAN DATA PRIVACY REVIEW]**  
> *RG Studios is operated from India by RixStonGamer (SHIPHARUJ). This document has not been reviewed or approved by a qualified lawyer. Compliance with applicable Indian data protection frameworks (including the Information Technology Act, 2000, associated SPDI Rules, and the Digital Personal Data Protection Act, 2023) is subject to review by a qualified Indian legal practitioner. See [LEGAL_OWNER_REVIEW.md](LEGAL_OWNER_REVIEW.md).*

---

## 11. Changes to this Privacy Policy

We may update this Privacy Policy from time to time to reflect software enhancements, updates to external APIs, or legal developments. When changes are made, the updated document will be published in this public repository with a revised effective date.

---

## 12. Privacy Contact Information

If you have questions, feedback, or concerns regarding your privacy or data practices in RG Launcher, please contact:
- **Developer & Operator**: RixStonGamer (SHIPHARUJ) / RG Studios
- **Email**: [in.rgstudios@gmail.com](mailto:in.rgstudios@gmail.com)
- **Official Website**: [https://rg-studios.in/](https://rg-studios.in/)
- **Community Discord**: [https://discord.gg/GFGCn2mMrE](https://discord.gg/GFGCn2mMrE)
