<p align="center">
  <img src="docs/logo.png" width="120" alt="wLt AxisNex logo">
</p>

<h1 align="center">wLt AxisNex</h1>

<p align="center">
  <b>Low-latency DualSense tuning for PC with an auto-calibrated deadzone (or set it by hand), built for Rocket League.</b><br>
  Made by <b>wLt</b> · <a href="https://wltziff.nl">wltziff.nl</a>
  <br><sub>Built with my basic knowledge of C#, together with Claude and Codex.</sub>
</p>

<p align="center">
  <a href="https://github.com/wlt1920/AxisNex/releases/latest"><b>⬇ Download the latest version</b></a> · <a href="CHANGELOG.md"><b>What's new in each update</b></a>
</p>

<p align="center">
  <img src="docs/screenshot.png" width="860" alt="wLt AxisNex screenshot">
</p>

---

## ⚠ Official downloads only

AxisNex is distributed **only** from these two places:

- **https://github.com/wlt1920/AxisNex/releases** (this repository)
- **https://wltziff.nl**

Anything else — other websites, YouTube links, Discord files, "cracked" or "premium" versions — is **not from wLt** and may contain malware. Beware of scams:

- AxisNex is **free**. wLt never asks for money, a login, your passwords or your game account.
- Check the installer's **SHA-256** against the value in the release notes, and the **VirusTotal** scan links below.

## VirusTotal scans

Scans of **V1.2.2** (still named Input Zero then), done by wLt:

