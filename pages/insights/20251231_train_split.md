title: Introducing Training Arenas
date: 2026-01-07
description: Nine new arenas, train models that are better long-running developers!
authors: Muhtasham Oblokulov, Aryan Siddiqui, John Yang

Since CodeClash's release, our top priority has been enabling practitioners to improve models as CodeClash competitors and ultimately, long-running, autonomous software developers.

As an initial step, we're releasing an initial set of **9** arenas that we're designating as the official "**train**" split of CodeClash (**CC:Train**).

- [Bridge](/arenas/bridge/)
- [Chess](/arenas/chess/)
- [Figgie](/arenas/figgie/)
- [Gomoku](/arenas/gomoku/)
- [Halite II](/arenas/halite2/)
- [Halite III](/arenas/halite3/)
- [MIT BattleCode 2023](/arenas/battlecode23/)
- [MIT BattleCode 2024](/arenas/battlecode24/)
- [MIT BattleCode 2025](/arenas/battlecode25/)

<div style="display:flex; gap:12px; justify-content:center;">
  <img src="/static/images/arenas/bridge.gif" alt="Arena 1" style="width:33%; height:auto; object-fit:cover;" />
  <img src="/static/images/arenas/chess.gif" alt="Arena 2" style="width:33%; height:auto; object-fit:cover;" />
  <img src="/static/images/arenas/figgie.gif" alt="Arena 3" style="width:33%; height:auto; object-fit:cover;" />
</div>
<div style="margin-top:0.5em; display:flex; gap:12px; justify-content:center;">
  <img src="/static/images/arenas/gomoku.gif" alt="Arena 1" style="width:33%; height:auto; object-fit:cover;" />
  <img src="/static/images/arenas/halite2.gif" alt="Arena 2" style="width:33%; height:auto; object-fit:cover;" />
  <img src="/static/images/arenas/halite3.gif" alt="Arena 3" style="width:33%; height:auto; object-fit:cover;" />
</div>
<div style="margin-top:0.5em; display:flex; gap:12px; justify-content:center;">
  <img src="/static/images/arenas/battlecode24.gif" alt="Arena 1" style="width:33%; height:auto; object-fit:cover;" />
  <img src="/static/images/arenas/battlecode24.gif" alt="Arena 2" style="width:33%; height:auto; object-fit:cover;" />
  <img src="/static/images/arenas/battlecode25.gif" alt="Arena 3" style="width:33%; height:auto; object-fit:cover;" />
</div>
<div style="margin-top:0.5em; text-align:center;">
    <span class="subtext">Introducing 9 new training arenas for CodeClash!</span>
</div>

**CC:Train** arenas span a range of properties, including:

- Perfect (Chess) vs. Imperfect Information (Bridge)
- Classical board games (Gomoku) vs. Custom competition formats (BattleCode)
- Head-to-head (Chess, Gomoku, BattleCode) vs. Multi-player (Figgie, Gomoku, Halite)

Today's models are mainly trained with tasks that use unit tests as verification (e.g., [SWE-bench](http://swebench.com/), [SWE-smith](https://swesmith.com/)).

We are curious if coding capabilities could improve by post-training on open-ended, competitive objectives.
Some ideas:

- Self play RL with competition outcomes as rewards
- Transferability.
    - Training on Halite II/III may likely lead to better performance on Halite I, but what about Gomoku?
    - Does training on open-ended code tasks (e.g., CodeClash, improving runtime [[1](https://swefficiency.com/), [2](https://swe-perf.github.io/), [3](https://gso-bench.github.io/)]) improve performance on in/out-of-distribution coding benchmarks?
- Mitigating [code slop and bad development practices](https://x.com/jyangballin/status/1986093913455968387) (e.g., single use scripts, redundant code, poor organization)
