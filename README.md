# Moon Lander DX

A retro, shareware-style lunar lander in a single HTML file: green-phosphor vector graphics, CRT glow,
generated terrain, and a fuel tank that has to last the whole run.

<h2 align="center"><a href="https://ajyounguk.github.io/lunar-lander-dx/">▶ Play it in your browser</a></h2>

No install, no build step, no dependencies. Play it online, or download `lunar-lander-dx.html`
and open it in a browser. It works on desktop and on phones/tablets (landscape).

[![Coming in to land on a x2 pad, with the camera zoomed in and the HUD showing LANDING OK](docs/screenshots/landing.png)](https://ajyounguk.github.io/lunar-lander-dx/)

| | |
|---|---|
| ![Title screen over generated terrain with x1, x2 and x5 landing pads](docs/screenshots/title.png) | ![Mid-flight on level 3 with the engine firing and the flight-data HUD](docs/screenshots/flight.png) |
| ![Crash: the lander breaks apart in a fireball and the mission failed panel shows why](docs/screenshots/crash.png) | |

## How to play

Land on a pad **slowly**, **upright** and **with both feet on the pad**.

- Every level has three pads. Wide **x1** pads are easy; narrow **x5** pads sit in valleys and are
  worth five times the points.
- Your fuel carries over from level to level. Landing refuels you, and riskier pads refuel you more.
- Crashing costs a big chunk of fuel and you retry the same level. When the tank's too low to fly,
  it's game over.
- Each level ramps up gravity and wind and shrinks the pads.

Near the ground, the camera zooms in and the HUD tells you whether you're within the landing limits:
readouts go green / amber / red, and **LANDING OK** shows when everything is safe.

### Scoring

Each landing scores `pad multiplier × (100 + soft-landing bonus + upright bonus)`, with up to 50
points for each bonus. The top five scores are saved in your browser.

## Controls

| Action | Keyboard | Touch |
|---|---|---|
| Thrust | ↑ or W | Hold **THRUST** (bottom right) |
| Rotate | ← → or A D | **◀ ▶** buttons (bottom left) |
| Start / continue | Space or Enter | Tap |
| Pause | P or Esc | **II** button |
| Quit run (when paused) | Q | **QUIT** button |
| Sound on/off | M | |
| CRT effect on/off | C | |

## Features

- Rotate-and-thrust flight with fixed-timestep physics, so it plays the same at 60Hz or 144Hz
- Generated terrain with three landing pads per level, and difficulty that ramps up
- Fuel economy across the whole run, plus scoring and a high-score table
- Arcade-style zoom camera near the ground
- Crash explosions with tumbling debris, screen shake and slow motion
- Synthesised sound (Web Audio): engine rumble, RCS hiss, low-fuel alarm, crash and landing chime
- Responsive, high-DPI canvas with touch controls
- CRT bloom and scanlines, which you can switch off for performance

## Tweaking

All gameplay numbers are in the `CONFIG` object at the top of the script: gravity and wind per
level, thrust, fuel, crash penalty, landing limits, pad sizes, camera zoom and effects. Change a
value, then reload the page.

Add `?debug` to the URL for an overlay with FPS, physics rate, position, speed and level settings.

To regenerate the README screenshots, open the game with `?shot=flight`, `?shot=landing` or
`?shot=crash`. Each one stages a fixed scene and freezes it.
