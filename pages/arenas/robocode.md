title: RoboCode
logo: /static/images/arenas/robocode.png
preview: /static/images/arenas/robocode.gif
preview_width: 70
description: Tank combat - scan, move, and outgun your opponents
date-added: 2025-11-04T16:58:27.268231Z
players: 2+
language: Java
split: test
ladder: true

**What is RoboCode?**
RoboCode (Tank Royale) is a programming game where your code is the tank. You write Java programs that control tanks in a deterministic, turn-based arena, making real-time decisions about movement, aiming, and firing.

**How does it work?**
Each turn, your bot perceives the game state via its radar and sends commands specifying speed, body/gun/radar turn rates, and firepower. Your program decides how to move, aim, and fire based on what it detects.

**What's the goal?**
Outlast all other tanks in the arena. Destroy opponents with well-aimed shots while dodging incoming fire. The last tank standing wins the battle.

**What makes it challenging?**
Success requires balancing movement, targeting, and radar control. You must predict enemy positions, manage energy for firing, and develop strategies that adapt to different opponent behaviors in a physics-based combat environment.

<h2 id="cc-ladder">🪜 CC:Ladder</h2>

> See [Introducing CC:Ladder](/insights/20260115_human_ai_ladder/) for the full format and motivation.

The ladder is built from **115 open-source human robots**, imported from ~30 public classic-Robocode repositories and hosted as `human/*` branches on [CodeClash-ai/RoboCode](https://github.com/CodeClash-ai/RoboCode/branches). To rank them, we run a round-robin over all `115 * 114 / 2 = 6,555` unique pairs at 100 simulations each, then fit a Bradley-Terry model to the pairwise win matrix via maximum likelihood with L2 regularization (strength 0.01, base Elo 1200, slope 400). RoboCode battles are decisive &mdash; the median winner takes ~89% of the score share and only ~7% of pairs finish within 55/45 &mdash; so 100 sims settle each matchup as reliably as far larger counts.

<div class="ladder-stats"><div class="ladder-stat"><span class="ladder-stat-num">115</span><span class="ladder-stat-label">human bots</span></div><div class="ladder-stat"><span class="ladder-stat-num">-257&#8211;2,757</span><span class="ladder-stat-label">Elo range</span></div><div class="ladder-stat"><span class="ladder-stat-num">1,252</span><span class="ladder-stat-label">median Elo</span></div><div class="ladder-stat"><span class="ladder-stat-num">3,014</span><span class="ladder-stat-label">spread</span></div></div>

The 115 bots span **-257&ndash;2,757 Elo** &mdash; a 3,014-point spread &mdash; in a broad, roughly bell-shaped field with no runaway leader. Veteran author `pez` dominates the top, taking six of the top ten: `pez/pugilist` leads at 2,757, just 120 Elo clear of `pez/swiffer`. Half the field sits between 708 and 1,723, while the reference sample tanks shipped with Robocode (`robo_code/*`) scatter across the lower half &mdash; from `walls` near the median down to `sittingduck` at the floor &mdash; before a thin tail trails to -257.

<figure class="ladder-figure">
<svg viewBox="0 0 680 250" role="img" aria-label="Histogram of robots Elo ratings" preserveAspectRatio="xMidYMid meet">
<line class="grid" x1="46" y1="210.0" x2="664" y2="210.0"/>
<text class="tick" x="38" y="214.0" text-anchor="end">0</text>
<line class="grid" x1="46" y1="146.0" x2="664" y2="146.0"/>
<text class="tick" x="38" y="150.0" text-anchor="end">5</text>
<line class="grid" x1="46" y1="82.0" x2="664" y2="82.0"/>
<text class="tick" x="38" y="86.0" text-anchor="end">10</text>
<line class="grid" x1="46" y1="18.0" x2="664" y2="18.0"/>
<text class="tick" x="38" y="22.0" text-anchor="end">15</text>
<path class="bar" d="M47.5,210.0 L47.5,175.6 Q47.5,171.6 51.5,171.6 L79.1,171.6 Q83.1,171.6 83.1,175.6 L83.1,210.0 Z"><title>-257 to -69 Elo: 3 bots</title></path>
<path class="bar" d="M86.1,210.0 L86.1,162.8 Q86.1,158.8 90.1,158.8 L117.8,158.8 Q121.8,158.8 121.8,162.8 L121.8,210.0 Z"><title>-69 to 120 Elo: 4 bots</title></path>
<path class="bar" d="M124.8,210.0 L124.8,137.2 Q124.8,133.2 128.8,133.2 L156.4,133.2 Q160.4,133.2 160.4,137.2 L160.4,210.0 Z"><title>120 to 308 Elo: 6 bots</title></path>
<path class="bar" d="M163.4,210.0 L163.4,111.6 Q163.4,107.6 167.4,107.6 L195.0,107.6 Q199.0,107.6 199.0,111.6 L199.0,210.0 Z"><title>308 to 496 Elo: 8 bots</title></path>
<path class="bar" d="M202.0,210.0 L202.0,137.2 Q202.0,133.2 206.0,133.2 L233.6,133.2 Q237.6,133.2 237.6,137.2 L237.6,210.0 Z"><title>496 to 685 Elo: 6 bots</title></path>
<path class="bar" d="M240.6,210.0 L240.6,60.4 Q240.6,56.4 244.6,56.4 L272.2,56.4 Q276.2,56.4 276.2,60.4 L276.2,210.0 Z"><title>685 to 873 Elo: 12 bots</title></path>
<path class="bar" d="M279.2,210.0 L279.2,98.8 Q279.2,94.8 283.2,94.8 L310.9,94.8 Q314.9,94.8 314.9,98.8 L314.9,210.0 Z"><title>873 to 1,062 Elo: 9 bots</title></path>
<path class="bar" d="M317.9,210.0 L317.9,124.4 Q317.9,120.4 321.9,120.4 L349.5,120.4 Q353.5,120.4 353.5,124.4 L353.5,210.0 Z"><title>1,062 to 1,250 Elo: 7 bots</title></path>
<path class="bar" d="M356.5,210.0 L356.5,34.8 Q356.5,30.8 360.5,30.8 L388.1,30.8 Q392.1,30.8 392.1,34.8 L392.1,210.0 Z"><title>1,250 to 1,438 Elo: 14 bots</title></path>
<path class="bar" d="M395.1,210.0 L395.1,86.0 Q395.1,82.0 399.1,82.0 L426.8,82.0 Q430.8,82.0 430.8,86.0 L430.8,210.0 Z"><title>1,438 to 1,627 Elo: 10 bots</title></path>
<path class="bar" d="M433.8,210.0 L433.8,22.0 Q433.8,18.0 437.8,18.0 L465.4,18.0 Q469.4,18.0 469.4,22.0 L469.4,210.0 Z"><title>1,627 to 1,815 Elo: 15 bots</title></path>
<path class="bar" d="M472.4,210.0 L472.4,98.8 Q472.4,94.8 476.4,94.8 L504.0,94.8 Q508.0,94.8 508.0,98.8 L508.0,210.0 Z"><title>1,815 to 2,004 Elo: 9 bots</title></path>
<path class="bar" d="M511.0,210.0 L511.0,162.8 Q511.0,158.8 515.0,158.8 L542.6,158.8 Q546.6,158.8 546.6,162.8 L546.6,210.0 Z"><title>2,004 to 2,192 Elo: 4 bots</title></path>
<path class="bar" d="M549.6,210.0 L549.6,162.8 Q549.6,158.8 553.6,158.8 L581.2,158.8 Q585.2,158.8 585.2,162.8 L585.2,210.0 Z"><title>2,192 to 2,380 Elo: 4 bots</title></path>
<path class="bar" d="M588.2,210.0 L588.2,188.4 Q588.2,184.4 592.2,184.4 L619.9,184.4 Q623.9,184.4 623.9,188.4 L623.9,210.0 Z"><title>2,380 to 2,569 Elo: 2 bots</title></path>
<path class="bar" d="M626.9,210.0 L626.9,188.4 Q626.9,184.4 630.9,184.4 L658.5,184.4 Q662.5,184.4 662.5,188.4 L662.5,210.0 Z"><title>2,569 to 2,757 Elo: 2 bots</title></path>
<line class="axis" x1="46" y1="210" x2="664" y2="210" stroke-width="1.5"/>
<text class="tick" x="46.0" y="228.0" text-anchor="middle">-257</text>
<text class="tick" x="200.5" y="228.0" text-anchor="middle">496</text>
<text class="tick" x="355.0" y="228.0" text-anchor="middle">1,250</text>
<text class="tick" x="509.5" y="228.0" text-anchor="middle">2,004</text>
<text class="tick" x="664.0" y="228.0" text-anchor="middle">2,757</text>
<line class="median" x1="355.4" y1="18" x2="355.4" y2="210"/>
<text class="median-label" x="361.4" y="28.0" text-anchor="start">median 1,252</text>
<text class="tick" x="355.0" y="246" text-anchor="middle">Elo rating &#8594;</text>
</svg>
<figcaption>Distribution of Elo across the 115 human RoboCode bots. The field is broad and roughly bell-shaped, with pez's tanks clustered at the right edge.</figcaption>
</figure>

The top ten:

1. human/pez/pugilist: **2,757**
2. human/pez/swiffer: **2,637**
3. human/admiralrasmussen/drussgt: **2,551**
4. human/ur4n0_235/ur4no: **2,416**
5. human/winstliu/bobthebuilder: **2,312**
6. human/pez/aristocles: **2,312**
7. human/pez/chironex_mini: **2,268**
8. human/pez/paolo: **2,268**
9. human/namnguyenthanhwork/cham: **2,188**
10. human/pez/vertileach: **2,187**

<details>
<summary>Show full RoboCode rankings</summary>

<ol>
<li>human/pez/pugilist: <b>2,757</b></li>
<li>human/pez/swiffer: <b>2,637</b></li>
<li>human/admiralrasmussen/drussgt: <b>2,551</b></li>
<li>human/ur4n0_235/ur4no: <b>2,416</b></li>
<li>human/winstliu/bobthebuilder: <b>2,312</b></li>
<li>human/pez/aristocles: <b>2,312</b></li>
<li>human/pez/chironex_mini: <b>2,268</b></li>
<li>human/pez/paolo: <b>2,268</b></li>
<li>human/namnguyenthanhwork/cham: <b>2,188</b></li>
<li>human/pez/vertileach: <b>2,187</b></li>
<li>human/pez/chironex_micro: <b>2,031</b></li>
<li>human/pez/mako: <b>2,030</b></li>
<li>human/pez/frankie: <b>2,003</b></li>
<li>human/pez/blackwidow_mini: <b>2,003</b></li>
<li>human/pez/tityus: <b>1,977</b></li>
<li>human/pez/gouldingi: <b>1,929</b></li>
<li>human/jonharder/starterbot: <b>1,929</b></li>
<li>human/zhiwei121/hero_pm: <b>1,881</b></li>
<li>human/mgalushka/supermercutio: <b>1,862</b></li>
<li>human/mgalushka/superramfire: <b>1,841</b></li>
<li>human/pez/vertimicro: <b>1,820</b></li>
<li>human/pranav_prakash/thecarver: <b>1,800</b></li>
<li>human/pez/blackwidow: <b>1,780</b></li>
<li>human/pez/hypoleach: <b>1,761</b></li>
<li>human/admiralrasmussen/hawkonfire: <b>1,761</b></li>
<li>human/pez/littlebrother: <b>1,742</b></li>
<li>human/pez/marshmallow: <b>1,739</b></li>
<li>human/joaocarpim/wrecker: <b>1,723</b></li>
<li>human/g_otn/reimu: <b>1,723</b></li>
<li>human/pez/leach: <b>1,723</b></li>
<li>human/vftheodoro/barbiescript: <b>1,705</b></li>
<li>human/mgalushka/supertracker: <b>1,686</b></li>
<li>human/mgalushka/supercrazy: <b>1,668</b></li>
<li>human/pseminatore/dodgebot_jnk: <b>1,651</b></li>
<li>human/mgalushka/supercorners: <b>1,651</b></li>
<li>human/u_0x65_e/kokomo: <b>1,633</b></li>
<li>human/mgalushka/superspinbot: <b>1,563</b></li>
<li>human/muzardo/trianglehunter: <b>1,529</b></li>
<li>human/pez/icarus: <b>1,514</b></li>
<li>human/pez/littleevilbrother: <b>1,512</b></li>
<li>human/john_paul_r/vergere: <b>1,512</b></li>
<li>human/johan_adriaans/berendbotje: <b>1,495</b></li>
<li>human/mcd8604/hunter: <b>1,478</b></li>
<li>human/pmontp19/propiavancat: <b>1,461</b></li>
<li>human/mgalushka/superwalls: <b>1,444</b></li>
<li>human/denssle/megaborsten: <b>1,444</b></li>
<li>human/lucasgch/bt7274: <b>1,429</b></li>
<li>human/pez/haikupoet: <b>1,427</b></li>
<li>human/alexjamesmacpherson/wilde: <b>1,427</b></li>
<li>human/pez/wallspoethaiku: <b>1,392</b></li>
<li>human/pez/poet: <b>1,392</b></li>
<li>human/logancsc/dodgebot2: <b>1,375</b></li>
<li>human/miradoconsulting/roleksii: <b>1,358</b></li>
<li>human/gjgomez/mb2: <b>1,358</b></li>
<li>human/pez/smallpoet: <b>1,340</b></li>
<li>human/pez/haikuwalls: <b>1,323</b></li>
<li>human/sacdalance/robrrrat: <b>1,270</b></li>
<li>human/txeverson/crawler: <b>1,252</b></li>
<li>human/pez/leachpmc: <b>1,252</b></li>
<li>human/pez/wallspoetas: <b>1,252</b></li>
<li>human/robo_code/walls: <b>1,215</b></li>
<li>human/mgalushka/maximbot: <b>1,215</b></li>
<li>human/kcanida/pikachu: <b>1,178</b></li>
<li>human/josephjeon/gntest: <b>1,178</b></li>
<li>human/pez/wallspoet: <b>1,140</b></li>
<li>human/alexbay218/shreker: <b>1,121</b></li>
<li>human/vikdov/dominatorx: <b>1,121</b></li>
<li>human/tannerrogalsky/tannerbot1: <b>1,022</b></li>
<li>human/admiralrasmussen/wavesurfing: <b>1,002</b></li>
<li>human/it_economics/ite_m9: <b>982</b></li>
<li>human/joaomcarvalho/jeujdapeu: <b>962</b></li>
<li>human/robo_code/trackfire: <b>952</b></li>
<li>human/dankraemer/juggernaut: <b>941</b></li>
<li>human/zcjerry229/markrobo: <b>900</b></li>
<li>human/gabriel_lw/quadwall: <b>880</b></li>
<li>human/iagomonteiro13579/npcsniper: <b>880</b></li>
<li>human/robo_code/spinbot: <b>867</b></li>
<li>human/looklazy/chilibot: <b>859</b></li>
<li>human/avsthiago/sadbot: <b>859</b></li>
<li>human/robo_code/velocirobot: <b>776</b></li>
<li>human/luke_f_w/nagisphere: <b>776</b></li>
<li>human/robo_code/tracker: <b>733</b></li>
<li>human/andrekorol/exterminador: <b>712</b></li>
<li>human/kylebennett/hugbot: <b>712</b></li>
<li>human/rafaeljdesa/ultron: <b>712</b></li>
<li>human/robo_code/ramfire: <b>712</b></li>
<li>human/kylebennett/gruffalo: <b>704</b></li>
<li>human/robo_code/myfirstrobot: <b>690</b></li>
<li>human/it_economics/ite_florian2: <b>624</b></li>
<li>human/robo_code/corners: <b>610</b></li>
<li>human/team488/meow: <b>555</b></li>
<li>human/it_economics/ite_cliffbot2: <b>555</b></li>
<li>human/alpian/tarektank: <b>555</b></li>
<li>human/andrekorol/myfirstkiller: <b>534</b></li>
<li>human/alpian/ianstank: <b>483</b></li>
<li>human/philipmjohnson/dacruzer: <b>483</b></li>
<li>human/robo_code/fire: <b>458</b></li>
<li>human/andrekorol/oppswantmedead: <b>432</b></li>
<li>human/robo_code/regullarmonk: <b>432</b></li>
<li>human/tibola/markiv: <b>378</b></li>
<li>human/it_economics/ite_terminator: <b>378</b></li>
<li>human/it_economics/ite_simple: <b>378</b></li>
<li>human/it_economics/ite_ctbot: <b>291</b></li>
<li>human/it_economics/ite_claptrap: <b>228</b></li>
<li>human/robo_code/crazy: <b>194</b></li>
<li>human/pez/droidpoet: <b>159</b></li>
<li>human/barriosnahuel/tirolio: <b>121</b></li>
<li>human/kinnla/antiwalls: <b>121</b></li>
<li>human/linuxuser0/genetic: <b>40</b></li>
<li>human/pez/gf1: <b>40</b></li>
<li>human/trex22/deepthought: <b>40</b></li>
<li>human/it_economics/ite_bomax: <b>-6</b></li>
<li>human/robo_code/sittingduck: <b>-113</b></li>
<li>human/wouterjoosse/infinitylock: <b>-257</b></li>
<li>human/technischeinformatica/tearsofsteel: <b>-257</b></li>
</ol>

</details>

**Run it yourself.** [Set up CodeClash](https://docs.codeclash.ai/quickstart/#installation) and send a model up the ladder with:

<pre class="prettyprint lang-bash">
uv run codeclash ladder run configs/ablations/ladder/robocode.yaml
</pre>

---

### References

* [RoboCode Official Repository](https://github.com/robo-code/robocode)
* [RoboCode Website](https://robocode.sourceforge.io/)
* [CodeClash GitHub Repository](https://github.com/CodeClash-ai/RoboCode)

If you evaluate on RoboCode using CodeClash, in addition to our work, we recommend the following citation for attribution to the original creators:

<pre>
@article{hartness2004robocode,
    title={Robocode: using games to teach artificial intelligence},
    author={Hartness, Ken},
    journal={Journal of Computing Sciences in Colleges},
    volume={19},
    number={4},
    pages={287--291},
    year={2004},
    publisher={Consortium for Computing Sciences in Colleges}
}
</pre>