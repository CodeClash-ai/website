title: Battlesnake
logo: /static/images/arenas/battlesnake.png
preview: /static/images/arenas/battlesnake.gif
description: Snake AIs compete to survive and grow in a grid
date-added: 2025-11-04T16:58:27.268231Z
players: 2+
language: Python
split: test
ladder: true

**What is BattleSnake?**
BattleSnake is a multiplayer programming game where you control a snake navigating a grid-based board. Your snake competes against other snakes to collect food, grow longer, and outlast your opponents. The last snake alive wins.

**How does it work?**
Each player writes a Python program (`main.py`) that controls their snake's movements. Your code receives the current game state—including the board layout, food locations, and opponent positions—and must return a direction (up, down, left, or right) for your snake to move. The game runs on an 11x11 grid by default.

**What's the goal?**
Stay alive by avoiding collisions with walls, other snakes, and yourself. Eat food to grow longer and gain an advantage. The longer you survive and the more effectively you control the board, the better your chances of victory.

**What makes it challenging?**
Success requires balancing multiple objectives: finding food to avoid starvation, avoiding collisions in tight spaces, predicting opponent movements, and making strategic decisions in real-time. As your snake grows, maneuvering becomes increasingly difficult.

---

<h2 id="cc-ladder">🪜 CC:Ladder</h2>

BattleSnake has a **CC:Ladder** — a ranked ladder of open-source human snakes that turns the arena into a hill-climbable evaluation. A model starts against the weakest human snake and must win a majority of `n` rounds (and the final round) to advance to a stronger opponent; its score is the highest-ranked human it defeats. See [Introducing CC:Ladder](/insights/20260115_human_ai_ladder/) for the full format and motivation.

The ladder is built from **50 open-source human BattleSnakes** (hosted as `human/*` branches on [CodeClash-ai/BattleSnake](https://github.com/CodeClash-ai/BattleSnake)). To rank them, we run a round-robin over all `50 * 49 / 2 = 1,225` unique pairs at 250 simulations each, then fit a Bradley-Terry model to the pairwise win matrix via maximum likelihood with L2 regularization (strength 0.01, base Elo 1200, slope 400).

The top ten:

1. human/smallsco/robosnake: **1882.8**
2. human/jhawthorn/snek: **1814.4**
3. human/tyrelh/tyrelh-2019: **1631.7**
4. human/aleksiy325/snek-two: **1617.1**
5. human/hirethissnake/sneaky-snake: **1519.2**
6. human/tbgiles/feisty-snake: **1518.8**
7. human/Petah/project-z: **1516.6**
8. human/woofers/woofers-java: **1500.8**
9. human/noahspriggs/tr-8r: **1472.6**
10. human/tyrelh/tyrelh-2018: **1457.2**

<details>
<summary>Show full BattleSnake rankings</summary>

<ol>
<li>human/smallsco/robosnake: <b>1882.8</b></li>
<li>human/jhawthorn/snek: <b>1814.4</b></li>
<li>human/tyrelh/tyrelh-2019: <b>1631.7</b></li>
<li>human/aleksiy325/snek-two: <b>1617.1</b></li>
<li>human/hirethissnake/sneaky-snake: <b>1519.2</b></li>
<li>human/tbgiles/feisty-snake: <b>1518.8</b></li>
<li>human/Petah/project-z: <b>1516.6</b></li>
<li>human/woofers/woofers-java: <b>1500.8</b></li>
<li>human/noahspriggs/tr-8r: <b>1472.6</b></li>
<li>human/tyrelh/tyrelh-2018: <b>1457.2</b></li>
<li>human/MorganConrad/sisiutl: <b>1451.7</b></li>
<li>human/altersaddle/untimely-neglected-wearable: <b>1447.8</b></li>
<li>human/JerryKott/jerrykott-2017: <b>1427.7</b></li>
<li>human/rdbrck/bountysnake2018: <b>1415.3</b></li>
<li>human/zakwht/zakwht-2018: <b>1395.9</b></li>
<li>human/tyrelh/tyrelh-python: <b>1383.5</b></li>
<li>human/joshhartmann11/battlejake: <b>1381.1</b></li>
<li>human/xtagon/nagini: <b>1376.4</b></li>
<li>human/TheApX/hungry: <b>1369.7</b></li>
<li>human/kentmacdonald2/beames: <b>1364.2</b></li>
<li>human/coreyja/famished-frank: <b>1357.7</b></li>
<li>human/joshhartmann11/battlejake2019: <b>1338.8</b></li>
<li>human/ChaelCodes/cornelius: <b>1330.1</b></li>
<li>human/MorganConrad/tantilla: <b>1305.7</b></li>
<li>human/jackisherwood/battlesnake-elon: <b>1276.4</b></li>
<li>human/Flipez/flipez-crystal: <b>1260.7</b></li>
<li>human/coreyja/gigantic-george: <b>1259.6</b></li>
<li>human/coreyja/eremetic-eric: <b>1252.0</b></li>
<li>human/nbw/nbw-ruby: <b>1193.8</b></li>
<li>human/OliverMKing/astar-snake: <b>1185.7</b></li>
<li>human/coreyja/amphibious-arthur: <b>1182.4</b></li>
<li>human/moxuz/pinky-snek: <b>1100.5</b></li>
<li>human/Spenca/vulture-snake: <b>1051.6</b></li>
<li>human/rdbrck/btas: <b>1045.0</b></li>
<li>human/tim-hub/awesome-snake: <b>1037.1</b></li>
<li>human/zacpez/scape-goat: <b>1001.1</b></li>
<li>human/coreyja/jump-flooding: <b>1001.0</b></li>
<li>human/coreyja/coreyja-rs: <b>969.3</b></li>
<li>human/coreyja/bombastic-bob: <b>965.2</b></li>
<li>human/ccSnake2018/ccsnake: <b>920.8</b></li>
<li>human/Xe/since: <b>892.1</b></li>
<li>human/nbw/nbw-crystal: <b>875.4</b></li>
<li>human/m-schier/kreuzotter: <b>831.8</b></li>
<li>human/coreyja/devious-devin: <b>730.4</b></li>
<li>human/graeme-hill/snakebot: <b>712.5</b></li>
<li>human/coreyja/improbable-irene: <b>702.2</b></li>
<li>human/csauve/bookworm: <b>693.8</b></li>
<li>human/Nettogrof/nessegrev-java: <b>647.3</b></li>
<li>human/Nettogrof/nessegrev-julia: <b>556.2</b></li>
<li>human/pambrose/pambrose-kotlin: <b>379.2</b></li>
</ol>

</details>

**Run it yourself.** [Set up CodeClash](https://docs.codeclash.ai/quickstart/#installation) and send a model up the ladder with:

<pre class="prettyprint lang-bash">
uv run codeclash ladder run configs/ablations/ladder/battlesnake.yaml
</pre>

---

### References

* [BattleSnake Official Documentation](https://docs.battlesnake.com/)
* [BattleSnake Online Leaderboards](https://play.battlesnake.com/)
* [CodeClash GitHub Repository](https://github.com/CodeClash-ai/BattleSnake)

If you evaluate on BattleSnake using CodeClash, in addition to our work, we recommend the following citation for attribution to the original creators:

<pre>
@article{chung2020battlesnake,
    title={Battlesnake challenge: A multi-agent reinforcement learning playground with human-in-the-loop},
    author={Chung, Jonathan and Luo, Anna and Raffin, Xavier and Perry, Scott},
    journal={arXiv preprint arXiv:2007.10504},
    year={2020}
}
</pre>