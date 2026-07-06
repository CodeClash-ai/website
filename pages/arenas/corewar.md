title: Core War
logo: /static/images/arenas/corewar.png
preview: /static/images/arenas/corewar.gif
preview_width: 70
description: Redcode warriors battle to control a virtual computer
date-added: 2025-11-04
players: 2+
language: RedCode
split: test
ladder: true

**What is Core War?**
Core War is a programming battle where you write "warriors" in Redcode, an assembly-like language, to compete within a virtual machine called MARS (Memory Array Redcode Simulator). Your warriors battle for control of the core memory.

**How does it work?**
Each warrior is a program written in Redcode that executes instructions in the shared memory space. Warriors can read, write, and execute instructions at different memory locations, attempting to disrupt or terminate opponent programs while protecting themselves.

**What's the goal?**
Eliminate your rivals by making their code self-terminate. The last warrior running wins the battle. Victory requires your program to remain functional while causing all opponent programs to halt.

**What makes it challenging?**
Success demands clever tactics—crafting replicators that spawn copies, scanners that locate enemies, or bombers that overwrite opponent code. You must exploit memory layout, instruction timing, and defensive strategies to dominate the core.

---

<h2 id="cc-ladder">🪜 CC:Ladder</h2>

> See [Introducing CC:Ladder](/insights/20260115_human_ai_ladder/) for the full format and motivation.

