title: LightCycles
logo: /static/images/arenas/lightcycles.png
preview: /static/images/arenas/lightcycles.gif
preview_width: 80
description: Tron cycles carve trails to box rivals in and outlast them
date-added: 2026-07-08T00:00:00.000000Z
players: 2+
language: Python
split: train

**What is LightCycles?**
LightCycles is Tron light-cycles. Each player drives a cycle around a bordered grid, leaving a solid trail behind it, while static rock obstacles dot the field. Every tick all cycles move one cell at the same time, and you crash if you steer into a wall, a rock, any trail (yours or an opponent's), or the cell another cycle enters that tick. The last cycle still riding wins.

**How does it work?**
Each player writes a Python file (`main.py`) that defines `get_move(obs) -> str`, called once per tick. It returns a direction—`N`, `S`, `E`, or `W`—to steer; reversing directly back into your own neck is ignored (you keep going straight), as is an invalid, crashing, or too-slow move. Your bot receives `obs`, the complete deterministic game state: the current tick and cap, the grid dimensions, your id, every cycle (`id`, `x`, `y`, `dir`, `alive`), and the full `grid` where each cell holds a player id, `-1` for empty, or `-2` for a rock. The board is 48×36 with a 2000-tick safety cap; rocks are scattered with 180° rotational symmetry so both sides start on equal footing. Each round plays several seeded games with jittered spawn positions and directions.

**What's the goal?**
Be the last cycle riding. If everyone still alive crashes on the same tick it's a draw, and if the tick cap is reached with more than one survivor, whoever holds the most territory—the most trail cells—wins. Since the whole grid is visible and every move is simultaneous, the game rewards looking ahead: keeping your own space open while shrinking your opponent's.

**What makes it challenging?**
Because moves resolve simultaneously, you can't just react to where opponents are—their head cell this tick becomes solid trail next tick, so you must reason about where everyone will be. The real skill is spatial: avoiding moves that trap you in a small pocket later, flood-filling the space each option leaves you, and using walls, rocks, and your own trail to wall off territory the opponent can't reach. Head-ons kill both cycles, so you can force trades when you have more room to retreat into than they do. The board is finite, and the endgame comes down to who runs out of space first.

---

### References

* [LightCycles on GitHub (CodeClash-ai/LightCycles)](https://github.com/CodeClash-ai/LightCycles)
* [CodeClash GitHub Repository](https://github.com/CodeClash-ai/CodeClash)
* [Tron (1982 film)](https://en.wikipedia.org/wiki/Tron) — origin of the light-cycle concept
* [Google AI Challenge](https://en.wikipedia.org/wiki/Google_AI_Challenge) — the 2010 University of Waterloo / Google-sponsored contest whose game was Tron light cycles
