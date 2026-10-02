<p align="center">
  <img src="docs/logo.png" width="120" alt="Input Zero logo">
</p>

<h1 align="center">Input Zero</h1>

<p align="center">
  <b>Minimum-latency DualSense tuning for PC, built for Rocket League.</b><br>
  Made by <b>WLT</b> · <a href="https://wltziff.nl">wltziff.nl</a>
</p>

<p align="center">
  <a href="https://github.com/wlt1920/InputZero/releases/latest"><b>⬇ Download the latest version</b></a> · <a href="CHANGELOG.md"><b>What's new in each update</b></a>
</p>

<p align="center">
  <img src="docs/screenshot.png" width="860" alt="Input Zero screenshot">
</p>

---

## ⚠ Official downloads only

Input Zero is distributed **only** from these two places:

- **https://github.com/wlt1920/InputZero/releases** (this repository)
- **https://wltziff.nl**

Anything else — other websites, YouTube links, Discord files, "cracked" or "premium" versions — is **not from WLT** and may contain malware. Beware of scams:

- Input Zero is **free**. WLT never asks for money, a login, your passwords or your game account.
- Check the installer's **SHA-256** against the value in the release notes, and the **VirusTotal** scan links below.

## VirusTotal scans

| File | SHA-256 | Result | Scan |
|---|---|---|---|
| `InputZero-V1-Setup.exe` (installer) | `c50bc59a5c6e1dc6cb7d188feec70fe1f933b5f1d5f13fd71ec350804bf9213f` | ✅ clean — 1 low-confidence ML guess (Trapmine) | [VirusTotal](https://www.virustotal.com/gui/file/c50bc59a5c6e1dc6cb7d188feec70fe1f933b5f1d5f13fd71ec350804bf9213f) |
| `InputZero.exe` (the app, inside the installer) | `d798e93e03c1d80c9ad69532882e84b4ef10a2bb9479fd3ba13ca10ff1ae858e` | ✅ **0 / 65** — no detections | [VirusTotal](https://www.virustotal.com/gui/file/d798e93e03c1d80c9ad69532882e84b4ef10a2bb9479fd3ba13ca10ff1ae858e) |
| `HidHide_x64.exe` (official Nefarius installer, bundled) | `f4bbbcb82e6258641b887c74bc81c4c5f66e4aa811808dfc304347687b7605f6` | official signed release | [VirusTotal](https://www.virustotal.com/gui/file/f4bbbcb82e6258641b887c74bc81c4c5f66e4aa811808dfc304347687b7605f6) |

The app itself (`InputZero.exe`) scores **0 / 65** on VirusTotal. All major antivirus engines (Microsoft Defender, Kaspersky, BitDefender, ESET, CrowdStrike, Avast, AVG, Google and others) report the files as clean. One engine (Trapmine) shows a low-confidence machine-learning guess (`Suspicious.low.ml.score`) on the installer `InputZero-V1-Setup.exe`: that is a known false positive for new, unsigned apps that install drivers, not a detected threat.

The installer is not code-signed yet, so Windows SmartScreen may show "Unknown publisher". That is normal for free indie software; the hashes and scans above let you verify the file.

**Not sure? That's completely fine.** You don't have to trust us: scan the files yourself with any antivirus or online scanner you like (VirusTotal, your own antivirus, Jotti, MetaDefender…), compare the SHA-256 above, or simply skip Input Zero. Nobody is forced to install it.
## What it does

> **Currently tested only with the PS5 DualSense, connected by USB cable (wired).** Bluetooth is **not tested yet**, so it is not guaranteed to work. Support for Bluetooth and more controllers is planned in future updates.

Input Zero sits between your **PS5 DualSense** and your games:

- **Only one controller in game.** Your physical DualSense is hidden from games (via HidHide), and the game sees a single virtual DualSense with your tuning applied. No more double input or "a second player joined".
- **As little delay as possible.** Zero smoothing, an event-driven input thread (no polling loop), allocation-free processing measured in microseconds, and nothing running in the background while you play.
- **Rocket League presets.** `Rocket League - Pro` (zero smoothing, linear response, 100% diagonals for faster aerial rotation) and `Rocket League - Freestyle` (a touch finer around center for air roll and flicks).
- **3-second deadzone calibration.** Put the controller down, press *Calibrate*, and Input Zero measures your stick drift and sets the smallest safe deadzone.
- **Full manual tuning.** Deadzone shape, inner/outer deadzone, anti-deadzone, response curve, square output, sensitivity, triggers.
- **English, Română, Deutsch.** Switch live, no restart.
- **6 color themes** (Zero, Ice, Inferno, Violet, Toxic, Mono).
- **Advanced tuning is not fully tested yet** — if you try it, [feedback](https://github.com/wlt1920/InputZero/issues/new) is very welcome!
- **Updates built in.** When a new version is released here, the app shows *"Vx available – Update"*, downloads the installer, verifies its SHA-256 and installs it. Your profiles stay.

## Install

1. Download the latest **`InputZero-…-Setup.exe`** from [Releases](https://github.com/wlt1920/InputZero/releases/latest).
2. Run it, pick your language, accept the license.
   The installer also sets up [HidHide](https://github.com/nefarius/HidHide) (if missing) and the virtual-controller driver.
3. Restart your PC once if HidHide was installed.
4. Open Input Zero → plug in the DualSense **with a USB cable** (Bluetooth is not tested yet) → press **START** → then launch your game.

A short animated tutorial runs the first time you open the app (and any time via the **?** button).

## Is it safe? Can I get banned?

- Input Zero **never touches the game**: no injection, no memory reading, no file changes. It only works at the controller level, the same way DS4Windows and Steam Input do.
- It does **not collect anything** from your PC. No telemetry, no accounts, no ads. The only internet access is the optional update check (it reads `version.json` from this GitHub page) and downloads you choose to start.
- Nobody can promise what every anti-cheat will do, so **you install and use it at your own risk** — see the license shown during setup.

## How it works

```text
Physical DualSense (USB cable — Bluetooth not tested yet)
      │  raw HID reports (250 Hz USB, full 0x31 reports on Bluetooth)
      ▼
DualSenseReader      dedicated high-priority thread, blocks on the HID read
      ▼
TuningEngine         deadzones, curve, square output, triggers  (~µs, no allocations)
      ▼
HIDMaestro           user-mode (UMDF2) driver → virtual DualSense
      ▼
Game                 sees only the virtual pad (physical one hidden by HidHide)
```

Built by WLT with C# / .NET 10 and WPF. The UI only draws while the window is in front; when you are in game it pauses all animations and previews, so the app costs almost nothing while you play.

## How it started — and where it is now

Input Zero started as a small personal experiment called **WLT Controller Tuner v0.1 — "DualSense Lab"**: a window full of sliders that read a DualSense, ran it through some deadzone math and pushed it out as a virtual controller. It worked, but it was a lab tool. You had to build it yourself, connect things in the right order, set up HidHide by hand, and games often saw two controllers at once.

The goal was simple: **the best possible Rocket League feel on a DualSense, with the lowest delay a PC can give, and only one controller in the game.** Getting there meant rebuilding almost everything:

- fixing how the app tells your real controller apart from the virtual one;
- automating HidHide so the physical pad is hidden and restored on its own;
- cutting latency out of every step between the controller and the game;
- writing proper Rocket League presets and a one-click drift calibration;
- a completely new interface, a guided tutorial, three languages, a real installer, a license, and built-in updates.

That became **Input Zero V1**. Since then it keeps getting updates — always download the latest release.

## What's next

Ideas on the list (no promises on dates):

- more presets and per-game profiles;
- optional 1000 Hz USB polling guidance;
- **tested Bluetooth support** — today only the wired (USB) DualSense is tested;
- **support for more controllers** (DualShock 4, DualSense Edge, Xbox and others) — today only the PS5 DualSense is tested;
- whatever the community asks for.

**I'll keep Input Zero alive for as long as I can and as much as my time allows.** If it helps you, a follow on [wltziff.nl](https://wltziff.nl) is always appreciated.

## Credits & licenses

Input Zero is made by **WLT** and builds on great open-source work. Thank you to all of these projects:

| Component | What for | GitHub | License |
|---|---|---|---|
| HIDMaestro | virtual DualSense driver (UMDF2) | [hifihedgehog/HIDMaestro](https://github.com/hifihedgehog/HIDMaestro) | MIT |
| HidHide by Nefarius | hides the physical controller from games | [nefarius/HidHide](https://github.com/nefarius/HidHide) | MIT |
| HidSharp | reading the DualSense over HID | [IntergatedCircuits/HidSharp](https://github.com/IntergatedCircuits/HidSharp) | Apache 2.0 |
| usbip-win2 (inside HIDMaestro) | USB transport for composite devices | [vadimgrn/usbip-win2](https://github.com/vadimgrn/usbip-win2) | BSD 2-Clause |
| DsHidMini by Nefarius (approach & parts used by HIDMaestro) | user-mode controller driver foundation | [nefarius/DsHidMini](https://github.com/nefarius/DsHidMini) | BSD 3-Clause |
| .NET Runtime | runtime | [dotnet/runtime](https://github.com/dotnet/runtime) | MIT |
| WPF | user interface | [dotnet/wpf](https://github.com/dotnet/wpf) | MIT |
| Inno Setup | installer | [jrsoftware/issrc](https://github.com/jrsoftware/issrc) | Inno Setup License |

Full license texts: [`THIRD-PARTY-NOTICES.txt`](THIRD-PARTY-NOTICES.txt). Input Zero's own license (EN / RO / DE): [`legal/`](legal/).

Input Zero is an independent project, not affiliated with Sony Interactive Entertainment, Psyonix, Epic Games or Nefarius Software Solutions. "PlayStation" and "DualSense" are trademarks of Sony Interactive Entertainment Inc.; "Rocket League" is a trademark of Psyonix LLC.

---

**Input Zero** © 2026 **WLT** ([wltziff.nl](https://wltziff.nl)). All rights reserved. Free to download and use under the [license](legal/EULA-en.txt) shown during installation. The installer may be shared unmodified and free of charge; selling it or re-publishing modified versions is not allowed.
