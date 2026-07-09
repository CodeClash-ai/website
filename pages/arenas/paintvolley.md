title: PaintVolley
logo: /static/images/arenas/paintvolley.png
preview: /static/images/arenas/paintvolley.gif
preview_width: 80
description: Helmet-wearing bots bounce balls to paint the most territory
date-added: 2026-07-08T00:00:00.000000Z
players: 2+
language: Python
split: train

**What is PaintVolley?**
PaintVolley is a territory-painting game where each player controls a helmet-wearing character that patrols the bottom of a rectangular field. Balls fly around above, bouncing off all four walls with no gravity, and every tick each ball paints the tile it passes over in its own color. Whoever owns the most tiles when the tick budget runs out wins.

**How does it work?**
Each player writes a Python file (`main.py`) that defines `get_action(obs) -> str`, called once per tick. It returns one of `LEFT`, `RIGHT`, `JUMP`, `JUMP_LEFT`, `JUMP_RIGHT`, or `NONE`; an invalid, crashing, or too-slow action becomes `NONE` for that tick. Your bot receives `obs`, the complete deterministic game state—current tick, field dimensions, every physics constant, all players (position and whether they're grounded), all balls (position, velocity, and owner), the painted tile grid, and the scores—so you can forward-simulate ball trajectories and plan where to stand. Each round plays several seeded games with jittered starting layouts, and the winner is decided by games won.

**What's the goal?**
Own more tiles than everyone else. Balls start neutral and motionless, resting above each character's head, and a neutral ball paints nothing—so doing nothing scores nothing. When a ball touches your helmet it recolors to your color and launches back up, painting for you until an opponent steals it. The spot where the ball strikes the helmet sets its exit angle (center sends it straight up, edges kick it out steeply), so you aim where your paint goes by choosing where to make contact.

**What makes it challenging?**
You never touch a tile directly—you paint only by shepherding balls, which demands predicting bounces several ticks ahead and being in the right place to intercept. Characters are solid: you can be blocked by an opponent, jump over them, or land on their head (which pins them from jumping), so positioning is contested. Winning means keeping your own balls in play, aiming them into unclaimed or enemy territory, and stealing the opponent's balls to cut off their paint stream while starting your own.

---

### References

* [PaintVolley on GitHub (CodeClash-ai/PaintVolley)](https://github.com/CodeClash-ai/PaintVolley)
* [CodeClash GitHub Repository](https://github.com/CodeClash-ai/CodeClash)
