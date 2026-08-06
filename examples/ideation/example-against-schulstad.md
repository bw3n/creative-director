# Worked Example: Ideation Against Schulstad

This example shows how the creative-director skill's `ideation` job operates against an existing corpus card.

## User input

A brief from a hypothetical client:

> We're launching a new premium instant coffee. The category is full of
> brands that romanticise the coffee ritual — the slow pour, the vintage
> grinder, the morning light. Our coffee is the opposite: it tastes
> excellent, you make it in 15 seconds, and it's meant for people who
> have better things to do than perform a coffee ceremony.
>
> Give me three territories.

## Load order

1. **SKILL.md** (Layer 1 reasoning, posture, moves, output shape for ideation).
2. **`references/index.md`** — agent scans for relevant cards. The brief touches on:
   - A product that contradicts category clichés → `principles/category-cliche.md` is read.
   - A product that delivers a specific experience rather than a generic promise → `schulstad-emergency-slice.md` is read as the closest analogue (a brand that rejected the gratitude angle and delivered a physical artefact at the moment of need).
3. **`references/vocabulary/tone-registers.md`** — generative register loaded before output.

Note: no principle card called `category-cliche` exists yet. In a real session, the agent would either read it as a missing card or work from the reasoning layer's built-in cliché-detection moves. The skill handles this gracefully because `SKILL.md` Layer 1 is self-contained.

## Output

```
IDEA 1 — "The 15-Second Ceremony"

HUMAN TRUTH: Time is the new luxury. The people who can afford
a coffee ceremony are not the people who need this product.

CATEGORY CLICHÉ REJECTED: The premium-instant-coffee category has
spent the last decade trying to make its product feel slow, ritual,
hand-crafted. The whole category is performing a lie — instant
coffee is fast because it's instant, and dressing it up in slow
imagery insults the customer's actual life.

TENSION: Performance vs. function. Every premium coffee ad says
"stop, smell, savour." This one says "you have better things to do."

TERRITORY: Urban / late-night / the-after-the-meeting-decompression
register. The visual register is the opposite of coffee-advertising-
as-usual: no slow-motion steam, no mahogany table, no porcelain
cup. The visual is the desk, the kettle, the rushed phone call.

EXECUTION MECHANISM: A 15-second film that actually runs in
15 seconds. The product is made on camera in real time, then
drunk. Cut every slow-mo. The film is the brief.

WHY IT IS NOT OBVIOUS: The category cliché is the slow-ceremony
romanticism. This work treats the ritual as a tax the customer
pays when they have nothing better to do. The product's
15-second nature is the brand's identity, not its limitation.

ALTERNATE TERRITORIES:

IDEA 2 — "No Ceremony" (Type-only, brutal typography, a manifesto
that names the slow-ceremony lie and refuses it. The product itself
is never shown — the work IS the brand.)

IDEA 3 — "The Other 23 Hours" (A campaign that treats the coffee
moment as the briefest, brightest 15 seconds of a much longer
day. The visual register is a long day's worth of work, with
the coffee shot as the only moment of pause — the opposite
of the standard "coffee is the morning pause" idea.)
```

## What the corpus contributed

- **Schulstad** is referenced in the `CATEGORY CLICHÉ REJECTED` and `WHY IT IS NOT OBVIOUS` fields. Schulstad refused the gratitude cliché by handing rye bread at the moment of absence. This work refuses the ceremony cliché by being honest about speed. The pattern is the same: refuse the category's sentimental version of the user.
- **Heritage-vs-relevance pattern** (extracted as a principle card after this session's principle-extraction step) is implicit in the tension. Premium instant coffee is heritage-coded as slow, modern-coded as fast. The work lives in the gap.

What the corpus did *not* contribute:

- A worked example of "premium FMCG that contradicts category cliché." None of the three existing cards is a perfect fit. The agent used the *pattern* (cliché refusal + form-of-product-as-claim) rather than the *case*.
- This is the right way for the corpus to work at this size. Three cards is not enough for direct case-matching. It's enough for pattern-matching. The corpus becomes more useful as it grows; by ~15 cards, direct matches will start to appear.

## Notes for the agent

- The tension field is the most important one to get right. If the tension is wrong, the whole idea is wrong. Spend more time on it than on the territory.
- The cliché field is the second most important. If you can't name the cliché, you don't yet understand the category.
- The "WHY IT IS NOT OBVIOUS" field is the most undervalued. It is the test of whether the idea actually escapes the cliché or just re-dresses it.
- The alternates are not throwaways. If the agent produces alternates that are stronger than the developed idea, the agent should flag that. The user may want to develop a different one.