| File | SHA-256 | Result | Scan |
|---|---|---|---|
| `Input Zero.rar` (the V1.2.2 setup, packed for scanning) | `7a7e03cd926d615fd3d06743a286e3599e8ca32b337935bff1a6b8f7023ab8ce` | ✅ **0 / 57** — no detections | [VirusTotal](https://www.virustotal.com/gui/file/7a7e03cd926d615fd3d06743a286e3599e8ca32b337935bff1a6b8f7023ab8ce) |
| `InputZero.dll` (the app's code) | `6fecffa9f7d7d7488182dfcd49670d85f0f65fd26383e83e36d80ae40ae384bc` | ✅ **0 / 66** — no detections | [VirusTotal](https://www.virustotal.com/gui/file/6fecffa9f7d7d7488182dfcd49670d85f0f65fd26383e83e36d80ae40ae384bc) |
| `hidusbf.sys` (1000 Hz USB driver by SweetLow, bundled) | `2f82cdeb36bdaa42ea1933a9b11f3b8e1bdb28e6d3e3da7e65b4631b3375412d` | ✅ **0 / 72** — no detections, Microsoft-signed | [VirusTotal](https://www.virustotal.com/gui/file/2f82cdeb36bdaa42ea1933a9b11f3b8e1bdb28e6d3e3da7e65b4631b3375412d) |
| `HidHide_x64.exe` (official Nefarius installer, bundled) | `f4bbbcb82e6258641b887c74bc81c4c5f66e4aa811808dfc304347687b7605f6` | official signed release | [VirusTotal](https://www.virustotal.com/gui/file/f4bbbcb82e6258641b887c74bc81c4c5f66e4aa811808dfc304347687b7605f6) |

No antivirus engine flags any of these files — Microsoft Defender, Kaspersky, BitDefender, ESET, CrowdStrike, Avast, AVG, Google and the rest all report them as clean. A few engines show "unable to process file type" or "timeout" for the `.rar` archive: that means they didn't scan it, not that they found something.

The official installer on the [Releases](https://github.com/wlt1920/AxisNex/releases/latest) page is `InputZero-V1.2.2-Setup.exe`, SHA-256 `dcd85db8deb04a5e51b0da055e46c40430118ce156d4f6e85494379368f51abb` (also in the release notes). Input Zero checks this hash itself before installing an update.

The installer is not code-signed yet, so Windows SmartScreen may show "Unknown publisher". That is normal for free indie software; the hashes and scans above let you verify the file.

**Not sure? That's completely fine.** You don't have to trust us: scan the files yourself with any antivirus or online scanner you like (VirusTotal, your own antivirus, Jotti, MetaDefender…), compare the SHA-256 above, or simply skip AxisNex. Nobody is forced to install it.
## What it does

> **Tested with the PS5 DualSense over USB cable and Bluetooth.** USB is recommended: only USB can run at **1000 Hz**. Support for more controllers is planned in future updates.

AxisNex sits between your **PS5 DualSense** and your games:

- **Only one controller in game.** Your physical DualSense is hidden from games (via HidHide), and the game sees a single virtual DualSense with your tuning applied. No more double input or "a second player joined".
- **As little delay as possible.** Zero smoothing, an event-driven input thread with Windows multimedia priority (MMCSS), allocation-free processing measured in microseconds, and nothing running in the background while you play.
- **1000 Hz over USB.** The DualSense reports 250 times per second from the factory; AxisNex raises that to 1000 on USB (up to 3 ms less delay) with the Microsoft-signed [hidusbf](https://github.com/LordOfMice/hidusbf) driver by SweetLow. On by default, one switch to turn it off, removed on uninstall. Not possible over Bluetooth.
- **4 Rocket League profiles.** `Rocket League - Pro` (zero smoothing, linear response, 100% diagonals for faster aerial rotation), `Rocket League - Freestyle` (a touch finer around center for air roll and flicks), `Rocket League - Aerial` (gentler curve near center for air dribbles and recoveries) and `Rocket League - Worn Controller` (bigger deadzones for older sticks with drift).
- **Pro calibration (15 seconds, guided).** After START, press *Calibrate* and follow 3 short steps: rest, roll both sticks around the edge, let go. AxisNex measures drift, the resting center of each stick, how far each stick reaches and your triggers, corrects the center and sets the smallest safe deadzone â worn sticks and triggers reach 100% again. You see the result before it is saved. Prefer your own values? Set them by hand in *Advanced tuning*.
- **Full manual tuning.** Deadzone shape, inner/outer deadzone, anti-deadzone, response curve, square output, sensitivity, triggers.
- **11 languages:** English, Română, Deutsch, Español, Français, Italiano, Português, Nederlands, Polski, Türkçe, Русский. Switch live, no restart.
- **6 color themes** (Zero, Ice, Inferno, Violet, Toxic, Mono).
- **Advanced tuning is not fully tested yet** — if you try it, [feedback](https://github.com/wlt1920/AxisNex/issues/new) is very welcome!
- **Updates built in.** When a new version is released here, the app shows *"Vx available – Update"*, downloads the installer, verifies its SHA-256 and installs it. Your profiles stay. Automatic checks can be turned off; then a **Check now** button checks on demand.

## Rocket League profiles

Pick one in step 2 on Home (before START). All of them have **zero smoothing**, and your calibration is saved into whichever profile is active â switch profiles and AxisNex asks you to calibrate again. Everything can be fine-tuned in *Advanced tuning*.

| Profile | Best for | What it does |
|---|---|---|
| `Rocket League - Pro` (default) | Ranked, general play, fast reactions | Linear response (what RL muscle memory is built on), small deadzone, **100% diagonals** so diagonal aerials reach full pitch + yaw, full throttle/boost before the trigger bottoms out. |
| `Rocket League - Freestyle` | Air roll, flicks, freestyle clips | Same base with a touch more precision around center for small air-roll and flick inputs. |
| `Rocket League - Aerial` | Air dribbles, ceiling shots, recoveries | Gentler curve near center for tiny pitch/yaw corrections in the air, still full speed at the edge and 100% diagonals for fast rotations. |
| `Rocket League - Worn Controller` | Older DualSense with drift or loose sticks | Bigger deadzones so the car doesn't steer on its own, and an earlier outer edge because worn sticks often stop short of the rim. |

Not sure? Start with **Pro**, press *Calibrate* after START, and only switch if you want something specific.


## Install

1. Download the latest **`InputZero-…-Setup.exe`** from [Releases](https://github.com/wlt1920/AxisNex/releases/latest).
2. Run it, pick your language, accept the license.
   The installer also sets up [HidHide](https://github.com/nefarius/HidHide) (if missing) and the virtual-controller driver.
3. Restart your PC once if HidHide was installed.
4. Open AxisNex → connect the DualSense **with a USB cable** (recommended, 1000 Hz) or over Bluetooth → press **START** → calibrate → then launch your game. Keep Steam Input **on** for Rocket League on Steam.

A short animated tutorial runs the first time you open the app (and any time via the **?** button).

## Is it safe? Can I get banned?

- AxisNex **never touches the game**: no injection, no memory reading, no file changes. It only works at the controller level, the same way DS4Windows and Steam Input do.
- It does **not collect anything** from your PC. No telemetry, no accounts, no ads. The only internet access is the optional update check (it reads `version.json` from this GitHub page) and downloads you choose to start.
- Nobody can promise what every anti-cheat will do, so **you install and use it at your own risk** — see the license shown during setup.

## How it works

```text
Physical DualSense (USB cable or Bluetooth)
      │  raw HID reports (1000 Hz USB via hidusbf, full 0x31 reports on Bluetooth)
      ▼
DualSenseReader      dedicated MMCSS "Games" thread, blocks on the HID read
      ▼
TuningEngine         deadzones, curve, square output, triggers  (~µs, no allocations)
      ▼
HIDMaestro           user-mode (UMDF2) driver → virtual DualSense
      ▼
Game                 sees only the virtual pad (physical one hidden by HidHide)
```

Built by wLt with C# / .NET 10 and WPF. The UI only draws while the window is in front; when you are in game it pauses all animations and previews, so the app costs almost nothing while you play.

## How it started — and where it is now

AxisNex started as a small personal experiment called **wLt Controller Tuner v0.1 — "DualSense Lab"**: a window full of sliders that read a DualSense, ran it through some deadzone math and pushed it out as a virtual controller. It worked, but it was a lab tool. You had to build it yourself, connect things in the right order, set up HidHide by hand, and games often saw two controllers at once.

The goal was simple: **the best possible Rocket League feel on a DualSense, with the lowest delay a PC can give, and only one controller in the game.** Getting there meant rebuilding almost everything:

- fixing how the app tells your real controller apart from the virtual one;
- automating HidHide so the physical pad is hidden and restored on its own;
- cutting latency out of every step between the controller and the game;
- writing proper Rocket League presets and a one-click drift calibration;
- a completely new interface, a guided tutorial, 11 languages, a real installer, a license, and built-in updates.

That became **AxisNex V1**. Since then it keeps getting updates — always download the latest release.

To build AxisNex I used my basic knowledge of C#, together with the AI tools **Claude** and **Codex**.

## What's next

Ideas on the list (no promises on dates):

- more presets and per-game profiles;
- **support for more controllers** (DualShock 4, DualSense Edge, Xbox and others) — today only the PS5 DualSense is tested;
- whatever the community asks for.

**I'll keep AxisNex alive for as long as I can and as much as my time allows.** If it helps you, a follow on [wltziff.nl](https://wltziff.nl) is always appreciated.

## Credits & licenses

AxisNex is made by **wLt** and builds on great open-source work. Thank you to all of these projects:

| Component | What for | GitHub | License |
|---|---|---|---|
| HIDMaestro | virtual DualSense driver (UMDF2) | [hifihedgehog/HIDMaestro](https://github.com/hifihedgehog/HIDMaestro) | MIT |
| HidHide by Nefarius | hides the physical controller from games | [nefarius/HidHide](https://github.com/nefarius/HidHide) | MIT |
| HidSharp | reading the DualSense over HID | [IntergatedCircuits/HidSharp](https://github.com/IntergatedCircuits/HidSharp) | Apache 2.0 |
| hidusbf by SweetLow | 1000 Hz USB polling (NoPatch driver, Microsoft-signed) | [LordOfMice/hidusbf](https://github.com/LordOfMice/hidusbf) | Public Domain |
| usbip-win2 (inside HIDMaestro) | USB transport for composite devices | [vadimgrn/usbip-win2](https://github.com/vadimgrn/usbip-win2) | BSD 2-Clause |
| DsHidMini by Nefarius (approach & parts used by HIDMaestro) | user-mode controller driver foundation | [nefarius/DsHidMini](https://github.com/nefarius/DsHidMini) | BSD 3-Clause |
| .NET Runtime | runtime | [dotnet/runtime](https://github.com/dotnet/runtime) | MIT |
| WPF | user interface | [dotnet/wpf](https://github.com/dotnet/wpf) | MIT |
| Inno Setup | installer | [jrsoftware/issrc](https://github.com/jrsoftware/issrc) | Inno Setup License |

Full license texts: [`THIRD-PARTY-NOTICES.txt`](THIRD-PARTY-NOTICES.txt). AxisNex's own license (EN / RO / DE): [`legal/`](legal/).

AxisNex is an independent project, not affiliated with Sony Interactive Entertainment, Psyonix, Epic Games or Nefarius Software Solutions. "PlayStation" and "DualSense" are trademarks of Sony Interactive Entertainment Inc.; "Rocket League" is a trademark of Psyonix LLC.

---

**AxisNex** © 2026 **wLt** ([wltziff.nl](https://wltziff.nl)). All rights reserved. Free to download and use under the [license](legal/EULA-en.txt) shown during installation. The installer may be shared unmodified and free of charge; selling it or re-publishing modified versions is not allowed.
