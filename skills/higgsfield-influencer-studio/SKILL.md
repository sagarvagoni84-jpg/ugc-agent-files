---
name: higgsfield-influencer-studio
description: Design the perfect fictional AI creator for a UGC product ad using Higgsfield Influencer Studio (menu-based character builder) and Soul ID for consistency. Covers casting that mirrors the US/UK buyer, attribute selection (age presentation, face, skin texture, body, hair, expression), wardrobe and background by product category, policy-safe styling, a photoreal portrait-prompt fallback, and the hand-off to Seedance 2.5 as an @Image identity reference. Use whenever an ad needs a visible person.
---

# Higgsfield Influencer Studio — casting and building the ad creator

The creator in a UGC ad is a trust device. Buyers believe people who look like them, live in rooms like theirs, and react the way they would. The job here is to cast and build that person, make them repeatable, and hand a clean identity reference to the video model.

What Influencer Studio is (verify the current UI; menus change): a visual character builder where you pick attributes from categories (identity, age presentation, face structure, skin, body proportions, hair, style, expression, etc.) instead of writing a prompt, generate a base look, then save it. For a face that stays identical across outfits, scenes and videos, train a **Soul ID** on a batch of 20+ varied portraits of the finished character and select that identity in later generations. Text prompting is the fallback when a menu option does not exist.

Reference files:
- `references/casting-matrix.md` — buyer -> creator mapping for US and UK, by product category and price point.
- `references/wardrobe-by-category.md` — what the creator wears and where they stand for each product type, with policy-safe notes.

---

## 1. Casting rules

1. **Mirror the buyer, not the fantasy.** A $29 pet-hair remover is bought by a tired pet owner, so cast a relatable 30s-40s person in a lived-in living room, not a model in a loft. Aspirational casting is only correct when the product IS aspiration (luxury skincare, fashion).
2. **Approachable over perfect.** Real pores, a few stray hairs, slight asymmetry, natural under-eye shading, imperfect brows. Viewers skip faces that look like stock photography.
3. **Age-appropriate to the category.** Acne-focused skincare: 20s. Anti-aging claims (if supported): 40s-50s. Baby products: parent 28-38. Supplements for joints: 45+. Gadgets: 25-40. Cleaning: 30-45. Never present a creator as a minor.
4. **Market-neutral but local.** US default: natural American look and styling; UK: subtly different wardrobe (layers, knitwear, trainers), flat/terraced-house interiors, softer daylight. Do not equate ethnicity with product fit; pick a believable creator for the location and buyer, with diversity across your roster.
5. **One creator per ad, one roster per brand.** Reuse the same Soul ID across a brand's ads so the account feels like one person. Never present the creator as a real customer or use any real person's likeness.
6. **Hands matter as much as face.** Clean, natural nails (short or neutral polish), no rings that reflect, no sleeve covering the wrist during demos.

## 2. Attribute sheet (what to set in the builder)

Output this table for every ad. If a menu option does not exist, write the closest option and add the detail to the portrait prompt.

| Attribute | Decision | Why |
|---|---|---|
| Age presentation | e.g. "early 30s" | matches buyer |
| Gender presentation | | matches buyer or product use |
| Face structure | e.g. "soft oval, slightly rounded jaw" | approachable |
| Skin | tone + "visible texture, light freckles, no retouch" | realism |
| Eyes / brows | e.g. "medium brown, natural brows" | avoids doll look |
| Hair | color, length, style; "a few strands loose" | continuity + realism |
| Body type | e.g. "average build" | relatable |
| Expression baseline | "relaxed, slight natural smile, not grinning" | UGC tone |
| Style preset | "casual everyday" / "athleisure" / "smart casual" | per category |
| Makeup level | "minimal" unless beauty product calls for it | realism |
| Accessories | "none" or one simple item | avoid reflections/logos |

## 3. Portrait generation plan (max 3 images per ad)

1. **Identity portrait** — waist-up, straight to camera, relaxed, soft window light, plain neutral wall. This is `@Image2` for Seedance.
2. **Optional wardrobe/body view** — only for try-on, fitness, fashion, or when the demo shows the torso and hands together. Same identity, the actual ad outfit.
3. **Optional targeted fix** — only if a defect blocks use (hand, eye, hairline).

Portrait prompt fallback (use in Soul / any photoreal image model when the builder lacks an option):

```text
Photorealistic smartphone-style portrait of a fictional adult [gender presentation], [age presentation], [face structure], [skin tone] skin with visible natural texture and light under-eye shading, [eye color] eyes, natural [brow description], [hair color/length/style] with a few loose strands. Waist-up, facing camera, relaxed direct gaze, slight natural smile, shoulders at ease. Wearing [ad wardrobe: plain, no logos, no text]. Soft daylight from a window on the left, plain light-neutral wall, shallow but realistic depth. No beauty filter, no retouching, no jewelry, no text, no watermark, single person, single frame. This is an identity reference for a later video, not an advertisement.
```

Then for the Soul ID: generate 20+ variations of the same character (angles, expressions, lighting, outfits) and train the identity so later renders stay consistent.

## 4. Wardrobe, background and policy safety

- Plain solid colors that contrast with the product (product is red -> creator wears grey/olive/cream; product is white -> creator wears a darker tone). No logos, slogans, patterns that shimmer, or branded sportswear.
- Coverage: crew or modest neckline, sleeves at least short-sleeve for close hand demos; no swimwear, lingerie, sheer fabric, or body-focused framing. This is both policy-safe and more believable for US/UK UGC.
- Hair out of the face for skincare, food, and demo-heavy ads.
- Background is the ad location, not a studio: bathroom mirror for skincare, kitchen counter for food/appliances, living-room couch for home/pet, bedroom mirror for fashion, desk for gadgets, hallway/park for footwear. See `references/wardrobe-by-category.md`.
- Nothing in the background that reads as a logo, screen with text, or another person's face.

## 5. Hand-off to Seedance 2.5

In the master prompt:

```text
@Image2 is the creator: [one-line identity summary from the attribute sheet]. Keep face, hair, skin tone, build and outfit identical in every frame. @Image2 does not define the room, lighting or camera.
```

And in the upload map: `@Image1 = product photo (cropped to product only)`, `@Image2 = identity portrait`, `@Image3 = wardrobe/body view (optional)`. Never upload a contact sheet or collage as an identity reference.

## 6. Inspection before use

Check: adult appearance, consistent face across generated images, natural eyes and teeth, five fingers if hands show, no text or watermark, no resemblance to a known public figure, outfit matches the ad, background neutral, no beauty-filter smoothing. A good portrait does not guarantee the video holds identity; still review the render.