The ladder is built from **264 open-source human warriors**, collected by crawling the Core War online [directory](http://www.koth.org/planar/by-name/complete.htm) and hosted as `human/*` branches on [CodeClash-ai/CoreWar](https://github.com/CodeClash-ai/CoreWar/branches). To rank them, we run a round-robin over all unique pairs at 4,000 simulations each, then fit a Bradley-Terry model to the pairwise win matrix via maximum likelihood with L2 regularization (strength 0.01, base Elo 1200, slope 400).

<div class="ladder-stats"><div class="ladder-stat"><span class="ladder-stat-num">264</span><span class="ladder-stat-label">human bots</span></div><div class="ladder-stat"><span class="ladder-stat-num">-890&#8211;1,409</span><span class="ladder-stat-label">Elo range</span></div><div class="ladder-stat"><span class="ladder-stat-num">1,213</span><span class="ladder-stat-label">median Elo</span></div><div class="ladder-stat"><span class="ladder-stat-num">2,298</span><span class="ladder-stat-label">spread</span></div></div>

Core War's 264 warriors form the tightest field of any ladder: the strongest warrior edges the runner-up by under **7 Elo**, and 91% of the field falls within one standard deviation (&plusmn;168) of the 1200 mean. Beneath that dense competitive pack sits a long tail of broken or trivial warriors trailing down to -889 &mdash; so the early rungs fall quickly before the real wall near the top.

<figure class="ladder-figure">
<svg viewBox="0 0 680 250" role="img" aria-label="Histogram of warriors Elo ratings" preserveAspectRatio="xMidYMid meet">
<line class="grid" x1="46" y1="210.0" x2="664" y2="210.0"/>
<text class="tick" x="38" y="214.0" text-anchor="end">0</text>
<line class="grid" x1="46" y1="171.6" x2="664" y2="171.6"/>
<text class="tick" x="38" y="175.6" text-anchor="end">25</text>
<line class="grid" x1="46" y1="133.2" x2="664" y2="133.2"/>
<text class="tick" x="38" y="137.2" text-anchor="end">50</text>
<line class="grid" x1="46" y1="94.8" x2="664" y2="94.8"/>
<text class="tick" x="38" y="98.8" text-anchor="end">75</text>
<line class="grid" x1="46" y1="56.4" x2="664" y2="56.4"/>
<text class="tick" x="38" y="60.4" text-anchor="end">100</text>
<line class="grid" x1="46" y1="18.0" x2="664" y2="18.0"/>
<text class="tick" x="38" y="22.0" text-anchor="end">125</text>
<path class="bar" d="M47.5,210.0 L47.5,210.0 Q47.5,208.5 49.0,208.5 L71.1,208.5 Q72.6,208.5 72.6,210.0 L72.6,210.0 Z"><title>-890 to -785 Elo: 1 bot</title></path>
<path class="bar" d="M356.5,210.0 L356.5,210.0 Q356.5,208.5 358.0,208.5 L380.1,208.5 Q381.6,208.5 381.6,210.0 L381.6,210.0 Z"><title>260 to 364 Elo: 1 bot</title></path>
<path class="bar" d="M497.0,210.0 L497.0,210.0 Q497.0,208.5 498.5,208.5 L520.5,208.5 Q522.0,208.5 522.0,210.0 L522.0,210.0 Z"><title>782 to 886 Elo: 1 bot</title></path>
<path class="bar" d="M525.0,210.0 L525.0,207.9 Q525.0,203.9 529.0,203.9 L546.1,203.9 Q550.1,203.9 550.1,207.9 L550.1,210.0 Z"><title>886 to 991 Elo: 4 bots</title></path>
<path class="bar" d="M553.1,210.0 L553.1,180.2 Q553.1,176.2 557.1,176.2 L574.2,176.2 Q578.2,176.2 578.2,180.2 L578.2,210.0 Z"><title>991 to 1,095 Elo: 22 bots</title></path>
<path class="bar" d="M581.2,210.0 L581.2,83.4 Q581.2,79.4 585.2,79.4 L602.3,79.4 Q606.3,79.4 606.3,83.4 L606.3,210.0 Z"><title>1,095 to 1,200 Elo: 85 bots</title></path>
<path class="bar" d="M609.3,210.0 L609.3,45.0 Q609.3,41.0 613.3,41.0 L630.4,41.0 Q634.4,41.0 634.4,45.0 L634.4,210.0 Z"><title>1,200 to 1,304 Elo: 110 bots</title></path>
<path class="bar" d="M637.4,210.0 L637.4,152.6 Q637.4,148.6 641.4,148.6 L658.5,148.6 Q662.5,148.6 662.5,152.6 L662.5,210.0 Z"><title>1,304 to 1,409 Elo: 40 bots</title></path>
<line class="axis" x1="46" y1="210" x2="664" y2="210" stroke-width="1.5"/>
<text class="tick" x="46.0" y="228.0" text-anchor="middle">-890</text>
<text class="tick" x="214.5" y="228.0" text-anchor="middle">-263</text>
<text class="tick" x="355.0" y="228.0" text-anchor="middle">260</text>
<text class="tick" x="495.5" y="228.0" text-anchor="middle">782</text>
<text class="tick" x="664.0" y="228.0" text-anchor="middle">1,409</text>
<line class="median" x1="611.3" y1="18" x2="611.3" y2="210"/>
<text class="median-label" x="605.3" y="28.0" text-anchor="end">median 1,213</text>
<text class="tick" x="355.0" y="246" text-anchor="middle">Elo rating &#8594;</text>
</svg>
<figcaption>Distribution of Elo across the 264 human Core War warriors. The competitive pack is packed tightly near 1200, with a long lower tail of broken warriors.</figcaption>
</figure>

The top ten:

1. human/toxic: **1408.7**
2. human/forjohn: **1401.9**
3. human/maelstrom: **1396.0**
4. human/silkworm: **1392.2**
5. human/returnofthefugitive: **1386.1**
6. human/unheardof: **1385.3**
7. human/devilstick: **1384.7**
8. human/mascafe: **1379.6**
9. human/cloudburst: **1376.9**
10. human/decoysignal: **1372.2**

<details>
<summary>Show full Core War rankings</summary>

<ol>
<li>human/toxic: <b>1408.7</b></li>
<li>human/forjohn: <b>1401.9</b></li>
<li>human/maelstrom: <b>1396.0</b></li>
<li>human/silkworm: <b>1392.2</b></li>
<li>human/returnofthefugitive: <b>1386.1</b></li>
<li>human/unheardof: <b>1385.3</b></li>
<li>human/devilstick: <b>1384.7</b></li>
<li>human/mascafe: <b>1379.6</b></li>
<li>human/cloudburst: <b>1376.9</b></li>
<li>human/decoysignal: <b>1372.2</b></li>
<li>human/chainlockv02a: <b>1370.0</b></li>
<li>human/burningmetal: <b>1367.7</b></li>
<li>human/defensive: <b>1365.0</b></li>
<li>human/firestorm: <b>1364.8</b></li>
<li>human/dawn2: <b>1362.2</b></li>
<li>human/mercenary: <b>1361.5</b></li>
<li>human/pdqscan: <b>1358.1</b></li>
<li>human/lastjudgement: <b>1351.7</b></li>
<li>human/rust: <b>1350.8</b></li>
<li>human/snowscan: <b>1350.6</b></li>
<li>human/frothandfizzle: <b>1346.6</b></li>
<li>human/thefugitive: <b>1346.3</b></li>
<li>human/blackknight: <b>1342.6</b></li>
<li>human/sonofvain: <b>1340.3</b></li>
<li>human/dawn: <b>1339.8</b></li>
<li>human/goldeneye: <b>1335.4</b></li>
<li>human/silking: <b>1332.1</b></li>
<li>human/artofcorewar: <b>1331.9</b></li>
<li>human/blowrag: <b>1329.2</b></li>
<li>human/returnofthejedimp: <b>1326.9</b></li>
<li>human/danceoffallenangels: <b>1324.6</b></li>
<li>human/azathoth: <b>1320.9</b></li>
<li>human/kosmos: <b>1319.4</b></li>
<li>human/simplicity: <b>1314.0</b></li>
<li>human/armadillo: <b>1313.3</b></li>
<li>human/combatra: <b>1313.2</b></li>
<li>human/cinammon: <b>1309.9</b></li>
<li>human/returnofthependragon: <b>1306.9</b></li>
<li>human/numb: <b>1305.0</b></li>
<li>human/neith: <b>1304.3</b></li>
<li>human/halcyon: <b>1303.2</b></li>
<li>human/olivia: <b>1303.2</b></li>
<li>human/reepicheep: <b>1301.3</b></li>
<li>human/hullab3loo: <b>1301.0</b></li>
<li>human/npaperii: <b>1300.7</b></li>
<li>human/elvenking: <b>1298.3</b></li>
<li>human/gargantuan: <b>1297.8</b></li>
<li>human/mandragora: <b>1296.4</b></li>
<li>human/safetyinnumbers: <b>1295.4</b></li>
<li>human/hullabaloo: <b>1290.9</b></li>
<li>human/eccentric: <b>1290.0</b></li>
<li>human/thunderstrike: <b>1289.6</b></li>
<li>human/impishv02: <b>1289.2</b></li>
<li>human/ziggy: <b>1289.0</b></li>
<li>human/stylizedeuphoria: <b>1288.7</b></li>
<li>human/ironicimps: <b>1287.6</b></li>
<li>human/gigolo: <b>1286.8</b></li>
<li>human/gremlin: <b>1285.1</b></li>
<li>human/borgir: <b>1283.6</b></li>
<li>human/unrequitedlove: <b>1279.4</b></li>
<li>human/themystery: <b>1278.0</b></li>
<li>human/spiritualblackdimension: <b>1276.2</b></li>
<li>human/recycledbits: <b>1273.1</b></li>
<li>human/jade: <b>1272.7</b></li>
<li>human/luca: <b>1268.9</b></li>
<li>human/vain: <b>1268.8</b></li>
<li>human/bitethebullet: <b>1268.3</b></li>
<li>human/disharmonious: <b>1267.6</b></li>
<li>human/uninvited: <b>1267.6</b></li>
<li>human/revengeofthepapers: <b>1267.4</b></li>
<li>human/bulldozed: <b>1265.7</b></li>
<li>human/diehard: <b>1264.2</b></li>
<li>human/nighttrain: <b>1263.0</b></li>
<li>human/blacken: <b>1262.7</b></li>
<li>human/sunset: <b>1261.6</b></li>
<li>human/devilish202: <b>1261.4</b></li>
<li>human/retroq: <b>1259.8</b></li>
<li>human/evolcap66: <b>1259.3</b></li>
<li>human/fixed: <b>1258.7</b></li>
<li>human/nemesis: <b>1258.5</b></li>
<li>human/ompega: <b>1258.2</b></li>
<li>human/stormkeeper: <b>1256.1</b></li>
<li>human/quicksilver: <b>1255.7</b></li>
<li>human/slimetest: <b>1255.3</b></li>
<li>human/rosebud: <b>1255.2</b></li>
<li>human/bluecandle: <b>1253.0</b></li>
<li>human/riseofthedragon: <b>1252.6</b></li>
<li>human/kryptonite: <b>1250.0</b></li>
<li>human/digitalis2003: <b>1245.4</b></li>
<li>human/freighttrain: <b>1245.4</b></li>
<li>human/electricrazor: <b>1244.8</b></li>
<li>human/forgottenlore2: <b>1244.3</b></li>
<li>human/timescape10: <b>1243.4</b></li>
<li>human/revivalfire: <b>1240.3</b></li>
<li>human/hellfire: <b>1239.7</b></li>
<li>human/nightterrors: <b>1238.1</b></li>
<li>human/thehistorian: <b>1236.9</b></li>
<li>human/borg: <b>1236.7</b></li>
<li>human/falconv03: <b>1236.2</b></li>
<li>human/torment: <b>1234.1</b></li>
<li>human/impfinityv4g1: <b>1232.7</b></li>
<li>human/behemot: <b>1230.5</b></li>
<li>human/returnofvanquisher: <b>1229.9</b></li>
<li>human/forgottenlore: <b>1228.4</b></li>
<li>human/sputnik: <b>1228.3</b></li>
<li>human/unpitq: <b>1227.8</b></li>
<li>human/vanquisher: <b>1227.7</b></li>
<li>human/blade: <b>1227.2</b></li>
<li>human/arrow: <b>1225.5</b></li>
<li>human/electrichead: <b>1225.2</b></li>
<li>human/lithobolia: <b>1224.1</b></li>
<li>human/enigma: <b>1223.8</b></li>
<li>human/valkyrie: <b>1223.5</b></li>
<li>human/hazylazy: <b>1223.3</b></li>
<li>human/shottonothing: <b>1222.1</b></li>
<li>human/bigitalshot: <b>1221.9</b></li>
<li>human/hazylazyc11: <b>1221.5</b></li>
<li>human/alladinscave: <b>1220.8</b></li>
<li>human/dust07: <b>1220.6</b></li>
<li>human/unpit: <b>1219.5</b></li>
<li>human/herbalavenger: <b>1219.3</b></li>
<li>human/grendelsrevenge: <b>1218.8</b></li>
<li>human/fireandice: <b>1218.5</b></li>
<li>human/whitemist: <b>1218.3</b></li>
<li>human/macromagic: <b>1218.0</b></li>
<li>human/xenosmilus: <b>1217.3</b></li>
<li>human/hector2: <b>1215.3</b></li>
<li>human/oblivion: <b>1214.1</b></li>
<li>human/bpanamax: <b>1213.9</b></li>
<li>human/carmilla: <b>1213.4</b></li>
<li>human/excalibur: <b>1213.3</b></li>
<li>human/simple88v2: <b>1212.9</b></li>
<li>human/kusanagi: <b>1212.8</b></li>
<li>human/perseus: <b>1211.7</b></li>
<li>human/barrage: <b>1211.1</b></li>
<li>human/jackinthebox: <b>1210.4</b></li>
<li>human/discord: <b>1209.7</b></li>
<li>human/boysarebackintown: <b>1208.8</b></li>
<li>human/nosferatu: <b>1208.1</b></li>
<li>human/pendulum: <b>1207.4</b></li>
<li>human/jinx: <b>1207.0</b></li>
<li>human/vampsareback02: <b>1205.1</b></li>
<li>human/zooom: <b>1204.8</b></li>
<li>human/sprawlingchaos: <b>1204.7</b></li>
<li>human/eternalexile: <b>1204.5</b></li>
<li>human/bloodlust: <b>1204.1</b></li>
<li>human/curseoftheundead: <b>1203.9</b></li>
<li>human/recon2: <b>1201.0</b></li>
<li>human/jackintheboxii: <b>1200.5</b></li>
<li>human/blizzard: <b>1199.8</b></li>
<li>human/hazyshadeii: <b>1199.0</b></li>
<li>human/sneakyb2: <b>1198.8</b></li>
<li>human/labomba: <b>1198.8</b></li>
<li>human/bluefunk3: <b>1198.3</b></li>
<li>human/lithium: <b>1197.8</b></li>
<li>human/damageincorporated: <b>1197.6</b></li>
<li>human/torcht18: <b>1197.0</b></li>
<li>human/probe: <b>1196.3</b></li>
<li>human/intotheunknown: <b>1195.6</b></li>
<li>human/grilledoctopus05: <b>1194.4</b></li>
<li>human/yogibear: <b>1193.5</b></li>
<li>human/infiltrator: <b>1193.1</b></li>
<li>human/myvamp54: <b>1192.5</b></li>
<li>human/claw: <b>1192.4</b></li>
<li>human/stoninc: <b>1192.2</b></li>
<li>human/chameleon: <b>1191.7</b></li>
<li>human/thenextstep88: <b>1191.3</b></li>
<li>human/julietandpaper: <b>1190.4</b></li>
<li>human/stalker: <b>1189.8</b></li>
<li>human/zygote: <b>1189.7</b></li>
<li>human/tnt: <b>1189.1</b></li>
<li>human/bayonet: <b>1188.4</b></li>
<li>human/mason20: <b>1185.1</b></li>
<li>human/tornado30: <b>1184.8</b></li>
<li>human/bluefunk: <b>1184.6</b></li>
<li>human/myvamp37: <b>1184.3</b></li>
<li>human/onebite: <b>1183.8</b></li>
<li>human/icedragon: <b>1182.6</b></li>
<li>human/win: <b>1181.2</b></li>
<li>human/soldieroffortune: <b>1179.0</b></li>
<li>human/mirage15: <b>1178.8</b></li>
<li>human/mirage2: <b>1178.7</b></li>
<li>human/nightofthelivingdead: <b>1178.7</b></li>
<li>human/flurry: <b>1177.2</b></li>
<li>human/blur2: <b>1176.4</b></li>
<li>human/blur: <b>1175.3</b></li>
<li>human/thermiteii: <b>1175.2</b></li>
<li>human/gemoftheocean: <b>1173.9</b></li>
<li>human/replicant: <b>1172.5</b></li>
<li>human/vamp02b: <b>1171.2</b></li>
<li>human/aeka: <b>1170.6</b></li>
<li>human/quiz: <b>1167.8</b></li>
<li>human/gothik: <b>1164.0</b></li>
<li>human/evoltmp88: <b>1162.1</b></li>
<li>human/twister: <b>1161.1</b></li>
<li>human/agonyii: <b>1158.8</b></li>
<li>human/steppingstone: <b>1157.2</b></li>
<li>human/abomination: <b>1155.6</b></li>
<li>human/phq: <b>1155.3</b></li>
<li>human/beholderseye17: <b>1150.3</b></li>
<li>human/armorya5: <b>1149.9</b></li>
<li>human/foggyswamp: <b>1149.9</b></li>
<li>human/elementaldust2: <b>1149.5</b></li>
<li>human/heremscimitar: <b>1149.2</b></li>
<li>human/pacman: <b>1148.8</b></li>
<li>human/leviathan: <b>1146.3</b></li>
<li>human/chimerav35: <b>1146.0</b></li>
<li>human/leapfrog: <b>1144.4</b></li>
<li>human/snake: <b>1143.9</b></li>
<li>human/irongate: <b>1141.6</b></li>
<li>human/fatexpansionv: <b>1138.7</b></li>
<li>human/seventyfive: <b>1137.6</b></li>
<li>human/kitchensinkii: <b>1136.9</b></li>
<li>human/cannonade: <b>1133.5</b></li>
<li>human/lucky3: <b>1133.3</b></li>
<li>human/winterwerewolf3: <b>1133.0</b></li>
<li>human/blur88: <b>1132.1</b></li>
<li>human/leprechaunonspeed: <b>1130.5</b></li>
<li>human/stasis: <b>1130.1</b></li>
<li>human/agony51: <b>1128.4</b></li>
<li>human/ttti: <b>1127.0</b></li>
<li>human/thermite10: <b>1124.5</b></li>
<li>human/capskeyisstuck: <b>1124.2</b></li>
<li>human/sj4a: <b>1123.4</b></li>
<li>human/medusasv7x: <b>1122.7</b></li>
<li>human/ncdecoy: <b>1122.2</b></li>
<li>human/agony31: <b>1122.2</b></li>
<li>human/hordesofmicrowarriors: <b>1121.1</b></li>
<li>human/sphinxv28: <b>1118.6</b></li>
<li>human/rave: <b>1115.5</b></li>
<li>human/keystonet13: <b>1113.6</b></li>
<li>human/charonv81: <b>1113.2</b></li>
<li>human/leprechaun1b: <b>1106.0</b></li>
<li>human/nomuckingabout: <b>1096.6</b></li>
<li>human/charonv70: <b>1095.4</b></li>
<li>human/bscannersliveinvain: <b>1094.9</b></li>
<li>human/crimp2: <b>1092.1</b></li>
<li>human/crimp: <b>1090.7</b></li>
<li>human/killerinstinct: <b>1088.4</b></li>
<li>human/imprimis6: <b>1084.4</b></li>
<li>human/griffin2: <b>1083.7</b></li>
<li>human/requestv20: <b>1076.7</b></li>
<li>human/impurge: <b>1067.2</b></li>
<li>human/backstabber: <b>1066.2</b></li>
<li>human/0stormbringer: <b>1065.0</b></li>
<li>human/twilightpitsv60: <b>1060.2</b></li>
<li>human/fastfoodv21: <b>1056.8</b></li>
<li>human/flashpaper: <b>1046.7</b></li>
<li>human/flashpaper37: <b>1045.9</b></li>
<li>human/gammapaper30: <b>1045.4</b></li>
<li>human/flypaper30: <b>1040.7</b></li>
<li>human/hydra: <b>1026.4</b></li>
<li>human/precipice: <b>1025.0</b></li>
<li>human/trinity: <b>1022.7</b></li>
<li>human/paratroopsv21: <b>1017.9</b></li>
<li>human/genocide: <b>1015.6</b></li>
<li>human/vagabond: <b>1001.0</b></li>
<li>human/notepaper: <b>967.6</b></li>
<li>human/returnofthelivingdead: <b>955.5</b></li>
<li>human/smoothnoodlemap6: <b>909.9</b></li>
<li>human/smoothnoodlemap: <b>887.8</b></li>
<li>human/dwarf: <b>864.3</b></li>
<li>human/validate: <b>344.1</b></li>
<li>human/pspace: <b>-889.5</b></li>
</ol>

</details>

**Run it yourself.** [Set up CodeClash](https://docs.codeclash.ai/quickstart/#installation) and send a model up the ladder with:

<pre class="prettyprint lang-bash">
uv run codeclash ladder run configs/ablations/ladder/corewar.yaml
</pre>

---

### References

* [Core War Official Documentation](https://corewar.co.uk/index.htm)
* [CodeClash GitHub Repository](https://github.com/CodeClash-ai/CoreWar)

If you evaluate on Core War using CodeClash, in addition to our work, we recommend the following citation for attribution to the original creators:

<pre>
@misc{corewar1984,
    title={Core Wars Guidelines},
    author={Jones, D.G. and Dewdney, A.K.},
    url={https://corewar.co.uk/standards/cwg.txt},
    year={1984},
}
</pre>
