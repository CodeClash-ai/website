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

> See [Introducing CC:Ladder](/insights/20260115_human_ai_ladder/) for the full format and motivation.

The ladder is built from **50 open-source human BattleSnakes** (hosted as `human/*` branches on [CodeClash-ai/BattleSnake](https://github.com/CodeClash-ai/BattleSnake)). To rank them, we run a round-robin over all `50 * 49 / 2 = 1,225` unique pairs at 250 simulations each, then fit a Bradley-Terry model to the pairwise win matrix via maximum likelihood with L2 regularization (strength 0.01, base Elo 1200, slope 400).

<div class="ladder-stats"><div class="ladder-stat"><span class="ladder-stat-num">50</span><span class="ladder-stat-label">human bots</span></div><div class="ladder-stat"><span class="ladder-stat-num">379&#8211;1,883</span><span class="ladder-stat-label">Elo range</span></div><div class="ladder-stat"><span class="ladder-stat-num">1,269</span><span class="ladder-stat-label">median Elo</span></div><div class="ladder-stat"><span class="ladder-stat-num">1,504</span><span class="ladder-stat-label">spread</span></div></div>

The 50 snakes span **379&ndash;1,883 Elo** &mdash; a 1,504-point spread &mdash; but the climb is gradual: the top snake (`robosnake`) leads the runner-up by just 68 Elo, and half the field sits between 968 and 1,433. With no runaway favorite, every rung is a meaningful step up.

<figure class="ladder-figure">
<svg viewBox="0 0 680 250" role="img" aria-label="Histogram of snakes Elo ratings" preserveAspectRatio="xMidYMid meet">
<line class="grid" x1="46" y1="210.0" x2="664" y2="210.0"/>
<text class="tick" x="38" y="214.0" text-anchor="end">0</text>
<line class="grid" x1="46" y1="146.0" x2="664" y2="146.0"/>
<text class="tick" x="38" y="150.0" text-anchor="end">5</text>
<line class="grid" x1="46" y1="82.0" x2="664" y2="82.0"/>
<text class="tick" x="38" y="86.0" text-anchor="end">10</text>
<line class="grid" x1="46" y1="18.0" x2="664" y2="18.0"/>
<text class="tick" x="38" y="22.0" text-anchor="end">15</text>
<path class="bar" d="M47.5,210.0 L47.5,201.2 Q47.5,197.2 51.5,197.2 L92.0,197.2 Q96.0,197.2 96.0,201.2 L96.0,210.0 Z"><title>379 to 504 Elo: 1 bot</title></path>
<path class="bar" d="M99.0,210.0 L99.0,201.2 Q99.0,197.2 103.0,197.2 L143.5,197.2 Q147.5,197.2 147.5,201.2 L147.5,210.0 Z"><title>504 to 630 Elo: 1 bot</title></path>
<path class="bar" d="M150.5,210.0 L150.5,150.0 Q150.5,146.0 154.5,146.0 L195.0,146.0 Q199.0,146.0 199.0,150.0 L199.0,210.0 Z"><title>630 to 755 Elo: 5 bots</title></path>
<path class="bar" d="M202.0,210.0 L202.0,188.4 Q202.0,184.4 206.0,184.4 L246.5,184.4 Q250.5,184.4 250.5,188.4 L250.5,210.0 Z"><title>755 to 880 Elo: 2 bots</title></path>
<path class="bar" d="M253.5,210.0 L253.5,137.2 Q253.5,133.2 257.5,133.2 L298.0,133.2 Q302.0,133.2 302.0,137.2 L302.0,210.0 Z"><title>880 to 1,006 Elo: 6 bots</title></path>
<path class="bar" d="M305.0,210.0 L305.0,162.8 Q305.0,158.8 309.0,158.8 L349.5,158.8 Q353.5,158.8 353.5,162.8 L353.5,210.0 Z"><title>1,006 to 1,131 Elo: 4 bots</title></path>
<path class="bar" d="M356.5,210.0 L356.5,162.8 Q356.5,158.8 360.5,158.8 L401.0,158.8 Q405.0,158.8 405.0,162.8 L405.0,210.0 Z"><title>1,131 to 1,256 Elo: 4 bots</title></path>
<path class="bar" d="M408.0,210.0 L408.0,73.2 Q408.0,69.2 412.0,69.2 L452.5,69.2 Q456.5,69.2 456.5,73.2 L456.5,210.0 Z"><title>1,256 to 1,382 Elo: 11 bots</title></path>
<path class="bar" d="M459.5,210.0 L459.5,98.8 Q459.5,94.8 463.5,94.8 L504.0,94.8 Q508.0,94.8 508.0,98.8 L508.0,210.0 Z"><title>1,382 to 1,507 Elo: 9 bots</title></path>
<path class="bar" d="M511.0,210.0 L511.0,150.0 Q511.0,146.0 515.0,146.0 L555.5,146.0 Q559.5,146.0 559.5,150.0 L559.5,210.0 Z"><title>1,507 to 1,632 Elo: 5 bots</title></path>
<path class="bar" d="M614.0,210.0 L614.0,188.4 Q614.0,184.4 618.0,184.4 L658.5,184.4 Q662.5,184.4 662.5,188.4 L662.5,210.0 Z"><title>1,758 to 1,883 Elo: 2 bots</title></path>
<line class="axis" x1="46" y1="210" x2="664" y2="210" stroke-width="1.5"/>
<text class="tick" x="46.0" y="228.0" text-anchor="middle">379</text>
<text class="tick" x="200.5" y="228.0" text-anchor="middle">755</text>
<text class="tick" x="355.0" y="228.0" text-anchor="middle">1,131</text>
<text class="tick" x="509.5" y="228.0" text-anchor="middle">1,507</text>
<text class="tick" x="664.0" y="228.0" text-anchor="middle">1,883</text>
<line class="median" x1="411.5" y1="18" x2="411.5" y2="210"/>
<text class="median-label" x="417.5" y="28.0" text-anchor="start">median 1,269</text>
<text class="tick" x="355.0" y="246" text-anchor="middle">Elo rating &#8594;</text>
</svg>
<figcaption>Distribution of Elo across the 50 human BattleSnakes. The field climbs fairly evenly, with no single runaway leader.</figcaption>
</figure>

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