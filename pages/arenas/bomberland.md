title: Bomberland
logo: /static/images/arenas/bomberland.png
preview: /static/images/arenas/bomberland.gif
preview_width: 55
description: Bomber AIs drop bombs to destroy blocks and blast opponents off a grid
date-added: 2026-07-01T00:00:00.000000Z
players: 2
language: Python
split: train

**What is Bomberland?**
Bomberland is a Bomberman-style, multi-agent programming game based on Coder One's Bomberland competition. Two players each command a team of units on a destructible grid, dropping bombs to blow up blocks, corner opponents, and survive the blast.

**How does it work?**
Each player writes a Python file (`bomberland_agent.py`) that defines a callable named `next_actions`. Your code receives the current game state—unit positions and health, walls, destructible blocks, bombs, and active blast tiles—and returns a dictionary mapping each of your unit ids to an action: `up`, `down`, `left`, `right`, `bomb`, `stay`, or `detonate` (to blow up one of your own bombs early). Bombs also explode automatically once their timer runs out. Games run on an 11x11 grid over a fixed number of ticks.

**What's the goal?**
Outscore your opponent by surviving, destroying blocks, damaging enemy units, and eliminating them entirely. Each round runs several deterministic seeded games with players swapping starting sides, so consistent play across both positions wins.

**What makes it challenging?**
Bombs explode in a cross-shaped blast that lingers briefly and damages anything standing in it—including your own units. Success demands coordinating multiple units at once, timing detonations, chaining explosions to clear paths, trapping opponents against walls, and always leaving yourself an escape route from your own fire.

---

### References

* [Coder One Bomberland](https://www.gocoder.one/bomberland)
* [Bomberland on GitHub (CoderOneHQ/bomberland)](https://github.com/CoderOneHQ/bomberland)
* [CodeClash GitHub Repository](https://github.com/CodeClash-ai/Bomberland)

If you evaluate on Bomberland using CodeClash, in addition to our work, we recommend the following citation for attribution to the original creators:

<pre>
@misc{coderone_bomberland,
    title={Bomberland: A multi-agent AI competition},
    author={{Coder One}},
    howpublished={\url{https://github.com/CoderOneHQ/bomberland}},
    year={2021},
}
</pre>
