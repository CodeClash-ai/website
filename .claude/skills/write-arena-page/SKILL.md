---
name: write-arena-page
description: >-
  Write the codeclash.ai arena page for a CodeClash arena. Use when asked to
  "write/add an arena page", "document an arena on the website", or "write up
  <arena> for the site". Produces pages/arenas/<arena>.md matching site conventions.
---

# Write an Arena Page

An arena page is a single markdown file, `pages/arenas/<arena>.md`, with a
key-value front matter block followed by the write-up body. `server.py` serves it
at `/arenas/<arena>/`, `templates/arena.html` renders it, and `templates/arenas.html`
auto-lists it on the index (sorted by title) — **no registration anywhere else.**

## Learn the arena first (don't write from the description alone)

The prompt's blurb is a starting point, not the source of truth. Before writing:

1. **Read the arena class** `repo/codeclash/arenas/<arena>/<arena>.py` — its `name`,
   `submission` file, `description`, and `validate_code` define the exact bot contract.
2. **Read the arena's own repo** (the Dockerfile `git clone`s `CodeClash-ai/<Arena>`).
   Its `README.md` + engine are the ground truth for rules, physics constants, the
   `obs`/state shape, actions, scoring, and win condition. Prefer engine code over the
   README when they disagree, and note the real starting conditions (e.g. balls that
   start at rest, side-swapping across seeded games).
3. **Read the test config** `repo/configs/test/<arena>.yaml` for player count and the
   `game_description` prompt shown to agents.
4. **Read 2-3 existing pages** in `pages/arenas/` to match tone and depth. Short
   train-split arenas (`bomberland.md`, `scml.md`) are the default shape; big
   test-split / ladder arenas (`battlesnake.md`, `corewar.md`) add extra sections.

## Front matter (one `key: value` per line, no `---` fences)

```
title: <Display name>
logo: /static/images/arenas/<arena>.png
preview: /static/images/arenas/<arena>.gif
preview_width: 55            # optional, % width of the preview (default 50)
description: <one line, imperative, no period — shown on the index card>
date-added: <YYYY>-<MM>-<DD>T00:00:00.000000Z   # date the arena was added
players: 2+                  # or an exact count, matching the arena/config
language: Python             # comma-separated; must have a matching static/images/languages/<lang>.svg
split: train                 # train = no leaderboard; test = renders the Leaderboard section
ladder: true                 # optional; adds the 🪜 badge + expects a CC:Ladder section
```

Set `split: test` only for arenas that have leaderboard data in `data/leaderboards.json`
(keyed by the page slug); otherwise `train`. Add `ladder: true` only if a CC:Ladder
exists — then include a `## 🪜 CC:Ladder` section (see `battlesnake.md`).

## Body

Four bold-question sections in this order, each one tight paragraph:

- **What is `<Arena>`?** — the game in one or two sentences + the win condition.
- **How does it work?** — the submission file, the entry function + its signature, the
  legal actions/return values, what `obs` (game state) contains, and how a round is scored.
- **What's the goal?** — the objective and the core scoring mechanic; call out any
  non-obvious rule (e.g. "doing nothing scores nothing").
- **What makes it challenging?** — the real strategic tension, concretely.

Then a `---`, an `### References` list (the arena's own repo + the CodeClash repo), and —
**only if the arena ports an external game** — a `<pre>` BibTeX block crediting the
original creators (see `bomberland.md`). Original CodeClash games need no third-party
citation.

## Accuracy rules

- Quote real numbers (grid size, tick budget, key physics constants) from the engine, not
  guesses. Preserve the arena's own terminology.
- State exact action strings / return values and the entry-function signature verbatim.
- Don't invent features, external inspirations, or citations the repo doesn't support.

## Assets (separate deliverable)

The page references `static/images/arenas/<arena>.png` (logo) and `.gif` (gameplay
preview). These are generated from a replay, not hand-authored — if they don't exist yet,
write the page with the conventional paths and flag that the two image assets still need to
be produced. Never commit a fabricated/placeholder binary.

## Verify

Run `python server.py` in `website/` and open `/arenas/<arena>/` and `/arenas/`, or
`python server.py build` to freeze. Confirm the page renders, the card appears on the
index, and the language icon resolves.
