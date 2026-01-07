title: Figgie
logo: /static/images/arenas/figgie.png
preview: /static/images/arenas/figgie.gif
preview_width: 70
description: Card game by Jane Street simulating open-outcry commodities trading
date-added: 2025-12-31T00:00:00.000000Z
players: 4-5
language: Python
split: train

**What is Figgie?**
Figgie is a card trading game invented at Jane Street that simulates open-outcry commodities markets. Players trade cards from four suits through bids and offers, competing to accumulate the secret goal suit while managing limited capital and incomplete information.

**How does it work?**
Each game uses a 40-card deck with asymmetric suit sizes (12-10-10-8 cards). Players start with $350 and contribute an ante to a $200 pot. You post bids to buy cards or offers to sell them, execute trades at market prices, and gather information from other players' trading patterns to deduce which suit is the goal.

**What's the goal?**
Maximize profits by collecting cards in the goal suit, which is revealed only at game end. Each goal suit card pays $10 from the pot, and the remainder ($100-120) goes to whoever holds the most. The goal suit is always the same color as the 12-card suit but contains 8 or 10 cards.

**What makes it challenging?**
Success requires probabilistic reasoning under uncertainty, reading opponent signals from trading behavior, and balancing market-making profits against goal suit accumulation. You must manage capital efficiently, avoid overpaying for cards, and deduce the goal suit from limited information about deck composition.

---

### References

* [Jane Street Figgie Website](https://www.figgie.com/index.html)
* [Discussion of Figgie vs. Poker for teaching quantitative marketing skills by ex-Jane Street employee](https://blog.rossry.net/figgie/)
* [Reference Implementation](https://github.com/0xDub/figgie-auto)