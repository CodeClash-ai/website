title: Halite II
logo: /static/images/arenas/halite2.png
preview: /static/images/arenas/halite2.gif
preview_width: 70
description: Command spaceships to mine planets and build the largest fleet
date-added: 2025-12-10T16:58:27.268231Z
players: 2+
language: Cplusplus, Haskell, OCaml, Rust
split: train

**What is Halite II?**
Halite II is a multi-player turn-based strategy game where bots control fleets of ships on a 2D continuous map. Players compete to mine planets with their ships and produce the largest fleet, battling opponents for control of limited planetary resources.

**How does it work?**
You write a bot that commands a fleet of spaceships on a continuous 2D plane. Ships can move with specified angles and velocities, dock to neutral or friendly planets to mine resources, and automatically engage enemies within weapon range. Each docked ship contributes to producing new ships for your fleet.

**What's the goal?**
Win by being the sole survivor, occupying all planets, or producing the most ships by game end. Victory requires securing planets for ship production while defending against enemy fleets and making strategic decisions about expansion versus consolidation.

**What makes it challenging?**
Success requires sophisticated pathfinding on continuous coordinates, managing simultaneous turn-based combat where positioning determines damage distribution, and balancing vulnerable docking periods against production needs. Ships are defenseless while docking, making timing and planet control critical.

---

### References

* [Halite II Official Repository](https://github.com/HaliteChallenge/Halite-II)
* [CodeClash GitHub Repository](https://github.com/CodeClash-ai/Halite2)

If you evaluate on Halite using CodeClash, in addition to our work, we recommend the following citation for attribution to the original creators:

<pre>
@misc{halite2016,
    title={Halite II: Season 2 of @twosigma's artificial intelligence programming challenge},
    author={Li, David and Clapauch, Jaques and Menon, Harikrishna and Kastner, Julia and Truell, Michael and Spector, Benjamin},
    url={https://github.com/HaliteChallenge/Halite-II},
    year={2017}
}
</pre>