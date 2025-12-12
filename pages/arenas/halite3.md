title: Halite III
logo: /static/images/arenas/halite3.png
preview: /static/images/arenas/halite3.gif
preview_width: 70
description: Navigate ships to collect halite and maximize resources
date-added: 2025-12-10T16:58:27.268231Z
players: 2+
language: Cplusplus, OCaml, Rust
split: train

**What is Halite III?**
Halite III is a resource management game where bots command ships that explore a grid-based ocean to collect halite. Players compete to accumulate the most stored halite by efficiently harvesting resources from the sea and managing their fleet.

**How does it work?**
You start with a shipyard and can build ships to navigate a 2D grid map. Ships move one cell per turn in cardinal directions, collecting 25% of halite when stationary or spending 10% movement costs when traveling. Ships automatically deposit cargo at your shipyard or dropoff points, and can convert into new dropoffs.

**What's the goal?**
Accumulate the most stored halite by game end (400-500 turns). Balance building ships, establishing dropoffs, and harvesting efficiently. Ships that collide are destroyed, dropping cargo into the sea, while inspired ships near opponents gain 200% collection bonuses.

**What makes it challenging?**
Success requires optimizing the economy of ship construction (1000 halite), dropoff placement (4000 halite), and collection efficiency. You must balance expansion with harvesting, avoid costly collisions, exploit inspiration bonuses, and manage movement costs on depleted cells.

---

### References

* [Halite III Official Repository](https://github.com/HaliteChallenge/Halite-III)
* [Halite Website](https://halite3webapp.azurewebsites.net/)
* [CodeClash GitHub Repository](https://github.com/CodeClash-ai/Halite3)

<pre>
@misc{halite2016,
    title={Halite III: Season 3 of @twosigma's artificial intelligence programming challenge},
    author={Two Sigma},
    url={https://github.com/HaliteChallenge/Halite-III},
    year={2018}
}
</pre>