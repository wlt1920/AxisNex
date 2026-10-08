Language: English | [Română](docs/README_RO.md)

<p align="center">
  <img src="docs/banner.jpg" alt="AxisNex — controller tuning and calibration for Windows">
</p>

<h1 align="center">AxisNex</h1>

<p align="center">
  <b>Controller tuning and calibration for Windows.</b><br>
  Fine-tune deadzones, response and controller profiles.<br>
  by <b>wLt</b> · <a href="https://wltziff.nl">wltziff.nl</a>
</p>

<p align="center">
  <a href="https://github.com/wlt1920/AxisNex/releases/latest"><img src="https://img.shields.io/github/v/release/wlt1920/AxisNex?style=for-the-badge&label=%E2%AC%87%20%20DOWNLOAD&color=2f6bff&labelColor=1a3fbf" height="46" alt="Download the latest AxisNex"></a>
</p>
<p align="center">
  <sub><b><!--downloads-->22<!--/downloads--></b> downloads &nbsp;·&nbsp; Windows 10 / 11 (64-bit) &nbsp;·&nbsp; Free</sub>
</p>

> **AxisNex is an independent project and is not affiliated with, endorsed by, or sponsored by Sony Interactive Entertainment, Epic Games, Psyonix, or any controller or game manufacturer. All trademarks belong to their respective owners.**

<p align="center">
  <a href="https://github.com/wlt1920/AxisNex/releases/latest"><b>⬇ Download the latest version</b></a> · <a href="CHANGELOG.md"><b>What's new in each update</b></a>
</p>

## What's new in V1.3

<table>
  <tr>
    <td width="50%" valign="top"><img src="docs/v1.3/profiles.png" alt="Profiles page"><br><b>Your own profiles.</b> Create, copy and rename profiles, and export them to a file to share with friends or keep as a backup.</td>
    <td width="50%" valign="top"><img src="docs/v1.3/home-difference.png" alt="See the difference"><br><b>See the difference.</b> The white ring shows where your stick would land with the original values, live, with a plain-words list of what changed.</td>
  </tr>
  <tr>
    <td width="50%" valign="top"><img src="docs/v1.3/tuning.png" alt="Advanced tuning live preview"><br><b>Live before and after.</b> Advanced tuning shows saved vs new values in real time, with a reset button on every value.</td>
    <td width="50%" valign="top"><img src="docs/v1.3/controller.png" alt="Controller page"><br><b>Name your controller.</b> AxisNex recognizes it automatically, over USB or Bluetooth, and greets it by name.</td>
  </tr>
</table>

Also new: **✕ keeps AxisNex running next to the clock** (right-click → Exit to close), a clear red message under START when no controller is connected, a welcome animation, and a fix for Windows menus scrolling on their own. **[Full list with pictures →](CHANGELOG.md)**


<p align="center">
  <a href="docs/AxisNex-promo.mp4"><img src="docs/promo-poster.jpg" width="240" alt="AxisNex in 50 seconds: watch the video"></a><br>
  <b>▶ <a href="docs/AxisNex-promo.mp4">AxisNex in 50 seconds</a></b> (video, with sound)
</p>

---

AxisNex reads your physical controller, applies your deadzone, response and trigger settings, and gives games a single virtual controller with those settings applied. The physical controller is hidden from games while AxisNex is running, so the game doesn't see two controllers.

AxisNex is free. It does not modify games and does not run inside them.

**What it helps with**

- **Stick drift and an off-center resting position.** A short calibration measures how much each stick moves on its own and where it rests, corrects the center and sets the smallest deadzone that covers it — instead of guessing a large one.
- **Worn sticks or triggers that no longer reach 100%.** Calibration measures how far each direction and trigger actually goes, so full output is still reached.
- **Inconsistent stick input and stacked deadzones.** One place for deadzone, response curve and trigger settings, plus recommended in-game values so the game's own deadzone doesn't add on top.
- **Rocket League on PC with a DualSense.** The built-in profiles and the Game settings page are made with Rocket League in mind; the deadzone and calibration tuning itself is not game-specific.

