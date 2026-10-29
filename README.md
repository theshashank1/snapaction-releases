<div align="center">

# ⚡ SnapAction Releases

**Official Distribution & Binary Release Channel for SnapAction**

[![Latest Release](https://img.shields.io/github/v/release/theshashank1/snapaction-releases?style=for-the-badge&logo=github&color=blue)](https://github.com/theshashank1/snapaction-releases/releases/latest)
[![Platform](https://img.shields.io/badge/Platform-Windows%2010%2F11%20(64--bit)-0078D6?style=for-the-badge&logo=windows&logoColor=white)](https://github.com/theshashank1/snapaction-releases/releases/latest)
[![Security Policy](https://img.shields.io/badge/Security-Policy%20%26%20Invariants-green?style=for-the-badge&logo=shield)](SECURITY.md)
[![License: Commercial](https://img.shields.io/badge/License-Commercial%20EULA-yellow.svg?style=for-the-badge)](LICENSE.txt)

<p align="center">
  <a href="#-download--installation">Download</a> •
  <a href="#-security--privacy-highlights">Security & Privacy</a> •
  <a href="#-hotkeys-cheat-sheet">Hotkeys</a> •
  <a href="SECURITY.md">Security Policy</a> •
  <a href="#-release-assets--verification">Release Assets</a>
</p>

</div>

---

## 📥 Download & Installation

### Windows 10 & Windows 11 (64-bit)

Download the official standalone production installer:

👉 **[Download SnapAction-Setup.exe (latest)](https://github.com/theshashank1/snapaction-releases/releases/latest/download/SnapAction-Setup.exe)**

Microsoft Store users receive `SnapAction-<version>.msix` through the Store. Store packages are signed and updated by Microsoft.

#### Installation Instructions:
1. Download **`SnapAction-Setup.exe`**.
2. Run the executable. If prompted by Windows SmartScreen, click **More Info** -> **Run Anyway**.
3. Choose your preferred installation directory and finish setup.
4. SnapAction launches automatically into the Windows System Tray and docks a floating desktop widget.

---

## 🛡️ Security & Privacy Highlights

SnapAction is built with strict, verifiable enterprise privacy invariants:

- **🔒 Zero-Disk RAM Invariant**: Screenshots exist exclusively in volatile RAM memory buffers (`Buffer`/`bytearray`). Zero temporary or cached image files are ever written to your hard drive.
- **⚡ Local Native OCR**: Instant text detection is executed on-device using Windows WinRT `Windows.Media.Ocr` hardware acceleration. No screenshot data is sent across the internet for OCR.
- **🎭 Automated PII Masking**: Credit cards, emails, SSNs, and API keys are automatically detected locally and masked with Gaussian blur or solid blackouts before cloud AI vision models see them.
- **🔐 Hardware-Backed Windows DPAPI**: API keys (OpenAI, Gemini) are protected by the Windows Data Protection API (`CryptProtectData`), cryptographically tied to your hardware TPM and Windows user session.
- **🔄 Differential Auto-Updates**: Bandwidth-efficient differential binary updates via `.blockmap` differential downloads.

For complete architectural proofs, threat models, and compliance alignment (GDPR, HIPAA), read our full specification:  
👉 **[Read the SnapAction Security Policy & Privacy Invariants (SECURITY.md)](SECURITY.md)**

---

## ⌨️ Hotkeys Cheat Sheet

| Shortcut | Action | Description |
| :--- | :--- | :--- |
| `Ctrl + Shift + S` | **Capture & Action** | Freeze screen, capture selection, and trigger the SnapPill overlay. |
| `Alt + Space` | **Toggle Floating Dock** | Show / Hide the floating desk widget or center the tool palette. |
| `PrintScreen` | **Native Snap** | Hook into clipboard capture and inspect recently copied screenshots. |
| `Esc` | **Dismiss Overlay** | Instantly dismiss active preview pill, OCR overlays, or modals. |

---

## 📦 Release Assets & Verification

Every official release includes five published files:

| File Name | Purpose | Description |
| :--- | :--- | :--- |
| [`SnapAction-Setup.exe`](https://github.com/theshashank1/snapaction-releases/releases/latest/download/SnapAction-Setup.exe) | **Full Installer** | Standalone NSIS installer containing the Electron shell and frozen Python engine. |
| [`SnapAction-Setup.exe.blockmap`](https://github.com/theshashank1/snapaction-releases/releases/latest/download/SnapAction-Setup.exe.blockmap) | **Differential Map** | Blockmap binary diff for ultra-fast differential delta updates. |
| `SnapAction-<version>.msix` | **Microsoft Store Package** | Store-format package containing the same app and engine. Microsoft re-signs Store submissions. |
| [`latest.yml`](https://github.com/theshashank1/snapaction-releases/releases/latest/download/latest.yml) | **Update Manifest** | Cryptographic SHA-512 hashes and version verification manifest for auto-updates. |
| [`SHA256SUMS.txt`](https://github.com/theshashank1/snapaction-releases/releases/latest/download/SHA256SUMS.txt) | **Checksums** | SHA-256 hashes for the installer, blockmap, and MSIX package. |

---

## ⚖️ License

SnapAction is commercial, proprietary software distributed under the **[SnapAction Commercial End User License Agreement](LICENSE.txt)**.
