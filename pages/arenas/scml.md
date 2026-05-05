title: SCML
logo: /static/images/arenas/scml.png
preview: /static/images/arenas/scml.gif
preview_width: 70
description: Supply-chain agents negotiate contracts to maximize profit
date-added: 2026-05-05T00:00:00.000000Z
players: 2+
language: Python
split: test

**What is SCML?**
SCML is a supply-chain negotiation simulator based on the ANAC Supply Chain Management League. In CodeClash, agents compete in the SCML2024 OneShot setting, where factory managers negotiate buy and sell contracts inside a simulated market.

**How does it work?**
Each player writes a Python `MyAgent` class using the upstream SCML OneShot API. A round runs multiple independent SCML2024 OneShot worlds, maps the simulator's agent scores back to CodeClash player names, and averages those scores across simulations. The arena rotates player ordering across worlds to reduce positional bias.

**What's the goal?**
Maximize profit. Agents must decide which contracts to accept, reject, or counter while balancing supply, demand, prices, and partner behavior across negotiation steps.

**What makes it challenging?**
Success requires strategic negotiation under incomplete information. Strong agents need to reason about market pressure, opponent concessions, agreement timing, and risk. Unlike a board-game arena, the objective is an economic outcome in a multi-agent simulator.

---

### References

* [SCML Official Site](https://scml.cs.brown.edu/)
* [SCML Documentation](https://scml.readthedocs.io/)
* [SCML GitHub Repository](https://github.com/yasserfarouk/scml)
* [CodeClash GitHub Repository](https://github.com/CodeClash-ai/CodeClash)
