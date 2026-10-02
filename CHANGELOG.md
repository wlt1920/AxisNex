# Changelog

Everything that changed in each version of Input Zero. Newest first.
Download the latest version from [Releases](https://github.com/wlt1920/InputZero/releases/latest).

## V1.2.2 — 2026-10-03

- **1000 Hz over USB:** the wired DualSense is now read 4× more often (stock 250 Hz → 1000 Hz, up to 3 ms less delay). It uses the Microsoft-signed hidusbf driver by SweetLow, installed together with Input Zero. On by default — switch **1000 Hz on USB** on the Home page. If your PC doesn't accept it, Input Zero puts the controller back to 250 Hz by itself, and uninstalling removes it.
- **Bluetooth works** (tested by WLT). 1000 Hz is USB-only; over Bluetooth the controller keeps its own rate.
- **Input thread priority:** the controller reader now uses Windows' multimedia scheduling (MMCSS), so a busy CPU in game can't hold back a controller report.
- **11 languages:** English, Română, Deutsch, Español, Français, Italiano, Português, Nederlands, Polski, Türkçe, Русский — in the app and in the installer.
- **Steam Input tip removed:** Rocket League on Steam needs Steam Input to see the controller, so keep it on.
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