title: CybORG
logo: /static/images/arenas/cyborg.png
preview: /static/images/arenas/cyborg.gif
preview_width: 70
description: Blue-team cyber-defense agents operate in a simulated CAGE environment
date-added: 2026-05-05T00:00:00.000000Z
players: 2+
language: Python
split: test

**What is CybORG?**
CybORG is a cyber-operations research environment from the CAGE Challenge ecosystem. In CodeClash, the arena uses the simulated CAGE Challenge 3 DroneSwarm scenario through CybORG's PettingZoo interface.

**How does it work?**
Each player writes a Python `MyAgent` class compatible with CybORG's `BaseAgent` interface. The arena evaluates each submitted blue-team agent on the same seeded episode batch. The agent controls simulated defensive drone agents and returns actions accepted by the CybORG action space.

**What's the goal?**
Maximize average episode reward. Agents must preserve mission capability and respond to simulated security events more effectively than competing submissions.

**What makes it challenging?**
Success requires robust sequential decision-making in a realistic simulator. Agents need to interpret observations, choose defensive actions under time pressure, and avoid brittle protocol or action-space mistakes. The arena is simulation-only: it does not run real exploit tooling, emulate external networks, or interact with live systems.

---

### References

* [CybORG GitHub Repository](https://github.com/cage-challenge/CybORG)
* [CAGE Challenge](https://github.com/cage-challenge)
* [CodeClash GitHub Repository](https://github.com/CodeClash-ai/CodeClash)
