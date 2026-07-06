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

RobotRumble has a **CC:Ladder** — a ranked ladder of open-source human robots that turns the arena into a hill-climbable evaluation. A model starts against the weakest human robot and must win a majority of `n` rounds (and the final round) to advance to a stronger opponent; its score is the highest-ranked human it defeats. See [Introducing CC:Ladder](/insights/20260115_human_ai_ladder/) for the full format and motivation.

The ladder is built from **58 open-source human robots**, collected from the public [leaderboard](https://robotrumble.org/boards/2/robots) and hosted as `human/*` branches on [CodeClash-ai/RobotRumble](https://github.com/CodeClash-ai/RobotRumble/branches). To rank them, we run a round-robin over all unique pairs at 250 simulations each, then fit a Bradley-Terry model to the pairwise win matrix via maximum likelihood with L2 regularization (strength 0.01, base Elo 1200, slope 400).

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