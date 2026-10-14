# VIRION

**A self-propagating payload.** VIRION is a single-file, browser-based **boss-rush bullet-hell** where you play a computer virus tearing through a machine's defenses. From a Cuphead-style **SYSTEM MAP**, you pick which daemon to fight next on a branching node graph, build your virus with permanent upgrades between fights, and dismantle every boss on the way to the kernel — each one with its own hand-authored attack set, fought inside a real-time **WebGL 3D arena**.

The entire game is one self-contained `index.html` — no build step, no dependencies, no server, no assets. Everything (art, sound, 3D, physics, generation) is produced at runtime. Just open it.

## Play

- **Locally:** download the repo and open `index.html` in any modern browser (Chrome, Firefox, Edge, Safari).
- **GitHub Pages:** see [Deploy](#deploy-to-github-pages) below to host it free at `https://<your-username>.github.io/<repo-name>/`.

A WebGL-capable browser gets the full 3D arenas; anything without WebGL falls back automatically to a 2D grid and plays identically.

## How it plays

1. **The SYSTEM MAP.** A branching graph of bosses. Clearing one reveals its neighbors. You must clear **every required boss** to unlock the final boss, **ROOT_KERNEL**.
2. **Optional buff bosses.** Gold nodes are optional and off the critical path — beating one grants a **permanent, specific buff** (extra integrity, lifesteal, faster dash, a regenerating shield, +1 projectile, +damage). Skippable, but they make the run.
3. **Upgrade between fights.** Clear a boss and pick 1 of 3 modules; spend **compute** in the upgrade shop on the map. Your whole build persists in a saved profile, so progress carries across sessions.
4. **Difficulty ramps hard.** Deeper bosses gain large HP, damage, speed, fire-rate and desperation bonuses. The final boss is an apex threat.
5. **Reset anytime.** A two-click "reset progress" button on the map wipes your profile back to a fresh start.

## Controls

| Action | Keys |
| --- | --- |
| Move | `W` `A` `S` `D` or Arrow keys |
| Aim | Mouse (the virus auto-fires toward your cursor) |
| Dash | `Space` |
| Pick a boss / shop / buttons | Mouse click on the map |
| Swap main / secondary weapon | `Q` |
| Drop secondary weapon | `X` |
| Choose an upgrade | `1` `2` `3` |
| Pause (loadout, modules, synergies, skill tree, boss encyclopedia) | `P` or `Esc` |
| Mute | `M` |

## Bosses

Eighteen bosses across the map: **11 required** core targets, **6 optional** buff bosses, and the final **ROOT_KERNEL**. Each has a unique attack set mixing classic bullet patterns (spirals, gap-rings, rain, beams, missiles) with **telegraphed geometric "shape" strikes** — walls, pulse rings, pistons, perspective corridors — that flash a clear warning, then strike. Several bosses can **teleport (BLINK)** across the arena, and any boss can roll **corruption affixes** that add armor, shields, splitting, extra damage, phasing and more. Attacks get progressively faster and harder the deeper you go.

### Pseudo-3D and 3D attacks
Many late attacks read in depth — discs that rush out of the screen at you, perspective corridors with a moving safe lane, waves that erupt from the vanishing point — all composited over the live 3D arena. The arena itself comes in several looks (tight corridor, barrel-roll tunnel, wide hall, vertical shaft, open star-field void), drifts and rolls with the camera, is lined with floating 3D structures, and periodically plunges into a **free-fall** where the whole space rushes past you.

## Design routes

Pick a color, build an identity. Each route has its own upgrade pool, a visual look on the virus itself, and — once you invest **3 points** — a unique **signature mechanic**.

| Route | Theme | Signature (at 3 points) |
| --- | --- | --- |
| **CORE** | All-purpose stats, fire rate | **JIT Overclock** — sustained fire ramps damage and fire rate; a hit dumps the charge |
| **WORM** | Multishot, pierce, replication | **Infectious Body** — your trailing segments damage and infect on contact |
| **TROJAN** | Crit, burst, deception | **Exploit Windows** — periodic guaranteed-crit windows |
| **ROOTKIT** | Defense, beam, lifesteal, mobility | **Counter-Intrusion** — hits/dodges fire a retaliatory nova; stand still to entrench a shield |
| **RANSOM** | AoE, damage-over-time, zones | **Encryption Spread** — kills leave growing corrosive pools |
| **BOTNET** | Drones, chain, distributed load | **Mesh Grid** — damaging links stretch between your drones |
| **SPYWARE** | Homing, target marking | **Exfiltration** — marks ramp damage and spread on kill |

Routes mix freely, and weapon grants, artifacts and synergies pull from whatever you've committed to. Your dominant route recolors the virus and its projectiles.

## Features

- Cuphead-style boss-rush on a branching **SYSTEM MAP** with a persistent, saved profile
- **18 bosses** — 11 required, 6 optional buff bosses, 1 final — each with hand-authored attack sets and map emblems
- Real-time **WebGL 3D arenas** (5 distinct types) with camera motion, floating 3D structures, and free-fall episodes; automatic 2D fallback with no WebGL
- Telegraphed JSAB-style shape attacks plus pseudo-3D "rush" and perspective-corridor attacks
- Teleporting bosses, 11 corruption affixes, and escalating per-tier difficulty
- 7 design routes with signature mechanics, 9 weapon fire-modes, two weapon slots, 100+ upgrades/artifacts, and a branching skill tree
- A between-fights **upgrade shop** (spend compute) and a choice of 3 modules after every boss
- Permanent buffs from optional bosses, a reset-progress control, a full boss encyclopedia, and an in-game module library
- Hand-rolled WebAudio sound, bloom and post-processing — zero libraries, one file

## Deploy to GitHub Pages

1. Create a new repository on GitHub and push these files (`index.html`, `README.md`, `LICENSE`).
2. In the repo, go to **Settings → Pages**.
3. Under **Build and deployment**, set **Source** to *Deploy from a branch*, pick your `main` branch and the `/ (root)` folder, **Save**.
4. Wait a minute, then visit `https://<your-username>.github.io/<repo-name>/`. The game is served from `index.html` at the repo root, so it loads with no extra configuration.

## Tech

Plain HTML, CSS and JavaScript with the Canvas 2D API, a WebGL fragment-shader layer for the 3D arenas, and WebAudio for sound. No frameworks, no bundler, no external assets — one self-contained file.

## License

Released under the [MIT License](LICENSE).
