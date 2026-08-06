# Briefs

Each brief you bring to the agent — for critique, ideation, art direction, or anything else — gets a card here. Brief cards are the *node* in the corpus graph. They reference the corpus cards (category, brand, shape, principle) and capture the work done on this brief.

A brief card is not part of the runtime corpus. The agent does not load briefs on demand the way it loads `references/`. Briefs are session-history. They tell future-you (and future-the-agent) what was tried, what was kept, and what was learned.

## When to write a brief card

Write one when:

- A new brief arrives (write it before doing the work).
- The agent loads multiple corpus cards for one brief (the brief card lists which ones, so future briefs can follow the same path).
- A brief ships, gets killed, or lands in market (write the outcome).
- You want to remember why a decision was made.

## When not to write a brief card

- For questions that aren't briefs ("what's the cliché in this category?"). Those are principle-card candidates.
- For campaigns from the past that aren't tied to a current piece of work. Those are campaign cards.
- For casual references ("have you seen this ad?"). Those are campaign or principle cards.

## Filename

```
briefs/YYYY-MM-DD-short-slug.md
```

Examples:
- `briefs/2026-08-07-toys-r-us-kv.md`
- `briefs/2026-08-09-sg60-singapore-flyer.md`

## Template

Use `briefs/_template.md`. It captures: original brief, category/brand/shape inferences, which corpus cards were loaded, the agent's first read, your decisions, the output, the outcome.

Brief cards accumulate. After ten briefs in the same category, you have a category-specific working history. After fifty, the agent is operating on your accumulated taste, not generic category knowledge.