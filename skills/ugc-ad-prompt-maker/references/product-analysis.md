# Product analysis, buyer psychology and claim discipline

The ad is only as good as the truth underneath it. Spend the first minutes here.

## 1. Extract from the product URL

Read, in order: title, price and offer block, bullet points, long description, specs table, "how to use", FAQ, shipping/returns/guarantee, and the review summary (star distribution + the 3-5 most repeated phrases). Capture:

- **Exact product name and variant** (color, size, pack count, scent, flavor).
- **What it does** in one sentence a 12-year-old understands.
- **Mechanism**: which part is held, which part touches what, what direction it moves, what happens physically.
- **Stated features** (quote them) and **stated outcomes** (quote them).
- **Verified offer**: price, discount, bundle, free shipping, guarantee — only if written on the page right now.
- **Customer language**: the words buyers use in reviews for the problem ("my couch looks like a sheepdog", "my serum pills under makeup"). These become dialogue.
- **Objections** found in low-star reviews or FAQ (too small, hard to clean, smell, sizing, battery life).
- **Limitations and safety** (not for X, keep away from Y). Respect them in the storyboard.

If the URL is not readable (blocked, login, app-only), say so in one line, work from images and details, and label conclusions as assumptions.

## 2. Extract from product images

For every image note: silhouette, proportions relative to a hand, materials and finish (matte/gloss/fabric/metal), colors (name them), moving parts (cap, lid, hinge, pump, button, zip, port), label/logo placement, packaging, and which angles are visible. Write 5-8 **identity locks**: the things that must stay identical on screen. Example:

```text
IDENTITY LOCKS
1. Matte sage-green cylinder, about palm height
2. Flat white pump cap, pressed straight down
3. Off-white label band on the lower third with dark grey text
4. Single bottle, no box shown
5. Front label faces camera; no claims about the back label (not supplied)
```

If only a front photo exists, never invent the back, the inside, or a hidden feature.

## 3. Feature -> Benefit -> Outcome

Fill this for the 2-3 strongest features only, then pick ONE to carry the ad.

| Feature (verifiable) | Practical benefit | Desired life outcome | Visible on camera? |
|---|---|---|---|
| Reusable rubber bristles | Collects pet hair without sticky sheets | Couch is guest-ready in 2 minutes | Yes: hair collects in strokes |
| Foldable handle | Fits in a kitchen drawer | Not another gadget on the counter | Yes: fold and drop in the drawer |

A feature that cannot be shown should not carry the ad.

## 4. Buyer as a situation

Write the buyer as one specific moment, then the emotion under it.

```text
BUYER SITUATION
US, suburban, 36, two kids and a golden retriever, 10 minutes before her in-laws arrive, lint roller is out of sheets again.
Functional want: hair off the couch fast.
Emotional want: not feeling judged about her home.
Awareness: problem-aware (knows the hair is a problem, does not know a reusable tool exists).
```

Awareness stage -> hook type:
- Unaware -> show the situation so they recognize themselves.
- Problem-aware -> name the frustration, show the fix fast.
- Solution-aware -> "why this kind of tool", quick comparison with the old way.
- Product-aware -> differentiation, objection-killer, detail close-up.
- Most-aware -> verified offer or convenience; the CTA is the hero.

## 5. US vs UK market notes

| Dimension | US (default) | UK |
|---|---|---|
| Spelling / words | color, favorite, sneakers, couch, trash, apartment, mom, diaper, stroller, drugstore, zip code | colour, favourite, trainers, sofa, bin, flat, mum, nappy, pushchair, chemist/Boots, postcode |
| Tone | upbeat, direct, benefit-forward, "honestly", "okay so", "literally" | drier, understated, self-deprecating, "right", "to be fair", "proper", "a bit", "decent" |
| Rooms | large kitchen island, open-plan living room, carpeted bedroom, big fridge, garage | smaller kitchen with kettle and tiled splashback, terraced house / flat, radiator under window, soft overcast daylight, carpeted stairs |
| Light | brighter, warmer interior light; big windows | softer, cooler, often overcast daylight; lamps on in daytime |
| Price talk | "$" and "under 30 bucks" only if verified | "£" and "under thirty quid" only if verified |
| CTA phrasing | "Grab yours at the link", "Check it out", "Shop now" | "Link's below", "Have a look", "Worth a look" |
| Avoid | British slang, "mate", "cheers" | overly hyped US phrasing, "you guys", "awesome" repeated |

Never mix markets in one ad.

## 6. Claim discipline (the lines you do not cross)

Allowed:
- Observed: "the pump clicks", "the fabric stretches", "the lid seals".
- Source-supported, quoted or closely paraphrased: "the page says it's dishwasher-safe".
- Designed-for language: "made for blemish-prone skin".
- Creator opinion about what is visible: "that's a lot of hair for one pass".

Not allowed (unless the user supplies substantiated, compliant evidence and asks for it):
- Results: cures, removes, fixes, whitens, grows, burns, lifts, "in 7 days".
- Numbers: percentages, counts, "10,000 reviews", "#1", "best".
- Comparatives naming competitors.
- Personal history: "I've used this for 3 months" — the creator is a fictional demonstrator, not a customer.
- Scarcity/urgency not on the page: "only today", "selling out".
- Safety words not on the page: "non-toxic", "hypoallergenic", "baby-safe".

Wording that sells without claiming: "This is the part that got me", "Watch how fast this is", "You can actually see it working", "That's the whole thing. Done.", "I didn't expect it to do that", "It just sits in the drawer now".

## 7. Sensitive categories (extra care)

Skincare, supplements, baby, pets, fitness, intimate wellness, medical devices, knives/heat, chemicals. For each: show the method, never the medical result; adult creator; full-coverage wardrobe; follow the swap table in `seedance-2.5-prompting/references/policy-safe-prompting.md`.

## 8. Output of this step (feeds the Brief)

```text
PRODUCT: [exact name/variant]
WHAT IT DOES: [one sentence]
MECHANISM: [hold / contact / motion / result]
IDENTITY LOCKS: [5-8 bullets]
VERIFIED FACTS: [quotes]
ASSUMPTIONS: [labeled]
UNKNOWNS: [what we will not show]
BUYER SITUATION: [US/UK, moment, functional want, emotional want, awareness]
CARRYING FEATURE: [one]
OBJECTION TO DEFUSE (optional): [one]
VERIFIED OFFER / CTA BASIS: [or "none, use soft CTA"]
```
