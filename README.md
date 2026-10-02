# Moon Lander DX

A retro, shareware-style lunar lander in a single HTML file: green-phosphor vector graphics, CRT glow,
generated terrain, and a fuel tank that has to last the whole run.

No install, no build step, no dependencies. Open `lunar-lander-dx.html` in a browser and play.
It works on desktop and on phones/tablets (landscape).

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
