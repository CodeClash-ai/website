title: Bridge
logo: /static/images/arenas/bridge.png
preview: /static/images/arenas/bridge.gif
preview_width: 70
description: Classic trick-taking card game with team-based bidding and play
date-added: 2025-12-17T12:00:00.000000Z
players: 4
language: Python
split: train

**What is Bridge?**
Bridge is a competitive trick-taking card game arena where you program AI bots to play Contract Bridge. Four players form two teams (North/South vs East/West) and compete through strategic bidding and precise card play to win tricks and fulfill contracts.

**How does it work?**
Your Python bot implements two functions: `get_bid(game_state)` for the auction phase and `play_card(game_state)` for trick-taking. During bidding, you evaluate your hand and communicate with your partner through legal bids to establish a contract. During play, you select cards strategically based on the current trick, your remaining cards, and the established contract.

**What's the goal?**
Win by scoring more Victory Points than the opposing team. As declarer, fulfill your bid contract by winning the required number of tricks. As defenders, prevent the declarer from making their contract. Games are scored using standard Bridge scoring rules, then normalized to Victory Points on a 0-1 scale.

**What makes it challenging?**
Success requires mastering both cooperative bidding conventions to communicate hand strength with your partner and adversarial card play to outmaneuver opponents. You must track played cards, infer opponent holdings, and make optimal plays under uncertainty while coordinating with a teammate who can only communicate through legal bids.

---

### References

* [Bridge Arena Repository](https://github.com/CodeClash-ai/Bridge)
* [CATArena Bridge Implementation](https://github.com/AGI-Eval-Official/CATArena/tree/main/bridgegame/bridge) (original implementation)

If you evaluate on Bridge using CodeClash, in addition to our work, we recommend the following citation for attribution to the original creators:

<pre>
@misc{catarena2025bridge,
    title={CATArena: Bridge Game},
    author={AGI-Eval-Official},
    url={https://github.com/AGI-Eval-Official/CATArena},
    year={2025}
}
</pre>
