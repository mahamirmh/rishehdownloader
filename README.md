# rishehdownloader
# ◆ Risheh Universal Downloader

**One-click universal file downloader for Windows, Android, and iOS.**

[![Version](https://img.shields.io/badge/version-1.0.0-blue)](https://github.com/risheh/RishehUniversalDownloader/releases)
[![Platform](https://img.shields.io/badge/platform-Windows%20%7C%20Android%20%7C%20iOS-lightgrey)](https://github.com/risheh/RishehUniversalDownloader)
[![License](https://img.shields.io/badge/license-MIT-green)](LICENSE)

---

## 📋 Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Downloads](#downloads)
- [Windows](#windows)
- [Android](#android)
- [iOS](#ios)
- [Update Policy](#update-policy)
- [Repository Structure](#repository-structure)
- [Contributing](#contributing)
- [License](#license)

---

## Overview

Risheh Universal Downloader is a production-ready, cross-platform solution for downloading files from any public URL. It features automatic file type detection, batch processing, progress tracking, and seamless auto-update functionality across all platforms.

**Key Highlights:**
- 🎯 **Universal Compatibility** — Works on Windows, Android, and iOS
- 🔍 **Smart Detection** — Automatically detects file types (text, audio, video, image, template, archive, document)
- 📦 **Batch Downloads** — Process multiple links simultaneously
- 📊 **Live Progress** — Real-time download progress and speed indicators
- 🔄 **Auto-Update** — Silent background update checks with one-click installation
- 🎨 **Dark Minimal UI** — Consistent branded experience across all platforms

---

## Features

| Feature | Windows | Android | iOS |
|---------|---------|---------|-----|
| Single URL Download | ✅ | ✅ | ✅ |
| Batch Download (Multiple URLs) | ✅ | ✅ | ✅ |
| Auto File Type Detection | ✅ | ✅ | ✅ |
| Progress Indicator | ✅ | ✅ | ✅ |
| Download Speed Display | ✅ | ⚠️ | ⚠️ |
| Error Handling | ✅ | ✅ | ✅ |
| Auto-Update | ✅ | ✅ | ✅ |
| One-Click Execution | ✅ | ✅ | ✅ |
| Dark Minimal UI | ✅ | ✅ | ✅ |
| Background Service | ✅ | ❌ | ❌ |

---

## Downloads

### Latest Release: v1.0.0 (2026-05-02)

| Platform | Download | Size | Installer |
|----------|----------|------|-----------|
| **Windows** | [RishehDownloader-Windows.zip](https://github.com/risheh/RishehUniversalDownloader/releases/download/v1.0.0/RishehDownloader-Windows.zip) | ~15 MB | Setup.exe |
| **Android** | [RishehUniversalDownloader.apk](https://github.com/risheh/RishehUniversalDownloader/releases/download/v1.0.0/RishehUniversalDownloader.apk) | ~8 MB | APK |
| **iOS** | [RishehUniversalDownloader.ipa](https://github.com/risheh/RishehUniversalDownloader/releases/download/v1.0.0/RishehUniversalDownloader.ipa) | ~12 MB | IPA |

> **Note:** iOS requires sideloading via AltStore, Sideloadly, or enterprise distribution.

---

## Windows

### Quick Start

1. Download `RishehDownloader-Windows.zip` from [Releases](https://github.com/risheh/RishehUniversalDownloader/releases)
2. Extract to your preferred location
3. Run `Setup.exe` for installation (creates Start Menu shortcuts)
4. Or run `Start.exe` directly for portable mode
5. Paste URLs and click **Download**

### System Requirements

- Windows 10/11 (64-bit)
- Python 3.8+ (bundled in installer)
- 50 MB disk space
- Internet connection

### Files

```
windows/
├── Start.exe          # Main launcher
├── Stop.exe           # Terminate background service
├── src/
│   └── main.py        # Core application
├── assets/
│   └── logo.ico       # Application icon
└── README.md
```

### Auto-Update

Start.exe automatically checks `update/latest.json` on GitHub at launch. If a new version is available, users are prompted to download and install the new Setup.exe.

[→ Windows README](windows/README.md)

---

## Android

### Quick Start

1. Download `RishehUniversalDownloader.apk` from [Releases](https://github.com/risheh/RishehUniversalDownloader/releases)
2. Enable "Install from Unknown Sources" in Settings
3. Install the APK
4. Grant storage permissions on first launch
5. Paste URLs and tap **Download**

### System Requirements

- Android 5.0+ (API 21+)
- 20 MB storage space
- Internet connection
- Storage permission

### Files

```
android/
├── app/src/main/java/com/risheh/downloader/
│   └── MainActivity.java
├── app/src/main/res/
│   ├── layout/
│   ├── values/
│   └── drawable/
├── build.gradle
└── README.md
```

### Auto-Update

The app checks `update/latest_mobile.json` on GitHub at startup. Users receive a notification dialog when an update is available, with a direct link to download the new APK.

[→ Android README](android/README.md)

---

## iOS

### Quick Start

1. Download `RishehUniversalDownloader.ipa` from [Releases](https://github.com/risheh/RishehUniversalDownloader/releases)
2. Install using [AltStore](https://altstore.io/) or [Sideloadly](https://sideloadly.io/)
3. Open the app
4. Paste URLs and tap **Download**

### System Requirements

- iOS 15.0+
- 25 MB storage space
- Internet connection

### Files

```
ios/
├── RishehUniversalDownloader.xcodeproj/
├── RishehUniversalDownloader/
│   ├── ContentView.swift
│   ├── Info.plist
│   └── Assets.xcassets/
└── README.md
```

### Auto-Update

The app checks `update/latest_mobile.json` on GitHub at startup. Users receive an alert when an update is available, with a direct link to download the new IPA.

[→ iOS README](ios/README.md)

---

## Update Policy

### Versioning

We follow [Semantic Versioning](https://semver.org/):
- **MAJOR**: Breaking changes requiring manual intervention
- **MINOR**: New features, backward compatible
- **PATCH**: Bug fixes and security updates

### Update Channels

| File | Platform | Purpose |
|------|----------|---------|
| `update/latest.json` | Windows | Version, download URL, changelog, mandatory flag |
| `update/version.txt` | Android | Version + download URL (legacy support) |
| `update/version_ios.txt` | iOS | Version + download URL (legacy support) |
| `update/latest_mobile.json` | Android + iOS | Unified mobile update manifest |

### Update Behavior

- **Silent Check**: Performed automatically at app launch
- **User Prompt**: Dialog shown only when update is available
- **Mandatory Updates**: Can be enforced via `mandatory: true` in JSON
- **Rollback**: Previous versions remain accessible in GitHub Releases

---

## Repository Structure

```
RishehUniversalDownloader/
├── windows/              # Windows application source
│   ├── src/
│   ├── assets/
│   ├── Start.py
│   ├── Stop.py
│   ├── build.py
│   ├── installer.nsi
│   └── README.md
├── android/              # Android application source
│   ├── app/src/main/
│   ├── build.gradle
│   └── README.md
├── ios/                  # iOS application source
│   ├── RishehUniversalDownloader.xcodeproj/
│   ├── RishehUniversalDownloader/
│   └── README.md
├── installer/            # Compiled installer output
├── update/               # Auto-update manifests
│   ├── latest.json
│   ├── version.txt
│   ├── version_ios.txt
│   └── latest_mobile.json
├── assets/               # Shared branding assets
│   └── logo.svg
├── docs/                 # Additional documentation
├── README.md             # This file
└── LICENSE
```

---

## Contributing

We welcome contributions! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

### Development Setup

**Windows:**
```bash
cd windows
python build.py
```

**Android:**
```bash
cd android
./gradlew assembleRelease
```

**iOS:**
```bash
cd ios
xcodebuild -project RishehUniversalDownloader.xcodeproj -scheme RishehUniversalDownloader -configuration Release
```

---

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

```
MIT License

Copyright (c) 2026 Risheh Technologies

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

---

## Support

- 🐛 **Bug Reports**: [GitHub Issues](https://github.com/risheh/RishehUniversalDownloader/issues)
- 💡 **Feature Requests**: [GitHub Discussions](https://github.com/risheh/RishehUniversalDownloader/discussions)
- 📧 **Email**: support@rishehcompany.ir

---

<p align="center">
  <strong>◆ Risheh Universal Downloader</strong><br>
  <em>Download anything, anywhere, anytime.</em>
</p>
