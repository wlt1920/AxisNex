# Changelog

Everything that changed in each version of wLt AxisNex (called Input Zero before V1.2.4). Newest first.
Download the latest version from [Releases](https://github.com/wlt1920/AxisNex/releases/latest).

## V1.2.4 — 2026-10-03

- **New name: wLt AxisNex.** Input Zero is now **wLt AxisNex** by wLt, with a new logo, app icon and installer. Updating from Input Zero keeps your profiles, calibration and settings, and replaces the old shortcuts.
- **Completely new layout:** a side menu (Home, Advanced tuning, Rocket League settings, RL rules, Settings) and a Home page that guides you step by step — **1 Connect → 2 Pick a profile → 3 START → 4 Calibrate** — with the next step highlighted. Toggles, theme, language and updates moved to the new **Settings** page.
- **Pro calibration:** a 15-second guided check — rest, roll both sticks around the edge, let go. It measures drift, the resting center of each stick, how far each stick reaches in every direction and both triggers. The center is now corrected, so the deadzone can be smaller and still safe; worn sticks and triggers reach 100% again. You see the result (drift, center, deadzone, range, roundness, condition) before anything is saved.
- **Switching profiles** now shows a notification and an animation telling you to calibrate again (every profile has its own deadzones).
- **9 clearly different themes** — each with its own background and surfaces: AxisNex (new, default), Midnight Ocean, Synthwave, Inferno, Sakura (new), Royal Gold (new), Matrix, Zero, Graphite.
- **Lots of animation:** a START burst (shockwaves, particles, flash), animated switches with an ON/OFF chip, a sliding menu highlight, moving background lights, staggered pages. All of it pauses while the window is in the background, so nothing runs while you play.
- **Controller rumble:** the DualSense gives a short rumble when START kicks in and a tick on the calibration steps (never while the sticks are being measured at rest). Can be turned off in Settings.
- **Big notifications** for update checks, rules checks, calibration and saves; they appear instantly ("Checking…") and turn into the result.
- **Release notes:** when an update is available you see what it brings before installing it, and after updating AxisNex shows what's new once.
- **Tutorial** button instead of "?", profile step before START, and a new USB-C animation.

## V1.2.3 — 2026-10-03

- **New RL rules page:** watches Epic's fair-play rules and shows exactly what changed, highlights official Rocket League news about the anti-cheat, and lists what players report on the Steam forum. Checks at startup and every 6 hours (can be turned off) and shows where Input Zero stands against the rules. In all 11 languages.

## V1.2.2 — 2026-10-03

- **1000 Hz over USB:** the wired DualSense is now read 4× more often (stock 250 Hz → 1000 Hz, up to 3 ms less delay). It uses the Microsoft-signed hidusbf driver by SweetLow, installed together with Input Zero. On by default — switch **1000 Hz on USB** on the Home page. If your PC doesn't accept it, Input Zero puts the controller back to 250 Hz by itself, and uninstalling removes it.
- **Bluetooth works** (tested by WLT). 1000 Hz is USB-only; over Bluetooth the controller keeps its own rate.
- **Input thread priority:** the controller reader now uses Windows' multimedia scheduling (MMCSS), so a busy CPU in game can't hold back a controller report.
- **11 languages:** English, Română, Deutsch, Español, Français, Italiano, Português, Nederlands, Polski, Türkçe, Русский — in the app and in the installer.
- **Steam Input tip removed:** Rocket League on Steam needs Steam Input to see the controller, so keep it on.
- **2 new Rocket League profiles:** `Rocket League - Aerial` (gentler curve near center for air dribbles, ceiling shots and recoveries, full diagonals for fast rotations) and `Rocket League - Worn Controller` (bigger deadzones and an earlier outer edge for older sticks with drift).
- **Check for updates button:** when automatic update checks are off, a **Check now** button appears next to the switch.
- New description: Input Zero is about low latency **and** an automatically calibrated deadzone (you can still set it by hand).

## V1.2.1 — 2026-10-03

- **Themes:** 6 color themes — Zero, Ice, Inferno, Violet, Toxic, Mono. Pick one at the top of the window; Input Zero restarts in a second to apply it.
- **Advanced tuning is not fully tested yet:** a notice on that page says so, with a **Send feedback** button. If you try it, your feedback is really appreciated!

## V1.2 — 2026-10-03

- **Calibration:** do it **after pressing START, every time you open Input Zero** — hold the controller gently in your hands without touching the sticks or triggers. After START the app now reminds you and the Calibrate button pulses.
- **Profiles:** only Rocket League profiles are left (`Rocket League - Pro`, `Rocket League - Freestyle`). The old `FPS - Precision` and `Raw - Linear` profiles are removed.
- Tutorial step 4 updated to match.

## V1.1 — 2026-10-03

- **Rocket League settings tab:** Dodge Deadzone, Steering Sensitivity and Aerial Sensitivity are now clearly marked as **WLT's personal settings** — set them to whatever feels right for you.
- **Latency tips:** "Disable Steam Input for Rocket League" is now marked as **optional** — your choice.
- Updating from V1: open Input Zero and click **Update** at the top. Your profiles, calibration and settings are kept.

## V1 — 2026-10-02

First public release.

- Only one controller in game: the physical DualSense is hidden (HidHide) and games see a single virtual DualSense with your tuning.
- Minimum-latency processing: zero smoothing, event-driven input thread, processing measured in microseconds; nothing animates while you play.
- Rocket League presets (`Rocket League - Pro`, `Rocket League - Freestyle`) and 3-second deadzone calibration.
- Automatic controller detection (plug in / unplug).
- Guided animated tutorial, English / Romanian / German.
- Installer with license, HidHide included, built-in updates from GitHub.
- Tested only with the PS5 DualSense over USB cable. Bluetooth is not tested yet.
