# Calibration and profiles

[← Back to README](../README.md)

AxisNex calibration measures your own controller — stick drift, where each stick rests, how far each stick and trigger reaches — and sets the deadzones from those measurements. It takes about 15 seconds.

## When to calibrate

- **After pressing START**, every time you open AxisNex.
- **After switching profiles.** Every profile keeps its own deadzones.
- When a stick starts moving on its own in game, or no longer seems to reach full lock.

Connect the controller and press **START** first; the **Calibrate** button on Home then pulses.

## The steps

| Step | What to do | What is measured |
|---|---|---|
| **1. Rest** | Hold the controller gently or put it down. Don't touch the sticks or triggers. | Drift and noise of each stick, the resting center, the resting trigger value. |
| **2. Range** | Slowly roll each stick around the edge 2–3 times, pushed all the way out. Press L2 and R2 all the way down once. | How far each stick reaches in every direction, and the full-press point of each trigger. |
| **3. Return** | Let go of both sticks and the triggers. | Where the sticks come back to after being moved (a worn spring often returns slightly off-center). |
| **4. Result** | Check the numbers, then press **Apply & save**, **Redo** or **Cancel**. | — |

If a stick moves during Rest or Return, AxisNex measures that step again by itself. If it keeps moving, you'll see **Calibration stopped**: put the controller on a table and press **Redo**.

The **Range** step can be skipped. The full-range values in the profile are then kept as they are. While rolling the sticks, the coverage counter should reach at least 75% for each stick, otherwise the range isn't used.

## Reading the result

On the result screen, the **orange ring** is the new deadzone and the **blue ring** is where full output is reached.

| Row | Meaning |
|---|---|
| **Rest drift** | How far the stick sat from the exact center while untouched. |
| **Center offset (X · Y)** | The resting position AxisNex corrects for, so the deadzone can stay small. |
| **Deadzone** | The new inner deadzone. It covers the measured resting spread around the corrected center plus a small safety margin. |
| **Full range at** | The point where the stick reaches 100% output, set just inside the stick's weakest direction so full lock is reached all the way around. |
| **Roundness** | Weakest direction compared with the strongest. 100% = perfectly round. |
| **Condition** | Based on the resting spread after center correction: **Excellent** (under 3%), **Good** (under 6%), **Fair** (under 10%), **Worn** (10% or more). |

For the triggers, the deadzone is set just above the resting value, and if the trigger was pressed far enough, full output is reached slightly before the measured full press — useful when a worn trigger no longer bottoms out at 100%.

Nothing changes until you press **Apply & save**. The result is saved into the active profile.

## Profiles

AxisNex has four built-in profiles. You can change any value in **Advanced tuning** and save it to the active profile, or use **Reset profile** to restore the original values.

| Profile | Meant for | Main differences |
|---|---|---|
| **Pro** (default) | A neutral starting point | Linear response, zero smoothing, full diagonals on the left stick. |
| **Freestyle** | Finer control around the center | Slightly curved response and a bit less square output on the left stick. |
| **Aerial** | Small air corrections | Gentler curve near the center, full diagonals for fast rotations. |
| **Worn Controller** | Older sticks with drift | Larger inner deadzones and an earlier outer edge. |

All built-in profiles use **zero smoothing**, because smoothing adds delay.

Pick the profile **before** pressing START. If you switch later, calibrate again.

## In-game settings

AxisNex already applies a deadzone and response curve. If the game also applies its own, the two add up and the stick feels slow to respond around the center. Open the **Game settings** page in AxisNex for recommended in-game values; in short, keep the game's own deadzone at or near its minimum.

## Tips

- A wired USB connection gives the most stable readings and allows 1000 Hz polling.
- If the Condition shows **Worn** on every run, try the **Worn Controller** profile as the base.
- AxisNex can't repair hardware drift. It keeps the drift from reaching the game.
