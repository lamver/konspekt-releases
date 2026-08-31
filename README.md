# Konspekt

Konspekt is a smart notes app for meetings. It records the call, transcribes it, turns your scribbled notes into proper summary. Everything runs 100% locally on your machine. No audio or transcripts ever leave your computer.

This repo holds public releases, documentation and issue tracker. Source code is in a separate private repository.

---

[🇷🇺 Русский](#русский) · [🇪🇸 Español](#español) · [🇷🇸 Српски / Srpski](#српски--srpski)

---

## Download

Windows 10 / 11, 64-bit: latest stable release on the [Releases](https://github.com/lamver/konspekt-releases/releases/latest) page.

Download `konspekt-X.Y.Z-setup.exe` and run it. No admin rights required. The program installs into your user profile.

## SmartScreen warning

When you run the installer, Windows will show a blue screen "Windows protected your PC". This happens to any program without an expensive code signing certificate. Click "More info" → "Run anyway".

We understand this looks bad, because Konspekt does exactly the same things as spyware: it records your microphone, listens to system audio and intercepts global hotkeys. That is why we do not ask you to trust us. Every release comes with independent proofs of origin:

### Verify the build

**VirusTotal report.** A link to full VirusTotal scan is included with every release. We publish it unmodified, regardless of result. It is normal for PyInstaller builds to get a handful of false positives.

**Build provenance.** The installer is signed by GitHub. You can verify that this exact file was built by our public workflow from our source code:

```
gh attestation verify konspekt-0.1.0-setup.exe --owner lamver
```

**Checksum.** `SHA256SUMS` file is attached to every release. Compare with your downloaded file:

```
certutil -hashfile konspekt-0.1.0-setup.exe SHA256
```

## Network usage

Almost nothing leaves your computer by default.

| Activity | When | Can be disabled |
|----------|------|-----------------|
| Check for updates | Once per day, a simple static file request | Yes, in settings |
| Download model files | Once, on first use of recognition | Manual download is available |

Recording, transcription, speaker identification and local LLM run entirely offline. Audio and transcripts are never sent anywhere, ever.

If you explicitly configure an external LLM provider with your own API key, meeting text will be sent there. This is your conscious choice, and it is not enabled by default.

## Pricing

Recording, transcription, speaker identification, local models, export and data deletion are **always free, forever, no limits**.

Only use of external LLM providers requires a license. We charge for the convenience of routing, not for the software itself.

## System requirements

- Windows 10 or 11, 64-bit
- 8 GB RAM for transcription, 16 GB for local LLM
- ~ 2 GB disk space with all models

## Found an issue?

Please open an issue in this repository. Include the program version from the About page, and if you can:

```
%LOCALAPPDATA%\Konspekt\konspekt.log
```

Do **not** send audio, transcripts or meeting notes. We never need them to debug the program.

---

## Русский

Konspekt — умный блокнот для встреч. Записывает разговор, расшифровывает и превращает ваши пометки в связное саммари. Всё работает целиком на вашем компьютере. Аудио и транскрипты никуда не уходят никогда.

В этом репозитории готовые сборки, документация и трекер ошибок. Исходный код в отдельном репозитории.

### Скачать

Windows 10 / 11, 64 бита: последняя стабильная сборка на странице [Releases](https://github.com/lamver/repo/releases/latest).

Скачайте `konspekt-X.Y.Z-setup.exe` и запустите. Права администратора не нужны, программа ставится в профиль пользователя.

### Нашли ошибку?

Заведите issue в этом репозитории. Приложите версию программы из раздела «О программе» и, если можно, файл журнала:

```
%LOCALAPPDATA%\Konspekt\konspekt.log
```

Аудио, транскрипты и заметки к issue прикладывать не нужно. Они нам никогда не требуются для отладки.

---

## Español

Konspekt es una aplicación de notas inteligente para reuniones. Graba la llamada, la transcribe y convierte tus apuntes en un resumen completo. Todo funciona 100% localmente en tu máquina. Ningún audio ni transcripción sale nunca de tu ordenador.

En este repositorio están las versiones publicadas, documentación y seguimiento de errores. El código fuente está en un repositorio separado.

### Descargar

Windows 10 / 11, 64 bits: última versión estable en la página [Releases](https://github.com/lamver/repo/releases/latest).

Descarga `konspekt-X.Y.Z-setup.exe` y ejecútalo. No se necesitan derechos de administrador. El programa se instala en tu perfil de usuario.

---

## Српски / Srpski

Konspekt je pametna aplikacija za bilješke na sastancima. Snima poziv, transkribuje ga i pretvara vaše brze bilješke u čitljiv sažetak. Sve funkcionalnosti rade isključivo lokalno na vašem računaru. Zvuk i transkripti nikada ne napuštaju vaš računar.

U ovom repozitorijumu se nalaze javne izdanja, dokumentacija i otvaranje problema. Izvorni kod je u zasebnom repozitorijumu.

### Preuzimanje

Windows 10 / 11, 64-bit: poslednje stabilno izdanje na stranici [Releases](https://github.com/lamver/repo/releases/latest).

Preuzmite `konspekt-X.Y.Z-setup.exe` i pokrenite. Nisu potrebne administratorske privilegije. Program se instalira u vaš korisnički profil.

---
