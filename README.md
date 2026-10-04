# VIRION

**A self-propagating payload.** VIRION is a single-file, browser-based roguelite bullet-hell where you play a computer virus burrowing down through a machine's filesystem — `/tmp` all the way to `/root` — mutating your own code as you go. Every run you pick a *design route*, chain together upgrades and synergies, crack data caches with a rhythm minigame, and fight versioned bosses with randomized attack patterns and corruptions.

The entire game is one self-contained `index.html` — no build step, no dependencies, no server. Just open it.

## Play

- **Locally:** download the repo and open `index.html` in any modern browser (Chrome, Firefox, Edge, Safari). That's it.
- **GitHub Pages:** see [Deploy](#deploy-to-github-pages) below to host it for free at `https://<your-username>.github.io/<repo-name>/`.

## Controls

| Action | Keys |
| --- | --- |
| Move | `W` `A` `S` `D` or Arrow keys |
| Aim | Mouse (the virus auto-fires toward your cursor) |
| Dash | `Space` |
| Swap main / secondary weapon | `Q` |
| Drop secondary weapon | `X` |
| Open skill tree | `T` |
| Interact / crack a data cache (Signal Sync) | `F` |
| Choose an upgrade / curse | `1` `2` `3` |
| Choose a cache reward | `1` `2` |
| Signal Sync (rhythm) lanes | `D` `F` `J` `K` or click the lanes |
| Pause | `P` or `Esc` |
| Mute | `M` |

## Design routes

Pick a color, build an identity. Each route has its own upgrade pool, visual look on the virus itself, and — once you invest **3 points** into it — a unique **signature mechanic** that changes how the route actually plays.

| Route | Theme | Signature (unlocks at 3 points) |
| --- | --- | --- |
| **CORE** | All-purpose stats, fire rate | **JIT Overclock** — sustained combat ramps your damage *and* fire rate; taking a hit dumps the charge |
| **WORM** | Multishot, pierce, replication | **Infectious Body** — your trailing segments damage and infect enemies they touch |
| **TROJAN** | Crit, burst, deception | **Exploit Windows** — periodic bursts where every shot is a guaranteed crit |
| **ROOTKIT** | Defense, beam, lifesteal, mobility | **Counter-Intrusion** — getting hit or dodging fires a retaliatory nova; stand still to entrench a shield |
| **RANSOM** | AoE, damage-over-time, zones | **Encryption Spread** — kills leave growing corrosive pools |
| **BOTNET** | Drones, chain, distributed load | **Mesh Grid** — damaging links stretch between your drones |
| **SPYWARE** | Homing, target marking | **Exfiltration** — marks ramp up damage over time and spread to nearby enemies on kill |

Routes mix freely — a WORM/TROJAN hybrid, a BOTNET/SPYWARE drone-marker, etc. — and weapon grants, artifacts, and synergies pull from whatever you've committed to. Your dominant route also recolors the virus and its projectiles.

## Features

- 7 design routes with distinct playstyles, signature mechanics, and synergies
- 9 weapon fire-modes (packet, sawblade, railgun, homing missiles, cutting beam, scatter, boomerang, tesla chain, flamethrower) plus per-weapon variant upgrades
- Two weapon slots (a full-power main and a capped secondary) you can swap and drop on the fly
- A branching skill tree across four disciplines, earned with skill points on level-up
- 7 themed floors with procedurally generated rooms (8 room shapes, multiple layouts)
- 14+ enemy types, elite modifiers, and a surge system that spawns tougher "over-paced" encounters
- 13 boss archetypes with versioned names, shuffled dodgeable attack patterns, and 10 corruption affixes
- Data caches cracked via a 4-lane rhythm minigame for artifacts, new weapons, or compute
- A between-floors curse system: pick which way the machine fights back
- 20 cache-exclusive artifacts, 12 synergies, 4 difficulty levels
- WebAudio sound, bloom, and post-processing — all hand-rolled, zero libraries

## Deploy to GitHub Pages

1. Create a new repository on GitHub and upload these files (or `git push` them).
2. In the repo, go to **Settings → Pages**.
3. Under **Build and deployment**, set **Source** to *Deploy from a branch*, pick your `main` branch and the `/ (root)` folder, and **Save**.
4. Wait a minute, then visit `https://<your-username>.github.io/<repo-name>/`. Because the game is served from `index.html` at the repo root, it loads with no extra configuration.

## Tech

Plain HTML, CSS, and JavaScript with the Canvas 2D API and WebAudio. No frameworks, no bundler, no external assets — everything (art, sound, physics, generation) is generated at runtime in a single file.

## License

Released under the [MIT License](LICENSE). Swap in whatever license you prefer before publishing if MIT isn't what you want.
