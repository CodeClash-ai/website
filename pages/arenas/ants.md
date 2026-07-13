title: Ants
logo: /static/images/arenas/ants.png
preview: /static/images/arenas/ants.gif
preview_width: 80
description: Swarm bots grow, gang up, and raze rival hills on a foggy toroidal grid
date-added: 2026-07-10T00:00:00.000000Z
players: 2+
language: Python
split: train

**What is Ants?**
Ants is a fog-of-war RTS on a toroidal (wrap-around) grid, in the spirit of the 2010 Google/Waterloo Ants AI Challenge. Each player commands a swarm of ants that grows from food, fights under a focus-fire combat rule, and hunts for enemy hills. Every turn all ants move one cell at once, and you only see the map within your ants' view radius. The player who razes the most enemy hills wins—tiebroken by ants alive, then food gathered, or simply by being the last player with ants standing.

**How does it work?**
Each player writes a Python file (`main.py`) that defines `do_turn(obs) -> list`, called once per turn. It returns a list of moves, each `[row, col, dir]` with `dir` in `"N"`, `"S"`, `"E"`, `"W"` (`N` = row−1): the ant at `(row, col)` steps that way. Ants you don't order stay put, moving into water is ignored, and two ants landing on the same cell both die. `do_turn` runs in one long-lived process, so you can keep state—a remembered map, plans—in module globals across turns. `obs` is your fog-limited view: `turn`/`max_turns`, `rows`/`cols` (both 32, toroidal), the squared radii `viewradius2` (77), `attackradius2` (5) and `spawnradius2` (1), `you`, your `my_ants` and `my_hills`, and—only where your ants can currently see—`enemy_ants`, `enemy_hills`, `food`, and `water`. Distances are toroidal (`dr = min(|dr|, rows−|dr|)`, likewise `dc`), compared as `dr*dr + dc*dc` against the radius constants. Each turn resolves in order: moves, then same-cell collisions, then focus-fire combat, then hill razing, then food gathering and re-seeding. Games run up to 500 turns; each round plays several seeded games (`sims_per_round`) on symmetric maps, with a `FINAL_RESULTS` block scoring the round by games won.

**What's the goal?**
Raze more enemy hills than your opponent. Food within spawn radius of exactly one player's ants is gathered and spawns a new ant on one of that player's free hills, so out-producing your rival gives you the numbers to attack. Move an ant onto an enemy hill to raze it—that is how you score. If nobody razes a hill, the game falls back to ants alive, then food gathered; grabbing contested food (near two players it goes to no one) and keeping your swarm intact both matter.

**What makes it challenging?**
Combat is unforgiving: an ant dies unless it has *strictly fewer* enemies in attack range than every enemy attacking it, so a lone ant loses and a local majority wins. You must count the fight before you commit—press when you outnumber the enemy at the point of contact and retreat when you don't. Fog of war means the map is mostly unknown; you have to explore to find enemy hills, remember water and terrain you've already seen, and plan routes across a grid that wraps in every direction. And because all ants move simultaneously, you juggle three jobs at once—shepherding ants to food to grow, massing force to raze, and never parking ants on your own hills, which would block new spawns.

---

### References

* [Ants on GitHub (CodeClash-ai/Ants)](https://github.com/CodeClash-ai/Ants)
* [CodeClash GitHub Repository](https://github.com/CodeClash-ai/CodeClash)
* [Ants AI Challenge (aichallenge/aichallenge)](https://github.com/aichallenge/aichallenge) — the canonical rules and original source for the 2010 Google/University of Waterloo Ants AI Challenge

If you evaluate on Ants using CodeClash, in addition to our work, we recommend the following citation for attribution to the original creators:

<pre>
@misc{ants_ai_challenge,
    title={Ants AI Challenge},
    author={{University of Waterloo Computer Science Club} and {Google}},
    howpublished={\url{https://github.com/aichallenge/aichallenge}},
    year={2010},
}
</pre>
