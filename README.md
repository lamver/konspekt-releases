# Konspekt

<p align="center">
  <img width="128" height="128" src="https://raw.githubusercontent.com/lamver/konspekt-releases/master/assets/icon-256.png" alt="Konspekt logo">
</p>

<p align="center">
  <b>Smart notes app for meetings</b>
</p>

---

<p align="center">
  Records your calls, transcribes them, turns your scribbled notes into a proper summary.
  <br>
  Everything runs 100% locally. No audio or transcripts ever leave your computer.
</p>

---

<p align="center">
  <a href="https://github.com/lamver/konspekt-releases/releases/latest"><b>Download latest version</b></a>
</p>

<p align="center">
  <a href="https://github.com/lamver/konspekt-releases/blob/master/docs/README.ru.md">Русский</a>
  ·
  <a href="https://github.com/lamver/konspekt-releases/blob/master/docs/README.es.md">Español</a>
  ·
  <a href="https://github.com/lamver/konspekt-releases/blob/master/docs/README.sr.md">Srpski</a>
  ·
  <a href="https://github.com/lamver/konspekt-releases/issues">Report an issue</a>
</p>

---

## What you need

Windows 10 or 11, 64-bit.

|           | Minimum | Comfortable |
| --------- | ------- | ----------- |
| Processor | 2 cores | 4 cores     |
| Memory    | 4 GB    | 8 GB        |
| Disk      | 1 GB    | 4 GB        |

Everything runs on your processor, no graphics card needed. Speech
recognition keeps up with room to spare: even on a single core it
transcribes five times faster than people speak.

Disk space goes mostly to models, downloaded on first launch: 214 MB for
speech recognition, plus about 1.8 GB if you want summaries written by
the built-in language model.

## Found an issue?

Please open an issue in this repository. Include:
1. Program version from the About page
2. Log file at: `%APPDATA%\Konspekt\konspekt.log`

Do **not** send audio, transcripts or meeting notes. We never need them to debug the program.

## Verify what you downloaded

Konspekt records your microphone, listens to system audio and intercepts
hotkeys. From the outside that is exactly how spyware behaves, so our own
"we checked, it's clean" is worth nothing. Check it yourself, it is one
command.

Every release ships a `SHA256SUMS` file next to the installer. Compare the
line in it with what Windows computes:

```
certutil -hashfile konspekt-0.4.0-setup.exe SHA256
```

A match means the file is exactly the one we built and nothing replaced it
on the way. No match: do not run it, and tell us.

## Why Windows complains during install

SmartScreen shows "Windows protected your PC" for any program without a
code signing certificate. Such a certificate costs money and is issued to a
company, which a young project usually does not have. Click "More info",
then "Run anyway".

Antivirus tools sometimes flag PyInstaller builds regardless of what is
inside: honest and malicious programs alike are packaged that way. That is
exactly why we publish checksums: they can be verified, promises cannot.
