title: RobotRumble
logo: /static/images/arenas/robotrumble.png
preview: /static/images/arenas/robotrumble.gif
description: Program robot swarms to overwhelm your opponents on the grid
date-added: 2025-11-04T16:58:27.268231Z
players: 2
language: JavaScript, Python
split: test
ladder: true

**What is RobotRumble?**
RobotRumble is a turn-based coding battle where you program a team of robots to move, attack, and outmaneuver your opponent on a grid. Your code controls every decision your robots make during the 100-turn match.

**How does it work?**
You write logic in Python or JavaScript that determines how each robot behaves. Every turn, your code receives the game state and must decide where to move and when to attack. Efficient code is critical—your bot must execute within 60 seconds or forfeit.

**What's the goal?**
Destroy all enemy robots while protecting your own. Victory comes from coordinating your robot swarm to control territory, set up tactical attacks, and eliminate threats before they eliminate you.

**What makes it challenging?**
Success requires crafting logic that positions robots smartly, times attacks effectively, and adapts to opponent strategies. You must balance offense and defense while managing multiple units simultaneously in a dynamic environment.

---

<h2 id="cc-ladder">🪜 CC:Ladder</h2>

> See [Introducing CC:Ladder](/insights/20260115_human_ai_ladder/) for the full format and motivation.

