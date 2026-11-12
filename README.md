# screenfetch-monokai

[![Latest Release](https://img.shields.io/github/v/release/Frankmau5/screenfetch-watch)](https://github.com/Frankmau5/screenfetch-watch/releases/latest)
[![Platform](https://img.shields.io/badge/Platform-Wear%20OS%20(WFF)-blue)](https://developer.android.com/training/wearables/wff)

A terminal-inspired Wear OS watch face featuring the classic `screenfetch` system info display themed in the Monokai color palette.

Built using the official **Watch Face Format (WFF v1)** for maximum battery efficiency, smoothness, and native Wear OS compatibility.

---

## Preview

<p align="center">
  <img src="screenshot.png" alt="screenfetch-monokai watch face preview" width="300" />
</p>

---

## Features

- **Monokai Color Palette**: Authentic syntax highlighting colors:
  - Green (`#A6E22E`): Terminal command prompt & user account.
  - Pink (`#F92672`): System info labels (`OS:`, `TIME:`, `DATE:`, `BATT:`).
  - Purple (`#AE81FF`): Host name (`wearos`).
  - White (`#F8F8F2`): Host delimiter & OS text.
  - Yellow (`#E6DB74`): 24-hour digital clock.
  - Cyan (`#66D9EF`): Date display.
  - Orange (`#FD971F`): Battery percentage.
- **Terminal System Info**:
  - `user@wearos` host header with divider.
  - `OS`: Wear OS indicator.
  - `TIME`: 24-hour digital time with leading zeros (`[HOUR_0_23_Z]:[MINUTE_Z]`).
  - `DATE`: Current day of the week, month, and day (`[DAY_OF_WEEK_S] [MONTH_S] [DAY]`).
  - `BATT`: Real-time device battery percentage (`[BATTERY_PERCENT]`).
- **Color Swatch Bar**: Six Monokai terminal color blocks aligned flush with the left edge of the system info text.
- **Terminal CLI Header**: Command prompt `user@watch:~$ screenfetch` positioned at the top.
- **Typography**: Powered by the JetBrains Mono typeface for crisp terminal rendering.
- **Declarative Watch Face Format**: Zero background battery drain—rendered natively by the Wear OS Watch Face Format runtime with no custom services or Java code required.

---

## Download

Pre-built signed release APKs are available on the [Releases](https://github.com/Frankmau5/screenfetch-watch/releases) page:

- **[Download screenfetch-monokai v1.0.1 APK](https://github.com/Frankmau5/screenfetch-watch/releases/download/v1.0.1/screenfetch-monokai-v1.0.1.apk)**

---

## Installation & Setup

### 1. Install via ADB
Connect your Wear OS watch (or start an emulator) via ADB, then install the APK:
```bash
adb install -r screenfetch-monokai-v1.0.1.apk
```

### 2. Set as Active Watch Face (ADB)
You can set the watch face active immediately via ADB:
```bash
adb shell am broadcast -a com.google.android.wearable.app.DEBUG_SURFACE --es operation set-watchface --es watchFaceId com.terminal.monokaifetch
adb shell am broadcast -a com.google.android.wearable.app.DEBUG_SYSUI --es operation show-watchface
```

Alternatively, long-press your watch display and choose **screenfetch-monokai** from the watch face picker.

---

## Building from Source

### Prerequisites
- Android SDK (API level 33+ platform tools and build tools)
- Java 17 or Java 21
- Gradle

### Build Commands
```bash
# Build Debug APK
gradle assembleDebug

# Build Signed Release APK
gradle assembleRelease
```

The output APK will be located at:
```text
app/build/outputs/apk/release/app-release.apk
```