[Features](#features) · [Requirements](#requirements) · [Installation](#installation) · [Getting started](#getting-started) · [Calibration & profiles](#calibration-and-profiles) · [Troubleshooting](#troubleshooting) · [FAQ](#faq) · [Privacy](#privacy) · [Security](#security)

## Features

<p align="center">
  <img src="docs/screenshot.png" width="860" alt="AxisNex V1.3 Home page: connect, pick a profile, START and calibrate, with live stick view">
</p>

- **One controller in game.** The physical controller is hidden from games with [HidHide](https://github.com/nefarius/HidHide), and a virtual controller ([HIDMaestro](https://github.com/hifihedgehog/HIDMaestro)) receives your tuned input. Stopping AxisNex makes the physical controller visible again.
- **Guided calibration (about 15 seconds).** Rest, roll both sticks around the edge, let go. AxisNex measures resting drift, the center of each stick, how far each stick reaches and both triggers, then proposes the smallest deadzone that covers the measured drift. You see the result before anything is saved.
- **Manual tuning.** Deadzone shape (radial, axial, hybrid, square), inner and outer deadzone, anti-deadzone, response curve, sensitivity, smoothing, diagonal stability, square output, and trigger ranges and curves.
- **Profiles.** 4 built-in profiles (Pro, Freestyle, Aerial, Worn Controller) plus your own: create, duplicate, rename, delete, and **export / import** them as `.axisnex` files. Calibration and changes are saved into the active profile; built-in profiles can be reset to their original values.
- **Live before / after.** *See the difference* on Home compares your profile with its original values while you move the sticks; Advanced tuning shows saved vs new values live, with a reset on every value.
- **Your controller, by name.** AxisNex recognizes each controller by its own ID (USB or Bluetooth) and shows the name you gave it.
- **Runs in the background.** Closing the window keeps AxisNex next to the clock so your controller stays tuned; right-click the icon to switch profiles or exit.
- **1000 Hz USB polling.** Over a USB cable, AxisNex can set the controller's polling interval from 4 ms (250 Hz, the default) to 1 ms (1000 Hz) with the Microsoft-signed [hidusbf](https://github.com/LordOfMice/hidusbf) driver by SweetLow. It can be switched off, and it is removed from the controller when you uninstall. This changes how often Windows reads the controller; it is not possible over Bluetooth. The live input rate is shown on the Home page.
- **Game settings page** with recommended in-game values, so the game's deadzone doesn't stack on top of AxisNex's.
- **Game rules page** (optional) that watches the game publisher's fair-play terms for changes and lists official news and player threads about the anti-cheat.
- **11 languages** (English, Română, Deutsch, Español, Français, Italiano, Português, Nederlands, Polski, Türkçe, Русский) and 9 color themes.
- **Built-in updates.** AxisNex can check GitHub for a new version, show its release notes, download the installer, verify its SHA-256 and install it. Automatic checks can be turned off.

**Advanced tuning is not fully tested yet.** If you try it, [feedback](https://github.com/wlt1920/AxisNex/issues/new) is welcome.

## Requirements

- Windows 10 or Windows 11, 64-bit.
- Administrator rights (for the installation and the drivers, see [Security](#security)).
- A supported controller: currently the **DualSense Wireless Controller**, connected by USB cable or Bluetooth. Other controllers are not supported yet.
- For 1000 Hz polling: a USB **data** cable (charge-only cables don't work).
- An internet connection only for the optional update check and Game rules page.

## Installation

> [!IMPORTANT]
> **Restart Windows after installing AxisNex for the first time.**
> The drivers for the virtual controller and for hiding the physical controller only load after a restart.

1. Download the latest **`AxisNex-…-Setup.exe`** from [Releases](https://github.com/wlt1920/AxisNex/releases/latest). Official downloads are **only** on this GitHub page and on [wltziff.nl](https://wltziff.nl).
2. Optional: compare the installer's SHA-256 with the value in the release notes (PowerShell: `Get-FileHash .\AxisNex-…-Setup.exe`).
3. Run the installer and confirm the Windows administrator prompt. The installer is not code-signed, so Windows SmartScreen may show "Unknown publisher".
4. Pick your language and accept the license.
5. The installer sets up AxisNex, [HidHide](https://github.com/nefarius/HidHide) (if it isn't installed yet), the virtual-controller driver and the 1000 Hz USB driver.
6. On the last page, **Restart required** appears. Choose **Restart now** and click *Finish*, or choose **Restart later** and restart before using AxisNex.
   If you open AxisNex before restarting, it shows **Restart recommended** once per Windows session until you restart.

Updates installed from inside the app keep your profiles, calibration and settings.

**Uninstalling:** use *Settings → Apps* (or Programs & Features). The uninstaller takes the 1000 Hz driver off the controller and removes AxisNex from HidHide's allowed apps. HidHide itself, the HIDMaestro driver certificate (see [Security](#security)) and your profiles in `%APPDATA%\Input Zero` are left in place; remove them yourself if you no longer need them.

## Getting Started

1. Connect your controller with a USB cable (recommended for 1000 Hz) or over Bluetooth.
2. Open AxisNex. The first time, a short tutorial explains the screen (you can replay it with the **Tutorial** button).
3. On **Home**, pick a profile (step 2). **Pro** is selected by default.
4. Press **START**. AxisNex hides the physical controller and starts the virtual controller; all three status dots turn green.
5. Press **Calibrate** and follow the three short steps. Do this after START, each time you open AxisNex, and again after switching profiles.
6. Launch the game **after** pressing START. If the game was already open, restart it.
7. Optional: open **Game settings** to see which in-game settings to use so deadzones don't stack. If the game runs through Steam, keep Steam Input on.

Press START again to stop; the physical controller becomes visible to games again. Closing the window with ✕ keeps AxisNex running next to the clock — right-click its icon → **Exit** to close it completely.

## Calibration and profiles

Calibration has three steps — **Rest** (don't touch anything), **Range** (roll both sticks around the edge, press both triggers fully once) and **Return** (let go) — followed by a result screen. Nothing is saved until you press **Apply & save**. The result is stored in the active profile, and every profile has its own deadzones, so calibrate again after switching.

| Profile | Meant for |
|---|---|
| **Pro** (default) | Linear response, zero smoothing, full diagonals. A neutral starting point. |
| **Freestyle** | Same base, slightly finer control around the center. |
| **Aerial** | Gentler curve near the center for small corrections, full diagonals for fast rotations. |
| **Worn Controller** | Larger deadzones and an earlier outer edge for older sticks with drift. |

Step-by-step guide, what each result means and which profile to pick: **[docs/calibration.md](docs/calibration.md)**.

## Controller Detection

- AxisNex looks for the **DualSense Wireless Controller** by its USB vendor and product ID (`054C:0CE6`), over USB and Bluetooth. The status bar shows the device name and connection type that Windows reports.
- Virtual or software-created devices are ignored, so AxisNex never picks up its own virtual controller.
- AxisNex checks for the controller about every 1.5 seconds, so plugging it in or reconnecting it is detected automatically.
- While AxisNex is running, the physical controller is hidden from other programs with HidHide; only AxisNex can read it. If AxisNex closes unexpectedly, the controller is made visible again the next time AxisNex starts.
- 1000 Hz polling applies to USB only. Over Bluetooth the controller uses its own report rate.

## Troubleshooting

### Controller is not detected

1. Restart Windows (required after the first installation).
2. Reconnect the controller: unplug and plug the USB cable back in, or reconnect it over Bluetooth.
3. Prefer a wired USB connection, with a cable that carries data (not a charge-only cable).
4. Launch AxisNex again.

### "Found the controller but can't open it"

Another controller tool is using the controller. Close it and press START again.

### The game sees two controllers

- Make sure **Hide the physical controller (HidHide)** is on in Settings.
- Start the game **after** pressing START, or restart it.
- If AxisNex says HidHide is missing, reinstall AxisNex (the installer includes HidHide), then restart Windows.

### 1000 Hz doesn't turn on

It only works with a USB cable. If Windows doesn't accept the driver, AxisNex puts the controller back to 250 Hz by itself and shows a message. Reinstalling AxisNex adds the driver again.

### "Anti-cheat violation detected" or a kick from a match

Press STOP in AxisNex and play without it for a while. See the **Game rules** page and the [Disclaimer](#disclaimer).

### Calibration keeps stopping ("Calibration stopped")

A stick moved during the Rest or Return step, or never came back to center. Put the controller down on a table, wait a second and press **Redo**. If a stick never settles, try the **Worn Controller** profile.

### Windows menus scroll on their own while the controller is plugged in

Fixed in V1.3: AxisNex corrects the controller layout Windows uses for its own menus, at startup and after START. Update to the latest version and open AxisNex once.

### Something else

Open a [bug report](https://github.com/wlt1920/AxisNex/issues/new/choose). The status bar text at the bottom of AxisNex and a screenshot help a lot.

## Known limitations

- Only the **DualSense Wireless Controller** is supported. DualSense Edge, DualShock 4, Xbox and other controllers are not detected.
- One controller at a time.
- **Advanced tuning** is not fully tested yet.
- Calibration is per profile and should be repeated each session (see [Getting Started](#getting-started)).
- The installer and app are not code-signed, so SmartScreen and some antivirus tools may warn.
- Windows only (10/11, 64-bit).

## FAQ

**Does AxisNex work with games other than Rocket League?**
The deadzone, response and calibration apply to any game that reads the virtual controller. The built-in profiles and the Game settings page are written for Rocket League, so other games may need different values.

**Is it safe with anti-cheat?**
AxisNex does not inject into games, read game memory or change game files; it only processes controller input. Still, nobody can guarantee how an anti-cheat system treats third-party controller software. Read the [Disclaimer](#disclaimer).

**Do I need Steam Input on or off?**
If the game runs through Steam, keep Steam Input on; some games only see the controller through it.

**Can AxisNex fix stick drift permanently?**
No. It can't repair hardware. It measures the drift and sets a deadzone and center correction so the drift doesn't reach the game.

**Why does it need administrator rights?**
Hiding the physical controller, creating the virtual controller and changing the USB polling rate are administrator-only operations in Windows. See [Security](#security).

**Does closing the window stop AxisNex?**
No. ✕ hides it next to the clock and your controller stays tuned. Right-click the icon → **Exit** to close it. You can change this in Settings.

**Can I share my profile?**
Yes. On the **Profiles** page, use the export button on a profile card and send the `.axisnex` file; your friend imports it there. Your calibration is not included.

**Is AxisNex open source?**
No. It's free to use, but the source code is not public. See [License](#license).

## Privacy

This is based on the source code of AxisNex:

- AxisNex has **no telemetry, analytics, ads or accounts**. It does not send information about you, your PC or your controller anywhere.
- Settings, profiles and calibration are stored locally on your PC (your user AppData folder and the Windows registry).
- AxisNex connects to the internet only for:
  - **Update check** (on by default, can be turned off in Settings): downloads `version.json` from this repository's latest GitHub release; when you choose to update, it downloads the installer from GitHub.
  - **Game rules page** (on by default, can be turned off on that page): at startup and every 6 hours while AxisNex is open, it reads public pages: the Epic Games terms of service, the game's news feed on Steam and a search on the game's Steam community forum.
  - **Links you click**, which open in your web browser.
- Like any website visit, those servers (GitHub, Epic Games, Valve/Steam) see your IP address and a User-Agent with the AxisNex version. wLt receives none of this.

## Security

- **Administrator rights.** The installer needs them to install into Program Files and to set up three drivers: HidHide (hides the physical controller), the HIDMaestro virtual-controller driver, and hidusbf (1000 Hz USB). AxisNex itself also runs as administrator, because hiding the controller, creating the virtual controller and changing the USB polling rate are administrator-only operations in Windows.
- **Driver certificate.** HIDMaestro installs its own self-signed driver certificate (`HIDMaestroTestCert`) into the computer's trusted certificate stores so its user-mode driver can load. It stays installed after uninstalling AxisNex and can be removed with `certlm.msc`.
- **Updates** are only accepted from this repository's GitHub releases over HTTPS. The installer is downloaded into the AxisNex program folder (writable only by administrators), checked against the SHA-256 in the release manifest, and only then started.
- **Bundled components** (HidHide installer, hidusbf driver, HIDMaestro library) are official releases whose SHA-256 hashes are checked when AxisNex is built.
- AxisNex is **not code-signed**. Verify downloads with the SHA-256 in the release notes.
- AxisNex never asks you to disable Windows Defender, your antivirus, Secure Boot, driver signature enforcement or any other Windows security feature.
- AxisNex does not inject into games, read game memory or change game files.

Scans of the bundled third-party files:

| File | SHA-256 | Scan |
|---|---|---|
| `hidusbf.sys` (1000 Hz USB driver by SweetLow, Microsoft-signed) | `2f82cdeb36bdaa42ea1933a9b11f3b8e1bdb28e6d3e3da7e65b4631b3375412d` | [VirusTotal](https://www.virustotal.com/gui/file/2f82cdeb36bdaa42ea1933a9b11f3b8e1bdb28e6d3e3da7e65b4631b3375412d) |
| `HidHide_x64.exe` (official Nefarius installer v1.5.230) | `f4bbbcb82e6258641b887c74bc81c4c5f66e4aa811808dfc304347687b7605f6` | [VirusTotal](https://www.virustotal.com/gui/file/f4bbbcb82e6258641b887c74bc81c4c5f66e4aa811808dfc304347687b7605f6) |

Not sure? You don't have to trust us: scan the installer yourself with any antivirus or online scanner, compare the SHA-256, or don't install it.

**Beware of scams:** AxisNex is free. wLt never asks for money, a login, your passwords or your game account. Copies from other websites, videos or Discord files are not from wLt.

Found a security problem? See [SECURITY.md](SECURITY.md).

## Feedback and contributing

Bug reports, feature ideas and feedback on Advanced tuning are welcome — see [CONTRIBUTING.md](CONTRIBUTING.md). Use the [issue templates](https://github.com/wlt1920/AxisNex/issues/new/choose) so the details needed to reproduce a problem are included.

## Disclaimer

**AxisNex is an independent project and is not affiliated with, endorsed by, or sponsored by Sony Interactive Entertainment, Epic Games, Psyonix, or any controller or game manufacturer. All trademarks belong to their respective owners.**

Product and game names are used only to describe compatible hardware and the sources AxisNex refers to. You install and use AxisNex at your own risk and are responsible for following the rules of every game and platform you use it with. Nobody can guarantee how an anti-cheat system treats third-party controller software. See the [license](legal/EULA-en.txt).

## License

AxisNex is **free proprietary software**, not open source. © 2026 wLt. All rights reserved. You may download and use it free of charge under the [license agreement](legal/EULA-en.txt) shown during installation ([Română](legal/EULA-ro.txt), [Deutsch](legal/EULA-de.txt)). The original, unmodified installer may be shared free of charge; selling it or publishing modified versions is not allowed.

The third-party components keep their own licenses: [`THIRD-PARTY-NOTICES.txt`](THIRD-PARTY-NOTICES.txt).

## Credits

Created by **wLt** ([wltziff.nl](https://wltziff.nl)), with my basic knowledge of C#, together with the AI tools Claude and Codex.

AxisNex builds on these open-source projects — thank you:

| Component | What for | GitHub | License |
|---|---|---|---|
| HIDMaestro | virtual controller driver (UMDF2) | [hifihedgehog/HIDMaestro](https://github.com/hifihedgehog/HIDMaestro) | MIT |
| HidHide by Nefarius | hides the physical controller from games | [nefarius/HidHide](https://github.com/nefarius/HidHide) | MIT |
| HidSharp | reading the controller over HID | [IntergatedCircuits/HidSharp](https://github.com/IntergatedCircuits/HidSharp) | Apache 2.0 |
| hidusbf by SweetLow | 1000 Hz USB polling (NoPatch driver, Microsoft-signed) | [LordOfMice/hidusbf](https://github.com/LordOfMice/hidusbf) | Public Domain |
| usbip-win2 (inside HIDMaestro) | USB transport for composite devices | [vadimgrn/usbip-win2](https://github.com/vadimgrn/usbip-win2) | BSD 2-Clause |
| DsHidMini by Nefarius (approach & parts used by HIDMaestro) | user-mode controller driver foundation | [nefarius/DsHidMini](https://github.com/nefarius/DsHidMini) | BSD 3-Clause |
| .NET Runtime | runtime | [dotnet/runtime](https://github.com/dotnet/runtime) | MIT |
| WPF | user interface | [dotnet/wpf](https://github.com/dotnet/wpf) | MIT |
| Inno Setup | installer | [jrsoftware/issrc](https://github.com/jrsoftware/issrc) | Inno Setup License |