The ladder is built from **58 open-source human robots**, collected from the public [leaderboard](https://robotrumble.org/boards/2/robots) and hosted as `human/*` branches on [CodeClash-ai/RobotRumble](https://github.com/CodeClash-ai/RobotRumble/branches). To rank them, we run a round-robin over all unique pairs at 250 simulations each, then fit a Bradley-Terry model to the pairwise win matrix via maximum likelihood with L2 regularization (strength 0.01, base Elo 1200, slope 400).

<div class="ladder-stats"><div class="ladder-stat"><span class="ladder-stat-num">58</span><span class="ladder-stat-label">human bots</span></div><div class="ladder-stat"><span class="ladder-stat-num">-1,737&#8211;3,219</span><span class="ladder-stat-label">Elo range</span></div><div class="ladder-stat"><span class="ladder-stat-num">1,547</span><span class="ladder-stat-label">median Elo</span></div><div class="ladder-stat"><span class="ladder-stat-num">4,956</span><span class="ladder-stat-label">spread</span></div></div>

RobotRumble has by far the widest spread &mdash; nearly **5,000 Elo** end to end &mdash; and one dominant outlier: `gigachad` sits **592 Elo** clear of every other robot. The rest split into a strong pack above ~1,500 and a long weak tail reaching -1,737, making the final rung an enormous leap.

<figure class="ladder-figure">
<svg viewBox="0 0 680 250" role="img" aria-label="Histogram of robots Elo ratings" preserveAspectRatio="xMidYMid meet">
<line class="grid" x1="46" y1="210.0" x2="664" y2="210.0"/>
<text class="tick" x="38" y="214.0" text-anchor="end">0</text>
<line class="grid" x1="46" y1="162.0" x2="664" y2="162.0"/>
<text class="tick" x="38" y="166.0" text-anchor="end">5</text>
<line class="grid" x1="46" y1="114.0" x2="664" y2="114.0"/>
<text class="tick" x="38" y="118.0" text-anchor="end">10</text>
<line class="grid" x1="46" y1="66.0" x2="664" y2="66.0"/>
<text class="tick" x="38" y="70.0" text-anchor="end">15</text>
<line class="grid" x1="46" y1="18.0" x2="664" y2="18.0"/>
<text class="tick" x="38" y="22.0" text-anchor="end">20</text>
<path class="bar" d="M47.5,210.0 L47.5,194.8 Q47.5,190.8 51.5,190.8 L74.8,190.8 Q78.8,190.8 78.8,194.8 L78.8,210.0 Z"><title>-1,737 to -1,461 Elo: 2 bots</title></path>
<path class="bar" d="M116.2,210.0 L116.2,204.4 Q116.2,200.4 120.2,200.4 L143.5,200.4 Q147.5,200.4 147.5,204.4 L147.5,210.0 Z"><title>-1,186 to -911 Elo: 1 bot</title></path>
<path class="bar" d="M184.8,210.0 L184.8,185.2 Q184.8,181.2 188.8,181.2 L212.2,181.2 Q216.2,181.2 216.2,185.2 L216.2,210.0 Z"><title>-635 to -360 Elo: 3 bots</title></path>
<path class="bar" d="M253.5,210.0 L253.5,185.2 Q253.5,181.2 257.5,181.2 L280.8,181.2 Q284.8,181.2 284.8,185.2 L284.8,210.0 Z"><title>-85 to 191 Elo: 3 bots</title></path>
<path class="bar" d="M287.8,210.0 L287.8,166.0 Q287.8,162.0 291.8,162.0 L315.2,162.0 Q319.2,162.0 319.2,166.0 L319.2,210.0 Z"><title>191 to 466 Elo: 5 bots</title></path>
<path class="bar" d="M322.2,210.0 L322.2,204.4 Q322.2,200.4 326.2,200.4 L349.5,200.4 Q353.5,200.4 353.5,204.4 L353.5,210.0 Z"><title>466 to 741 Elo: 1 bot</title></path>
<path class="bar" d="M356.5,210.0 L356.5,185.2 Q356.5,181.2 360.5,181.2 L383.8,181.2 Q387.8,181.2 387.8,185.2 L387.8,210.0 Z"><title>741 to 1,016 Elo: 3 bots</title></path>
<path class="bar" d="M390.8,210.0 L390.8,175.6 Q390.8,171.6 394.8,171.6 L418.2,171.6 Q422.2,171.6 422.2,175.6 L422.2,210.0 Z"><title>1,016 to 1,292 Elo: 4 bots</title></path>
<path class="bar" d="M425.2,210.0 L425.2,137.2 Q425.2,133.2 429.2,133.2 L452.5,133.2 Q456.5,133.2 456.5,137.2 L456.5,210.0 Z"><title>1,292 to 1,567 Elo: 8 bots</title></path>
<path class="bar" d="M459.5,210.0 L459.5,60.4 Q459.5,56.4 463.5,56.4 L486.8,56.4 Q490.8,56.4 490.8,60.4 L490.8,210.0 Z"><title>1,567 to 1,842 Elo: 16 bots</title></path>
<path class="bar" d="M493.8,210.0 L493.8,156.4 Q493.8,152.4 497.8,152.4 L521.2,152.4 Q525.2,152.4 525.2,156.4 L525.2,210.0 Z"><title>1,842 to 2,118 Elo: 6 bots</title></path>
<path class="bar" d="M528.2,210.0 L528.2,194.8 Q528.2,190.8 532.2,190.8 L555.5,190.8 Q559.5,190.8 559.5,194.8 L559.5,210.0 Z"><title>2,118 to 2,393 Elo: 2 bots</title></path>
<path class="bar" d="M562.5,210.0 L562.5,185.2 Q562.5,181.2 566.5,181.2 L589.8,181.2 Q593.8,181.2 593.8,185.2 L593.8,210.0 Z"><title>2,393 to 2,668 Elo: 3 bots</title></path>
<path class="bar" d="M631.2,210.0 L631.2,204.4 Q631.2,200.4 635.2,200.4 L658.5,200.4 Q662.5,200.4 662.5,204.4 L662.5,210.0 Z"><title>2,944 to 3,219 Elo: 1 bot</title></path>
<line class="axis" x1="46" y1="210" x2="664" y2="210" stroke-width="1.5"/>
<text class="tick" x="46.0" y="228.0" text-anchor="middle">-1,737</text>
<text class="tick" x="183.3" y="228.0" text-anchor="middle">-635</text>
<text class="tick" x="355.0" y="228.0" text-anchor="middle">741</text>
<text class="tick" x="526.7" y="228.0" text-anchor="middle">2,118</text>
<text class="tick" x="664.0" y="228.0" text-anchor="middle">3,219</text>
<line class="median" x1="455.5" y1="18" x2="455.5" y2="210"/>
<text class="median-label" x="461.5" y="28.0" text-anchor="start">median 1,547</text>
<text class="tick" x="355.0" y="246" text-anchor="middle">Elo rating &#8594;</text>
</svg>
<figcaption>Distribution of Elo across the 58 human RobotRumble robots. Note the lone outlier far to the right (gigachad) and the wide tails on both ends.</figcaption>
</figure>

The top ten:

1. human/entropicdrifter/gigachad: **3219.0**
2. human/entropicdrifter/seven-of-nine: **2627.3**
3. human/entropicdrifter/we-are-borg: **2560.0**
4. human/entropicdrifter/glommerv2: **2456.8**
5. human/mousetail/coward-bot: **2326.5**
6. human/entropicdrifter/glommer: **2250.2**
7. human/mitch84/crw_preempt: **2109.9**
8. human/mitch84/retreat_walk2: **2040.6**
9. human/devchris/black_magic: **2001.7**
10. human/tabaxi3k/black-magic-1: **1994.3**

<details>
<summary>Show full RobotRumble rankings</summary>

<ol>
<li>human/entropicdrifter/gigachad: <b>3219.0</b></li>
<li>human/entropicdrifter/seven-of-nine: <b>2627.3</b></li>
<li>human/entropicdrifter/we-are-borg: <b>2560.0</b></li>
<li>human/entropicdrifter/glommerv2: <b>2456.8</b></li>
<li>human/mousetail/coward-bot: <b>2326.5</b></li>
<li>human/entropicdrifter/glommer: <b>2250.2</b></li>
<li>human/mitch84/crw_preempt: <b>2109.9</b></li>
<li>human/mitch84/retreat_walk2: <b>2040.6</b></li>
<li>human/devchris/black_magic: <b>2001.7</b></li>
<li>human/tabaxi3k/black-magic-1: <b>1994.3</b></li>
<li>human/mitch84/walk_retreat: <b>1968.8</b></li>
<li>human/jammyliu/sixty-nine-line: <b>1889.7</b></li>
<li>human/atl15/centerrr: <b>1838.2</b></li>
<li>human/clay/diag-lattice: <b>1719.0</b></li>
<li>human/gerenuk/gere-ape: <b>1712.4</b></li>
<li>human/wolfsleuth/simple: <b>1656.1</b></li>
<li>human/essickmango/pickle-up: <b>1655.9</b></li>
<li>human/mkap/test: <b>1638.9</b></li>
<li>human/ketza/arthur: <b>1624.4</b></li>
<li>human/mountain/neuralbot4-3h: <b>1622.5</b></li>
<li>human/aaoutkine/silo34: <b>1618.6</b></li>
<li>human/anton/om-om: <b>1594.2</b></li>
<li>human/mee42/follow-bot: <b>1594.1</b></li>
<li>human/lanity/sivuy: <b>1593.7</b></li>
<li>human/underscore/bot1: <b>1589.8</b></li>
<li>human/mario31313/alpha_13: <b>1588.9</b></li>
<li>human/thesmilingturtl/naivefaa: <b>1587.8</b></li>
<li>human/aaoutkine/school-bot: <b>1570.6</b></li>
<li>human/suddenlyseals/control-center: <b>1551.4</b></li>
<li>human/ketza/bob: <b>1543.2</b></li>
<li>human/mjburgess/rule99: <b>1499.7</b></li>
<li>human/kalkin/maxad: <b>1498.1</b></li>
<li>human/mousetail/genetic-robot: <b>1493.7</b></li>
<li>human/edward/flail: <b>1477.2</b></li>
<li>human/aayyad/testbot: <b>1427.0</b></li>
<li>human/anton/anton4000: <b>1397.8</b></li>
<li>human/luisa/baselinegere: <b>1226.0</b></li>
<li>human/luisa/luisasrobot: <b>1223.1</b></li>
<li>human/jay0jayjay/naivestarter: <b>1168.3</b></li>
<li>human/aaa/jippty5: <b>1032.3</b></li>
<li>human/devchris/first_test: <b>940.9</b></li>
<li>human/tabaxi3k/charles: <b>936.3</b></li>
<li>human/essickmango/fruity-test: <b>935.9</b></li>
<li>human/sbasu3/meek-bot: <b>499.4</b></li>
<li>human/jiricodes/jiricodes-bot: <b>400.0</b></li>
<li>human/navster8/maginot-line: <b>397.3</b></li>
<li>human/kalkin/artemis2: <b>390.0</b></li>
<li>human/kalkin/artemis: <b>340.7</b></li>
<li>human/mountain/neuralbot2-6h: <b>331.4</b></li>
<li>human/sivecano/clouded-mind: <b>75.9</b></li>
<li>human/mountain/neuralbot1-1h: <b>23.5</b></li>
<li>human/aaoutkine/dark-knight: <b>-55.6</b></li>
<li>human/navster8/bash-brothers: <b>-496.0</b></li>
<li>human/ldang/nemo: <b>-496.7</b></li>
<li>human/ldang/nessy: <b>-538.5</b></li>
<li>human/anton/wallifier: <b>-911.3</b></li>
<li>human/happysquid/test: <b>-1624.4</b></li>
<li>human/anton/anton3000: <b>-1736.7</b></li>
</ol>

</details>

**Run it yourself.** [Set up CodeClash](https://docs.codeclash.ai/quickstart/#installation) and send a model up the ladder with:

<pre class="prettyprint lang-bash">
uv run codeclash ladder run configs/ablations/ladder/robotrumble.yaml
</pre>

---

### References

* [RobotRumble GitHub Organization](https://github.com/robot-rumble)
* [RobotRumble Website](https://robotrumble.org/)
* [CodeClash GitHub Repository](https://github.com/CodeClash-ai/RobotRumble)

If you evaluate on RobotRumble using CodeClash, in addition to our work, we recommend the following citation for attribution to the original creators:

<pre>
@misc{robotrumble2020,
    title={Robot Rumble},
    author={Outkine, Anton and Oxer, Noa},
    url={https://robotrumble.org/},
    year={2020},
}
</pre>