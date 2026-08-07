# creative-director-skill

A working creative director for an advertising context. Three-layer architecture: reasoning (model-driven), knowledge (corpus on demand), vocabulary (style register).

Five jobs at MVP: brief critique, ideation, brainstorm expansion, art direction, work critique. Brief critique is the entry point — it runs first when a brief arrives, before any work is produced.

## Repo layout

```
SKILL.md                  # Layer 1 — reasoning (posture, moves, output shapes)
references/
  index.md                # Layer 2 — index of all corpus cards
  campaigns/              # Layer 2 — one file per famous campaign
  principles/             # Layer 2 — one file per principle of art direction
  vocabulary/             # Layer 3 — vocabulary patterns (currently tone-registers.md)
briefs/                   # brief cards — one folder per real brief, agent writes
examples/                 # worked examples of the four jobs (added over time)
sessions/                 # scrap-session notes (added over time)
```

## Branches

- `main` — the merged, stable corpus
- `scratch` — the active scrap session, merged to `main` after review

## Adding cards

1. Copy the appropriate template (`references/campaigns/_template.md`, `references/principles/_template.md`, `references/vocabulary/_template.md`).
2. Write the card. Cards are short — 100–400 lines.
3. Add the one-line entry to `references/index.md`.
4. Commit on `scratch`. Merge to `main` after review.

## Card quality rule

Don't write a campaign card unless the visual mechanism can be named from the source. Cards from rationale-text-only fetchers (D&AD, TBWA scrape) wait for an image. The corpus is only as useful as its weakest card; one thin card is a tax on every future session.

## Brief cards

Each real brief the agent works on becomes a brief card under `briefs/`. The card captures: original brief, the agent's first read, corpus cards loaded, work done, your decisions, the output, the outcome, lessons. Brief cards are session-history, not part of the runtime corpus. See `briefs/README.md` for the format and when to write one.

## Expanding scope

To add a new job to the skill (presentation, brief writing, strategy, etc.):

1. Add a new section to `SKILL.md` Layer 1 with posture + moves + output shape.
2. Add the relevant cards to Layer 2 (`references/`).
3. Update the frontmatter version.
4. Update this README.

## Versioning

`SKILL.md` has a version in its frontmatter. Bump on:
- New job added
- Layer architecture change
- Posture or move rewrite

Do not bump on card additions.