# Policy-safe prompting for Seedance 2.5 (and most video models)

Moderation runs on BOTH the text prompt and the reference images. A block costs credits and time. Design the prompt so it never gets close to the line, while still selling hard. These are practical patterns, not legal advice; platform rules change, so when a render is blocked read the actual error and fix the specific trigger.

## 1. What triggers blocks (and why)

| Trigger | Typical examples | Why it blocks |
|---|---|---|
| Real people / likeness | celebrity names, "looks like X", real influencer photos as references, user selfies of other people | identity and deepfake protection; real faces are often hard-blocked at the image scan |
| Protected brands / characters | "Nike", "Stanley cup", "Dyson-style", "Disney", "Marvel", "Barbie" | trademark and IP filters |
| Medical and health claims | "cures acne", "removes wrinkles in 7 days", "lose 10 pounds", "treats anxiety", "kills 99.9% bacteria" | health-claim filters; also an advertising-compliance problem |
| Minors | children + anything ingestible, cosmetic, sharp, hot, or body-related; "teen", "schoolgirl" | child-safety filters are aggressive and literal |
| Nudity / sexualization | "lingerie", "topless", "wet skin close-up on thighs", "seductive", "bikini try-on" | adult-content filters trigger on wording even in beauty contexts |
| Body-part focus | "close-up of her chest/butt", "rubbing cream on breasts" | same filter class as above |
| Violence / weapons / self-harm | knives in threatening context, blood, "smash", "stab", "crush test on skull" | safety filters; unboxing knives is fine when framed as cutting an apple |
| Regulated substances | alcohol, tobacco, vapes, CBD/THC, prescription drugs, gambling | regulated-category filters |
| Hate / politics / religion | flags, slogans, religious symbols as props | sensitivity filters |
| Text generation | asking for logos, slogans, captions, price tags in-frame | not a policy block but produces garbage text; add in post |
| Deceptive framing | "fake news broadcast", "doctor in white coat endorsing" | impersonation of authority |

## 2. Neutral phrasing — the swap table

Write the right column, never the left.

| Instead of | Write |
|---|---|
| the creator (real name or celebrity) | a fictional adult creator, [traits] |
| "Nike-style sneakers" | "white low-top trainers, plain, no logos" |
| "cures acne" / "removes wrinkles" | "the gel is designed for blemish-prone skin" / "she pats the cream in along her cheekbone" (show, do not promise) |
| "lose weight" | "fits into her routine" / show the product in use, never the outcome |
| "sexy", "seductive", "sensual" | "relaxed", "confident", "unbothered" |
| "bikini try-on", "lingerie" | "swim top under an open linen shirt" (if essential) or avoid the category |
| "rubs lotion on her legs/chest" | "smooths lotion over the back of her hand and forearm" |
| "wet skin, glistening" | "freshly washed face, towel-dried, slightly damp hairline" |
| "kid eats the gummies" | "parent places the bottle on the counter; child is not shown" (or adult only) |
| "toddler plays with the toy alone" | "parent sits beside the toddler, hands visible, soft play mat" (only for age-appropriate toys) |
| "sharp knife slicing fast" | "chef's knife slices a tomato in one controlled stroke on a wooden board" |
| "wine", "beer", "vape" | do not advertise; if a glass is a prop, write "a glass of sparkling water" |
| "doctor recommends" | "the label lists ..." / "the box says ..." (only if the box really says it) |
| "99.9% germs" | "wipes the counter clean; the surface looks dry and streak-free" |
| "before/after transformation" | "method demonstration: how it is applied" |
| "pregnant woman" / "baby bump" in product shots | avoid unless the product is maternity and the user requests it; keep clothing full-coverage |
| "shower scene" | "standing at the bathroom sink, hair tied up, towel on the shoulder" |

## 3. Category-specific guardrails

**Skincare / beauty**
- Apply to face, hand, forearm, neck only. Never chest, legs, stomach.
- Say "designed for", "formulated with [ingredient only if listed on page]", "feels lightweight", "absorbs". Never "treats", "cures", "heals", "removes", "anti-aging result".
- Towel, robe-over-top, or crew-neck tee. Bare shoulders only if the frame is tight on the face and the user accepts the risk.
- Avoid the words: dermatologist (unless on the box), medical-grade, clinically proven (unless on the page and you quote it exactly), acne (prefer "blemish-prone"), wrinkles (prefer "fine lines" only if the page uses it).

**Supplements / food**
- Adult only. Show the capsule/scoop/gummy held or dropped into water; swallowing is fine if calm and single.
- Never promise energy, sleep, weight, immunity, focus or hormone outcomes; say "part of her morning routine".
- No "FDA approved". If a certification is printed on the pack, reference "the badge on the label as in @Image1" instead of naming the authority.

**Baby / kids**
- Parent is the creator. Child appears only when needed, fully clothed, never alone with the product, never ingesting anything in frame, never in a bath.
- No "baby-safe", "non-toxic" unless on the page; say "the label shows ...".

**Fitness / wearables / shapewear**
- Athleisure with full coverage (leggings + fitted tee or hoodie). No mirror poses that emphasize body parts. Show the function: strap, step, stretch, buckle.

**Pet**
- Supervised, calm pet. No pet consuming a non-food product. No pet "fighting" the tool.

**Cleaning / home**
- Household chemical bottles are fine; never spray toward a face or food. Gloves if the product page says so.

**Kitchen / knives / heat**
- One controlled slice. Pan handles held properly. No open flames close to hair or fabric.

**Fashion / jewelry**
- Standard streetwear coverage. Jewelry close-ups on the hand/neck/ear. No "sheer", "see-through", "bodycon close-up".

**Tech / gadgets**
- Screens show a generic UI; write "screen shows a simple neutral interface, no readable text, no app logos".

## 4. Reference image hygiene (image-scan layer)

- Product photo: crop to the product only. Remove other brands, shop UI, price stickers, barcodes, and especially other people's faces or hands from the screenshot.
- Creator image: must be a fictional AI-generated portrait (Influencer Studio / Soul). Do not use photos of real people, including the client, unless they have authorized it AND the host allows it.
- Style/video reference: use clips without visible brands, text overlays or recognizable creators; or describe the style in words instead.
- Do not pass screenshots that contain watermarks or platform UI.

## 5. The "legal-but-hot" words to keep out of the prompt text

guarantee, cure, heal, treat, clinically, medical, doctor, FDA, instantly, permanently, 100%, miracle, detox, burn fat, anti-aging, sexy, seductive, lingerie, bikini, nude, topless, wet skin, kid/child/teen (unless the product category requires a supervised parent-child frame), knife (use "chef's knife on a cutting board" only in cooking context), gun, blood, alcohol, beer, wine, vape, cigarette, casino, any celebrity or brand name other than the client's own.

## 6. If a render is blocked anyway

1. Read the error. Image block -> fix the reference (crop, swap to AI portrait). Text block -> search the prompt for the hot words above.
2. Rewrite the single offending sentence with the swap table; do not pad the prompt with "safe for work".
3. If the product category is inherently sensitive (intimate wellness, shapewear, medical devices), switch to a hands-and-product or product-only concept with voiceover; it is almost always approvable and still converts.
4. Never try to "trick" the filter with misspellings or Unicode; it fails and risks the account.
