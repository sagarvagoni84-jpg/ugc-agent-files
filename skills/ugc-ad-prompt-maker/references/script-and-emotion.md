# Script, dialogue, emotion and action direction for a 20-second UGC ad

AI video looks fake for three reasons: the words sound written, the face emotes without a reason, and the hands do things no human would do while talking. This file fixes all three.

## 1. The 20-second edit map (must sum to 20.0)

| Beat | Time | Visual job | Words | Emotion job |
|---|---|---|---|---|
| Hook | 0.0-2.0 | mid-action, product/problem in frame 1 | 4-7 | recognition / mild tension |
| Bridge | 2.0-6.0 | situation + product clearly placed in hand or on surface | 8-12 | curiosity, focus |
| Demo | 6.0-13.0 | ONE correct action, start state -> end state; optional insert | 10-16 with a pause | concentration, then first small relief |
| Payoff | 13.0-17.0 | the visible result or detail | 8-12 | quiet satisfaction / confidence |
| CTA | 17.0-20.0 | product steady, label to camera, last 0.5s silent | 4-7 | warm, low-pressure |

Total 40-55 words. Count them. If over, cut adjectives first, then whole sentences. Never cut pauses.

## 2. Dialogue that sounds like a person

- Write how people talk, not how brands write. Fragments, contractions, one "okay" or "honestly" max.
- Say what is happening, not what the brand promises: "That's one pass" beats "Removes pet hair effortlessly".
- Use the buyer's review language from product-analysis.
- One pause per beat, marked with "..." or `[beat]` in the storyboard; in the Seedance prompt the pause is a period and a short silent action.
- Match the words to the visual at that exact second. Never describe a feature the camera has not shown yet.
- The creator is a demonstrator: "I tried", "watch", "look at this" are fine; "I've used it for months", "it cured my", "my customers" are not.
- US default wording; UK wording on request (see product-analysis section 5).
- CTA options: "Link's below if you want it." / "Grab it at the link." / "Have a look, link below." / "Check the details at the link." / "Shop now" only when the page supports a direct purchase. Never invent discounts or urgency.

Bad: "This revolutionary tool removes 99% of pet hair in seconds and will change your cleaning routine forever!"
Good: "Okay... that's one pass. [beat] It all just... sits on the bristles."

## 3. Emotion with a cause (the core realism rule)

Never write an emotion word alone. Always: **trigger -> micro-reaction -> duration**.

| Moment | Trigger | Visible micro-reaction (write this) |
|---|---|---|
| Recognition (hook) | sees the problem | eyes narrow slightly, small exhale through the nose, tiny head tilt |
| Curiosity (bridge) | picks up the product | eyes drop to the product, brows lift a few millimeters, lips part |
| Focus (demo) | starts the action | mouth closes, gaze locked on the contact point, breathing slows |
| First relief (end of demo) | sees it working | brows relax, a short "huh" or quiet laugh through the nose, glance to lens for half a second |
| Satisfaction (payoff) | result is clear | small nod, one side of the mouth lifts, shoulders drop |
| Warmth (CTA) | talks to viewer | soft eye contact, relaxed smile that does not show full teeth, slight shrug |

Rules:
- Reactions last 0.5-1.5 seconds then return to neutral. Faces that stay in one expression look rendered.
- Blink naturally; look away and back. Constant lens contact is unnatural; constant looking at the product is also unnatural. Alternate.
- No surprise face, no gasp, no jaw drop, no wide-eyed grin for a lint roller.
- The "UGC imperfections" that sell: a half-laugh at your own line, a quick glance off-frame, re-gripping the product, pushing hair back once, a small "um".

## 4. Action design for hands

- One hand does the thing; the other hand is parked (on the counter, holding the phone, or resting on the thigh). Say where it is.
- Each action has a start state and end state. "Cap on -> cap off and held in the left hand."
- Speak BEFORE or AFTER a precise hand action, not during. Simple actions (hold, tilt, point) can overlap speech; mechanisms (pump, zip, fold, lid) should not.
- Product orientation: label toward camera at hook and CTA; functional side toward camera during demo.
- Scale anchor: relate the product to the hand ("about palm height").
- Allowed verbs: pick up, hold, tilt, turn once, open, close, press once, pump once, pour, dab, smooth, stroke, fold, clip, lace, zip, place down, point at.
- Banned verbs: toss, spin, juggle, flip, shake vigorously, slam, twirl, hand to another person, wave around.

## 5. Camera logic (pick one per beat, keep it consistent)

- **Selfie**: phone in the non-demo hand at arm's length, eye height; the demo is one-handed. Works for talking hook, bridge, CTA.
- **Propped phone**: on a shelf/stack of books at chest height; both hands free; creator leans in. Best for demos.
- **Handheld insert**: close on the product/hands, 1-3 seconds, usually for the payoff detail.
- **Mirror**: for fashion/beauty; the phone is visible in the reflection, gaze follows the mirror.
- **POV**: camera is the creator's eyes; hands enter from the bottom of frame; no face.

Do not switch from selfie to propped mid-sentence without a cut. One cut max in 20 seconds unless the style is explicitly jump-cut.

## 6. Light and room

Name one key light and its direction, one background practical, and 2-3 lived-in objects. Keep them constant. Daylight from camera-left window + warm lamp behind = the standard UGC look. Night ads: lamp + phone screen glow, grainier.

## 7. Captions plan (post-production, not in the render)

- 3-7 words per caption, mirror the dialogue, sentence case.
- Bold white sans-serif, 75-85% opacity black box, centered, lower 70-78% of the frame; move it if a hand or product is there.
- First caption appears at 0.0s so sound-off viewers get the hook.
- No emojis in captions for US/UK ads unless the brand voice is playful.
- Write the caption list with timestamps in the deliverable.

## 8. Storyboard beat format (use this in the output)

```text
BEAT 1 — 0.0-2.0s — HOOK
Camera: selfie, arm's length, eye height, slight downward tilt
Action: right hand already stroking the tool across the grey couch cushion; hair gathers on the bristles
Dialogue (on camera): {Okay... watch this one pass.}
Emotion: trigger = hair visibly collecting -> eyes narrow slightly, small nose exhale
Product: tool in right hand, bristle side toward camera, about hand-length
Sound: <soft rubber-on-fabric drag>, room tone
Caption (post): "watch this one pass"
```
