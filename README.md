# Avatar Dash

**▶ [Play now](https://renrenmimi.github.io/avatar-dash/)** — runs in your browser, nothing to install.

A six-level side-scrolling platformer across three themed worlds. The player starts as
my GitHub avatar, then transforms into a larger dog avatar after collecting a dog treat.
Run, jump, stomp enemies, collect coins, and reach each flag.

![The level, with the avatar on the starting platform](docs/screenshot.jpg)

*The level, with the avatar on the starting platform*

## Controls

| Action | Keys |
|---|---|
| Move | `←` `→` or `A` `D` |
| Jump | `Space`, `W` or `↑` — hold longer to jump higher |
| Restart | `R` |
| Pause | `P` |

On a touch screen the on-screen buttons appear automatically.

## What is in it

- **Variable-height jumping** — releasing the key early cuts the rise short, so tap height differs from hold height
- **Coyote time and input buffering** — you can still jump for 100 ms after walking off an
  edge, and a jump pressed just before landing still fires.
- **Stomp to kill** — landing on an enemy squashes it and bounces you; touching one from the
  side costs a life
- **Enemies turn at edges** — they check for ground ahead and reverse instead of walking off
- **Six progressively longer levels** across Neon Skyline, Sunset Canyon, and Moonlit Grove
- **Dog Mode power-up** — treats transform the player into a larger dog; the next enemy hit
  removes the transformation instead of costing a life
- **Full-run progression** — score, lives, coins, time, and active Dog Mode carry between levels
- **Best times per level and a full-run completion time**, kept in `localStorage` and shown on
  the title roster, the clear screen, and the HUD. Beating one is called out on the spot, and a
  button on the title screen wipes every stored time and ghost.
- **Ghost replay** — your best run of a level comes back as a translucent racer. It is a
  position trace sampled 20 times a second, stored as two-character deltas and capped at 900
  samples, so a long run halves its own sample rate instead of growing without bound. The HUD
  shows how far ahead or behind that ghost you are.
- **Level select** from the title screen, so a level can be practised against its own ghost
- **Fixed timestep physics** at 120 Hz, decoupled from the render loop, so the feel does not
  change with frame rate
- **Parallax background**, screen shake on impact, and particle bursts

## Tech

Canvas 2D with no runtime dependencies. The starting avatar is embedded in the HTML;
the optimized Dog Mode portrait is included as a local PNG asset.

Physics and level layout were verified with a Node script before release: no tunnelling
through blocks at full speed, jump height clears a two-tile gap, the flag has ground under
it, and every enemy stands on a platform.

## A note on naming

This is an original game. It is **not** affiliated with, endorsed by, or derived from any
existing game franchise — no third-party artwork, names, audio, or level data are used. The
genre conventions (run, jump, stomp, flag) are just that: conventions.

---

© 2026 Weiren Feng. All rights reserved.
