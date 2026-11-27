# LabelKit — Read Any Food Label in Plain Words

**Live:** https://abhiramunni.github.io/labelkit/

The packet says "healthy". The label tells the truth. LabelKit turns the numbers on the back of any food packet into plain words: traffic lights for sugar, salt, fat and saturated fat, a score out of 100, and what one serving really does to your day.

## What it does

- **Label Decoder** — type the per-100g values from any packet (energy, sugars, salt, total fat, saturated fat, protein, fibre, serving size) and get a verdict stamp (Everyday pick / Sometimes food / Occasional treat / Best left on the shelf), a score ring, four traffic lights, the sugar in teaspoons per serving, and a plain-words explanation.
- **Quick picks** — 12 well-known Indian packets pre-loaded with typical per-100g values (Parle-G, Maggi, cola, Kurkure, Haldiram's Bhujia, ketchup, cornflakes, white bread, chocolate milk, potato chips, energy drink, oats biscuits). Tap one to load it into the decoder. Values are labelled "typical" — always check your own pack.
- **Compare shelf** — add up to 3 decoded products side by side; the best score gets the green crown.
- **Today's budget** — log servings against the WHO daily guidance (25g added sugar, 5g salt). Rings fill as you log; the header pill always shows today's totals.
- **Sugar's many names** — 12 hidden-sugar aliases (dextrose, maltodextrin, jaggery, agave…) with a tap-to-read explanation for each.
- **Guides** — six plain-language guides, including the serving-size trap, salt vs sodium (salt = sodium mg × 2.5 ÷ 1000), "no added sugar" tricks, and what the new FSSAI front-of-pack warnings will mean (the Supreme Court asked FSSAI in November 2026 to finalise "High Sugar / High Salt / High Fat" warnings within four months).

## How the score works

Traffic-light thresholds follow the widely used UK front-of-pack system, per 100g:

| Nutrient | Green (low) | Amber (medium) | Red (high) |
|---|---|---|---|
| Sugars | ≤ 5g | ≤ 22.5g | > 22.5g |
| Salt | ≤ 0.3g | ≤ 1.5g | > 1.5g |
| Total fat | ≤ 3g | ≤ 17.5g | > 17.5g |
| Saturates | ≤ 1.5g | ≤ 5g | > 5g |

A light also turns red if one serving crosses the per-serving red line (sugar > 27g, salt > 1.8g, fat > 21g, saturates > 6g). Score starts at 100: −22 per red light, −8 per amber light, −10 if one serving carries 20g or more of sugar, +5 for high fibre (≥ 6g), +3 for high protein (≥ 10g).

## Tech

- One self-contained `index.html` — no backend, no signup, no tracking.
- All data stays in the browser (`localStorage`, key `labelkit-v1`).
- Warm editorial design (ivory paper, espresso ink, bronze/amber/terracotta), Fraunces + Inter, cinematic intro with tap-to-skip, 3-step onboarding tour, Ken Burns photography.
- Two AI-generated warm-editorial photos served with the page (labelkit-hero.webp, labelkit-flatlay.webp).

## QA

`qa-test.js` — 114 headless jsdom assertions, all passing: structure, threshold boundaries, hand-checked scores for all 12 quick picks, decode / log / compare / erase flows, zero uncaught JS errors. Run with `node qa-test.js` (requires jsdom). Live verified 27 Nov 2026.

## Disclaimer

A guide, not medical advice. If you manage diabetes, blood pressure or kidney disease, check with your doctor. Typical values are indicative; brands change recipes.
