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
| Disk      | 3 GB    | 10 GB       |

Everything runs on your processor, no graphics card needed.

Disk space goes to the program (about 250 MB), the speech recognition
models (about 560 MB, downloaded on first launch) and the model that
writes notes (1.8 GB, downloaded the first time you ask for notes; the
larger ones are 2.5 and 5 GB). Recordings take about 230 MB per hour.

## License

The first 10 meetings work in full. After that you can still view,
search and copy everything; recording new meetings needs a license:
[aisearch.ru/pricing/license/konspekt](https://aisearch.ru/pricing/license/konspekt). Paste the key in
Settings → License. It is checked on your computer, without internet.

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
certutil -hashfile konspekt-0.9.0-setup.exe SHA256
```

A match means the file is exactly the one we built and nothing replaced it
on the way. No match: do not run it, and tell us.

Every installer is scanned by VirusTotal during the build, against some
seventy antivirus engines, and the report link is in the release
description. The scan runs on the build server before publishing, so there
is no step where anyone could quietly skip it.

You can also check that the file was built by us, from our source, rather
than by someone else:

```
gh attestation verify konspekt-0.9.0-setup.exe --repo lamver/konspekt
```

The command names `lamver/konspekt`, the source repository where the build
runs, not this one where releases are published. That is not a typo: the
signature records where a file was built.

## Why Windows complains during install

SmartScreen shows "Windows protected your PC" for any program without a
code signing certificate. Such a certificate costs money and is issued to a
company, which a young project usually does not have. Click "More info",
then "Run anyway".

Antivirus tools sometimes flag PyInstaller builds regardless of what is
inside: honest and malicious programs alike are packaged that way. That is
exactly why we publish checksums, the VirusTotal report and the build
attestation: they can be verified, promises cannot.

If the program is blocked outright and will not start (Defender reports
error 225), the file is intact, it is simply denied permission to run.
Check the checksum first, and only if it matches: "Virus & threat
protection" → "Protection history" → find Konspekt → "Actions" → "Allow on
device".
