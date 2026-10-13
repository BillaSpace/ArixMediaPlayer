<div align="center">

<img src="docs/assets/icon.png" width="112" alt="Arix Media Player icon" />

# Arix Media Player

**Only Media Player with CD-R | XR BD-DVD BLURAY playback support through USB Drives for Android phones and Android TV**

[![Platform](https://img.shields.io/badge/Platform-Android%20%7C%20Android%20TV-3DDC84?logo=android&logoColor=white)](#)
[![Min SDK](https://img.shields.io/badge/Min%20SDK-24%20(Android%207.0)-blue)](#)
[![Target SDK](https://img.shields.io/badge/Target%20SDK-34-blue)](#)
[![Version](https://img.shields.io/badge/Version-2.0%20beta-orange)](#)
[![ABI](https://img.shields.io/badge/ABI-arm64--v8a%20%7C%20armeabi--v7a-informational)](#)
[![Source](https://img.shields.io/badge/Source-Closed%20for%20now-lightgrey)](#project-status)
[![Release](https://img.shields.io/badge/GitHub%20%26%20Play%20Store-Coming%20soon-success)](#project-status)

[Repository: BillaSpace/ArixMediaPlayer](https://github.com/BillaSpace/ArixMediaPlayer)

</div>

---

## 📌 Project status ( launching soon )

| | |
|---|---|
| **Source code** | Closed for now. Opening it up is something we will think about in the future. |
| **Releases** | Public builds on **GitHub** and the **Google Play Store** are coming soon. |
| **State** | 2.0 beta. Features below are the ones built into the app; a beta can still have rough edges. |

---

## ✨ What it is

Arix Media Player is a media player for Android phones and Android TV. It plays video and music from local storage, USB drives, home networks and streams, and it can read **discs and disc images from USB drives** (CD-R, DVD and Blu-ray media) like a small disc player.

It is built for the TV remote first: every screen works with D-pad, OK and Back, and also with touch and a pointer.

<details>
<summary><b>💿 Disc playback from USB drives</b></summary>

<br/>

Plug in a USB disc drive or a USB stick and Arix reads it by itself, without another app.

- 🎵 **Audio CD / CD-R**: tracks listed and played from the drive
- 📀 **Video CD**: MPEG-1 video from the disc, track by track
- 📀 **DVD-Video** (also DVD-R / DVD-RW): main title, titles and chapters in the player menu
- 💠 **Blu-ray** (BDMV): main title playback
- 🗂️ **Disc images** (`.iso`, `.img`, `.udf`): opened like a drive, with their folders listed
- 💾 Drives and sticks formatted **FAT32, exFAT, NTFS** and **UDF / ISO 9660** discs are read by the app itself
- 🔁 A disc that stalls is read again from where it stopped

> Arix plays discs and images that can be read as they are. It does not remove copy protection from discs.

</details>

<details>
<summary><b>🎬 Video formats</b></summary>

<br/>

**Containers**

| Family | Extensions |
|---|---|
| MPEG-4 / QuickTime | `mp4` `m4v` `mov` `f4v` `3gp` `3g2` |
| Matroska / WebM | `mkv` `webm` |
| AVI | `avi` `divx` |
| MPEG transport stream | `ts` `tp` `trp` `mts` `m2ts` |
| MPEG program stream / Video CD | `mpg` `mpeg` `mpe` `m1v` `m2v` `vob` `dat` |
| Flash video | `flv` |
| Ogg | `ogv` `ogm` `ogx` |
| Windows Media, RealMedia and more | `wmv` `asf` `rm` `rmvb` and others, through the universal engine |

**Video codecs:** H.264 / AVC, H.265 / HEVC, VP8, VP9, AV1, MPEG-4 Part 2, MPEG-1 / MPEG-2, MJPEG and more. Hardware decoding is used where the device has it; AV1 also has a software decoder for devices without one.

**Subtitles:** embedded tracks and external subtitle files, with style options.

</details>

<details>
<summary><b>🎧 Audio formats</b></summary>

<br/>

| Type | Formats |
|---|---|
| Lossy | MP3, MP2, AAC / HE-AAC, Ogg Vorbis, Opus, AMR-NB / AMR-WB, WMA |
| Lossless | FLAC, ALAC (Apple Lossless), APE, WAV / PCM, WavPack |
| Surround | AC-3, E-AC-3 (Digital Plus, JOC), TrueHD / MLP, DCA |
| Containers | `mka`, `m4a`, `m4b`, `ogg`, `oga`, `opus`, `wav`, `aac`, `ac3`, `eac3`, `dts`, `amr`, `awb`, `mp2`, `mp3`, `flac`, `wma`, `ape`, `alac` and more through the universal engine (`wv`, `mpc`, `tta`, `aif`, `aiff`, `dsf`, `dff`, `caf`) |

**Surround and metadata**

- Channel layouts from mono up to 7.1 and beyond are shown correctly: 2.1, 5.1, 6.1, 7.1, 9.1, 11.1
- Surround streams can be sent to an AV receiver as they are (passthrough) when the TV or receiver supports it, or decoded inside the app
- Codec, sample rate, bit depth, bitrate and channel layout are shown for the playing track, with title, artist, album and cover art
- Audio delay (sync) control, equalizer and a bit-perfect mode

</details>

<details>
<summary><b>🌐 Streams and network sources</b></summary>

<br/>

- HLS (`m3u8`), MPEG-DASH (`mpd`), progressive HTTP / HTTPS
- RTMP and other live stream addresses
- **SMB** (Windows shares), **WebDAV** and **UPnP / DLNA** servers
- FTP, SFTP and NFS addresses through the universal engine
- Remembered logins for network shares
- Automatic retry for short connection problems

</details>

<details>
<summary><b>🔐 Protected streams (DRM)</b></summary>

<br/>

Android provides the DRM system for apps (the platform `MediaDrm` / Widevine components that Google makes available for player apps to implement), and Arix uses those platform interfaces for streams that need them.

- Widevine and ClearKey licence handling through Android's own DRM APIs
- Secure decoders where the device offers them
- Playback needs a valid licence from the content provider; Arix does not bypass or remove any protection

</details>

<details>
<summary><b>🧩 Universal engine for other formats</b></summary>

<br/>

When the main player cannot open a file (an uncommon container or codec), Arix hands it over, with the current position, to a **separate universal engine** based on the open-source LibVLC library. It runs in its own process, so the memory is returned when it closes and the main player is not affected.

- Playback controls: seek, pause, audio track, subtitle track, speed
- It is used only when it is needed

</details>

<details>
<summary><b>📲 Open with and Share</b></summary>

<br/>

Arix appears in Android's **Open with** and **Share** menus:

- Video and audio files from file managers, downloads and other apps (many extensions, upper and lower case)
- Shared files, several shared songs at once (played as a queue), and links shared as text
- Web, stream and network addresses (`http`, `https`, `rtsp`, `rtmp`, `smb`, `ftp`, `sftp`, `nfs`, ...)
- The real file name is shown for files shared by other apps

</details>

<details>
<summary><b>📺 Made for Android TV, works on phones</b></summary>

<br/>

- Remote-first screens with clear focus, plus pointer (air mouse) and touch support
- Picture-in-picture, resume position, history and playlists
- Light on memory, tuned for TVs with 1–2 GB RAM
- Separate builds for **arm64-v8a** and **armeabi-v7a**, so each APK carries only the libraries its CPU needs

</details>

<details>
<summary><b>🛠️ Building</b></summary>

<br/>

Build notes are in [`tools/README_BUILD.md`](tools/README_BUILD.md). The build produces one APK per CPU type:

```
build/Arix-Player-TV-v8a-debug.apk   # arm64-v8a
build/Arix-Player-TV-v7a-debug.apk   # armeabi-v7a
```

Pick the one that matches your device (`arm64-v8a` for most current phones and TVs; `armeabi-v7a` for older 32-bit devices).

</details>

<details>
<summary><b>⚖️ Open-source components and notices</b></summary>

<br/>

Arix uses these open-source libraries, each under its own licence (also listed with links inside the app, under Legal):

AndroidX Media3 (Apache-2.0) · FFmpeg audio decoders (LGPL-2.1+) · LibVLC by VideoLAN (LGPL-2.1+) · jcifs-ng (LGPL-2.1) · Bouncy Castle · SLF4J · Glide · Material Components · Gson · ZXing

Product, format and company names are trademarks of their owners and are used here only to describe which files the player can open. Arix is an independent project and is not affiliated with or endorsed by any of them. Use the app only with content you own or have the right to play.

</details>

---
<div align="center">
  <sub>© 2026 Arix Player · BillaSpace. All rights reserved. Proprietary software.</sub>
</div>
