title: Humans & AI [Ep. 2] - Introducing CC:Ladder
date: 2026-01-15
description: Where does AI rank among public solutions by human programmers?
authors: John Yang

**tl;dr** We introduce boss battles as a new format for evaluating LMs' coding + reasoning capabilities.

We pit [Claude 4.5 Sonnet against <img src="/static/images/insights/20251108_human_ai/gigachad.jpg" class="img-inline" style="height:1.2rem;margin-right:0em;" /> GigaChad](/insights/20251105_human_ai/) in [RobotRumble](/arenas/robotrumble) and found that today's best coding models still struggle heavily to develop suboptimal codebases into ones that rival the best human written solutions.

Inspired by this finding, we introduce **CC:Ladder**, a twist that makes evaluating LMs as competitive, long-horizon software developers **hill-climable** and **cheaper**.

## How it works

In **CC:Ladder**, models begin against the weakest human solution and must win a majority of `n` rounds to advance to increasingly stronger opponents; evaluation is determined by the highest-ranked opponent defeated.

<img src="/static/images/insights/20260116_human_ai_ladder/cc_ladder.png" class="img-insight" />

Some key details:

- Models start with a codebase containing the weakest opponent's solution.
- Models play `n` rounds against an opponent, where **`n >= 3`** and **`n` is odd**.
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
- For BattleSnake, we found 50 open source implementations with reliable game servers.

Given a solution, we (1) check that the solution compiles and runs properly, then (2) push the solution as a branch (named `human/<name>` or `human/<author>/<name>`) to the corresponding repository (branches for [Core War](https://github.com/CodeClash-ai/CoreWar/branches), [RobotRumble](https://github.com/CodeClash-ai/RobotRumble/branches), [BattleSnake](https://github.com/CodeClash-ai/BattleSnake/branches)).

We currently execute this workflow manually.
Ping us in [Slack](https://join.slack.com/t/swe-bench/shared_invite/zt-36pj9bu5s-o3_yXPZbaH2wVnxnss1EkQ) if you'd be interested in automating this process or putting together a new ladder for a different arena!

## Initial Findings

### Part 1: Ranking human-written solutions

Given `n` solutions, we make every unique pair of solutions compete `t` times.

- `t=250` for RobotRumble
- `t=4000` for Core War

`t` varies solely due to compute constraints.
Core War simulations run more quickly than RobotRumble simulations.

Then, we compute each solution's Elo and determine the rankings.
Elo ratings are computed by fitting a Bradley-Terry model to the pairwise win matrix via maximum likelihood estimation with L2 regularization.
We set the regularization strength to 0.01 and use a base Elo of 1200 with a slope of 400 to convert log-odds strengths to interpretable ratings.

We host the ranked human solutions — along with the full Elo tables — on each arena's own page. Head there for the complete rankings:

- **[Core War](/arenas/corewar#cc-ladder)** — 264 human warriors (`t=4000`)
- **[RobotRumble](/arenas/robotrumble#cc-ladder)** — 58 human robots (`t=250`)
- **[BattleSnake](/arenas/battlesnake#cc-ladder)** — 50 human snakes (`t=250`)

### Part 2: How high do current models climb?

On Core War

* <img src="/static/images/orgs/anthropic.svg" class="img-inline" style="height:1rem;margin-right:0em;"/> Claude Opus 4.5 reaches *[coming soon]*
* <img src="/static/images/orgs/openai.svg" class="img-inline" style="height:1rem;margin-right:0em;"/> GPT 5.2 (medium thinking) reaches *[coming soon]*
* <img src="/static/images/orgs/google.svg" class="img-inline" style="height:1rem;margin-right:0em;"/> Gemini 3 Pro reaches *[coming soon]*

On RobotRumble

* <img src="/static/images/orgs/anthropic.svg" class="img-inline" style="height:1rem;margin-right:0em;"/> Claude Opus 4.5 reaches *[coming soon]*
* <img src="/static/images/orgs/openai.svg" class="img-inline" style="height:1rem;margin-right:0em;"/> GPT 5.2 (medium thinking) reaches *[coming soon]*
* <img src="/static/images/orgs/google.svg" class="img-inline" style="height:1rem;margin-right:0em;"/> Gemini 3 Pro reaches *[coming soon]*

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

For Pokémon fans, **CC:Ladder** is the equivalent of the [Elite 4](https://pokemon.fandom.com/wiki/Elite_Four) battles (and for the real aficionados, **CC:Ladder** is inspired heavily by the [Trainer Tower](https://bulbapedia.bulbagarden.net/wiki/Trainer_Tower)).
CodeClash is the real world [Video Game Championships](https://en.wikipedia.org/wiki/Pok%C3%A9mon_World_Championships), where individuals compete against other humans (*not* a static bot).

<img src="/static/images/insights/20260116_human_ai_ladder/elite4firered.png" class="img-insight" />
<div style="text-align:center;font-size:0.9em;">
As with the Elite Four, <b>CC:Ladder</b> tests progression against fixed opponents, whereas CodeClash reflects real competition by measuring performance against intelligent competitors.
</div>

We recommend CC:Ladder be treated as a proper evaluation as well.
Similar to how SWE-bench Lite and Verified were created as easier subsets of SWE-bench, we think 

CodeClash remains the north-star evaluation.
Competition against dynamic, intelligent competition is more challenging than static solutions.
However, given the rather dismal current state of models' ability to code against smart rivals across a long horizon, we introduce **CC:Ladder** as a stepping stone towards such capabilities.