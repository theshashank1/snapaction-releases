# SnapAction Privacy Policy

**Last updated:** October 29, 2026

SnapAction is a Windows desktop utility for screen capture, local OCR, and privacy
redaction. This policy explains what SnapAction processes, what it stores on your
device, and when data can leave your device.

## 1. Screen captures and clipboard images

SnapAction processes captures in memory. It does not create temporary screenshot
files, and it does not upload a capture anywhere unless you explicitly choose a
cloud AI action (see section 4).

Captured images are kept only for the active snap and are discarded when you
dismiss the result or the auto-dismiss timer expires. If you copy a redacted
image, the result is placed on the Windows clipboard, which is managed by
Windows.

## 2. Local OCR and redaction

OCR, PII detection, and redaction run on your device. The bundled Python engine
binds only to `127.0.0.1` on an ephemeral port and requires a random per-session
token. Other devices cannot reach it.

The local detection stack checks for payment cards, email addresses, phone
numbers, government identifiers, API keys, and other secret patterns. If the
local engine cannot complete a redaction, SnapAction keeps the original image and
reports an error instead of silently sending or copying an unredacted result.

## 3. What SnapAction stores on your device

SnapAction stores only what it needs to run:

- **Settings** in `%APPDATA%\SnapAction\settings.json`, such as your chosen theme,
  provider, model, and auto-dismiss timing. API keys are not stored in plaintext.
- **Encrypted API keys** protected with the Windows Data Protection API (DPAPI)
  through Electron `safeStorage`, tied to your Windows user account.
- **Local model files** downloaded from the official release channel. These are
  model weights, not user content.
- **A diagnostic log** (`snapaction-engine.log`) containing process lifecycle
  events and errors. It does not contain screenshots or clipboard images, and it
  is rotated automatically.

Uninstalling SnapAction removes the application. You can also delete
`%APPDATA%\SnapAction` to remove settings, encrypted keys, models, and logs.

## 4. Optional cloud AI providers

Cloud AI is opt-in. SnapAction contacts a cloud provider only when you select a
cloud action and have configured a key for that provider:

- **Google Gemini** — governed by Google's applicable terms and privacy policy.
- **OpenAI** — governed by OpenAI's applicable terms and privacy policy.

Before a cloud request, SnapAction runs local redaction and sends the sanitized
image and your prompt. The request is authenticated with your own API key. If you
select the **Local** provider, no image or prompt leaves your device.

SnapAction does not operate a proxy service and does not receive copies of your
prompts or images.

## 5. No telemetry or analytics

SnapAction contains no telemetry, analytics, advertising, or behavioral tracking
SDK. It does not send usage events to SnapAction or to third parties.

## 6. Updates

- **Installer builds** check the official GitHub release feed for updates and
  download them over HTTPS.
- **Microsoft Store builds** are updated by the Microsoft Store. SnapAction does
  not run its own updater in Store mode.

## 7. Data sharing

SnapAction does not sell or rent personal data. Data leaves your device only:

- when you explicitly send a capture to a cloud AI provider you configured;
- when the installer or Store client checks for updates; or
- when you open an external link from the app.

## 8. Security

SnapAction uses Windows DPAPI for stored credentials, a per-session localhost
token for the engine, and in-memory processing for captures. No method of
storage or transmission is completely secure, but these controls are designed to
keep sensitive content local by default.

## 9. Children

SnapAction is a general productivity tool and is not directed to children under
13. It does not knowingly collect personal information from children.

## 10. Changes

If this policy changes, the updated version will be published in this repository
with a new "Last updated" date.

## 11. Contact

Questions about this policy or SnapAction's privacy practices:

- Open an issue: <https://github.com/theshashank1/snapaction-releases/issues>
