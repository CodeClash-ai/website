title: Humans & AI [Ep. 2] - Introducing CC:Ladder
date: 2026-01-15
description: Where does AI rank among public solutions by human programmers?
authors: John Yang

We pit [Claude 4.5 Sonnet against <img src="/static/images/insights/20251108_human_ai/gigachad.jpg" class="img-inline" style="height:1.2rem;margin-right:0em;" /> GigaChad](/insights/20251105_human_ai/) in [RobotRumble](/arenas/robotrumble) and found that today's best coding models still struggle heavily to develop suboptimal codebases into ones that rival the best human written solutions.

Inspired by this finding, we introduce **CC:Ladder**, a twist that makes evaluating LMs as competitive, long-horizon software developers **hill-climable** and **cheaper**.

**tl;dr** 

## How it works

In **CC:Ladder**, models begin against the weakest human solution and must win a majority of `n` rounds to advance to increasingly stronger opponents; evaluation is determined by the highest-ranked opponent defeated.

<img src="/static/images/insights/20260116_human_ai_ladder/cc_ladder.png" class="img-insight" />

Some key details:

- Models start with a codebase containing the weakest opponent's solution.
- Models play `n` rounds against an opponent, where **`n >= 3`**and **`n` is odd**.
- A model "advances" to the next opponent if it **wins `(n+1)/2` rounds** *and* it **wins the last round**.
- If a model advances, **its codebase carries over**. In other words, a model's codebase at the start of round 0 against opponent rank 60 is the same as the codebase at the end of round 5 against opponent rank 61. The model's codebase does *not* get reset to the initial state.

**CC:Ladder** has several advantages over the default Elo leaderboard.

- **Hill-climable**: See how far up the rankings a model can go. Better models achieve higher rankings.
- **Cheaper**: The model competes against static human solutions. No need to spend $$ to run another LM as an opponent.
- **Less noise**: Again, because the opponent is a static human solution.
- **Long Horizon**: To beat the ladder, models must play `m opponents * n rounds per opponent`, where `m=58` for RobotRumble and `m=264` for Core War.

## Building CC:Ladder

Putting together a ladder for a CodeClash arena is entirely dependent on how many open source, human written solutions are available on the web.

- For RobotRumble, we found 58 open source implementations on the [public leaderboard](https://robotrumble.org/boards/2/robots)
- For Core War, we found 264 open source implementations by manually crawling the Core War online [directory](http://www.koth.org/planar/by-name/complete.htm).

Given a solution, we (1) check that the solution compiles and runs properly, then (2) push the solution as a branch (named `human/<name>` or `human/<author>/<name>`) to the corresponding repository (branches for [Core War](https://github.com/CodeClash-ai/CoreWar/branches), [RobotRumble](https://github.com/CodeClash-ai/RobotRumble/branches)).

We currently execute this workflow manually.
Ping us in [Slack](https://join.slack.com/t/swe-bench/shared_invite/zt-36pj9bu5s-o3_yXPZbaH2wVnxnss1EkQ) if you'd be interested in automating this process!

## Initial Findings

### Part 1: Ranking human-written solutions

Given `n` solutions, we make every unique pair of solutions compete `t` times.

- `t=250` for RobotRumble
- `t=4000` for Core War

`t` varies solely due to compute constraints.
Core War simulations run more quickly than RobotRumble simulations.

Then, we compute each solution's Elo and determine the rankings.

For **Core War**, the top ten:



<details>
<summary>Show full Core War rankings</summary>

</details>

For **RobotRumble**, the top ten:

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

### Part 2: How high do current models climb?

On Core War

* <img src="/static/images/orgs/anthropic.svg" class="img-inline" style="height:1rem;margin-right:0em;"/> Claude Sonnet 4.5 reaches
* <img src="/static/images/orgs/openai.svg" class="img-inline" style="height:1rem;margin-right:0em;"/> GPT 5 (medium thinking) reaches
* <img src="/static/images/orgs/google.svg" class="img-inline" style="height:1rem;margin-right:0em;"/> Gemini 2.5 Pro reaches

On RobotRumble

* <img src="/static/images/orgs/openai.svg" class="img-inline" style="height:1rem;margin-right:0em;"/> GPT 5 (medium thinking) reaches
* <img src="/static/images/orgs/anthropic.svg" class="img-inline" style="height:1rem;margin-right:0em;"/> Claude Sonnet 4.5 reaches
* <img src="/static/images/orgs/google.svg" class="img-inline" style="height:1rem;margin-right:0em;"/> Gemini 2.5 Pro reaches

## How to run?

Run your model against **CC:Ladder** today.
[Set up CodeClash](https://docs.codeclash.ai/quickstart/#installation) and run `uv run python ladder.py configs/ladder/<arena>.yaml`, where `<arena>.yaml` specifies (using Core War as the example arena):

<pre class="prettyprint lang-yaml">
tournament:
  rounds: 5 # Number of rounds model players each opponent
game:
  name: CoreWar
  sims_per_round: 1000
  args: {}
player:
  agent: mini
  name: claude-sonnet-4-5-20250929
  config:
    agent: !include mini/default.yaml
    model:
      model_name: '@anthropic/claude-sonnet-4-5-20250929'
      model_kwargs:
        temperature: 0.2
        max_tokens: 4096
</pre>

## Relationship between CC:Ladder & CodeClash

We encourage practitioners to...

- Use **CC:Ladder** for development.
- Once your model / scaffold / AI system is finalized, run evaluation against other models on CodeClash proper.

For Pokémon fans, **CC:Ladder** is the equivalent of the [Elite 4](https://pokemon.fandom.com/wiki/Elite_Four) battles.
CodeClash is the real world [Video Game Championships](https://en.wikipedia.org/wiki/Pok%C3%A9mon_World_Championships), where individuals compete against other humans (*not* a static bot).

<img src="/static/images/insights/20260116_human_ai_ladder/elite4firered.png" class="img-insight" />
<div style="text-align:center;font-size:0.9em;">
As with the Elite Four, <b>CC:Ladder</b> tests progression against fixed opponents, whereas CodeClash reflects real competition by measuring performance against intelligent competitors.
</div>

CodeClash remains the north-star evaluation.
Competition against dynamic, intelligent competition is more challenging than static solutions.
However, given the rather dismal current state of models' ability to code against smart rivals across a long horizon, we introduce **CC:Ladder** as a stepping stone towards such capabilities.