# Seedance 2.5 failure modes -> cause -> fix

Diagnose one cause at a time. Change the one sentence that controls it. Re-render the draft at 480p. Do not add adjectives; add constraints.

## Hands and body

| Symptom | Likely cause | Fix (write this) |
|---|---|---|
| Extra / fused fingers at the product | Grip undefined, two hands doing different things, fast motion | "Right hand holds the bottle by its middle, four fingers wrapped, thumb on the pump. Left hand rests flat on the counter and does not move." |
| Hands pass through the product | Contact not described | "Fingertips press the lid; the lid visibly flexes and clicks. Real contact shadow under the product." |
| Third hand appears | Two subjects or hand-off | Remove the second person; never hand the product across; one action per beat |
| Arm bends wrong / torso twists | Camera and body orientation conflict | State body facing: "Creator faces the camera squarely; the counter is in front of her at waist height." |
| Face morphs mid-clip | Identity reference not bound, or large head turn | Bind `@Image2` with "keep face identical"; limit head turn to "glances to the product then back to lens" |
| Creator ages / changes hair | Lighting change or outfit conflict | Lock: "same hair, same outfit, same light direction for the entire clip" |

## Product

| Symptom | Likely cause | Fix |
|---|---|---|
| Product redesigned (new cap, different proportions) | Reference described vaguely | List identity locks: "matte white cylinder, flat black pump cap, grey label band in the lower third, roughly the height of her palm" |
| Product changes size between shots | Scale not anchored | "The bottle is about the length of her hand from wrist to fingertip and stays that size." |
| Two products appear | Plural wording or "set of" | "Exactly one product in frame at all times." |
| Label text garbles | Model cannot render text | "Label layout as in @Image1; readable text is not required." Composite the real label in post. |
| Product floats / no shadow | No surface contact stated | "The product rests on the counter with a soft contact shadow." |
| Wrong operation (pump pressed from the side) | Mechanism not explained | "Press the pump straight down once; a pea-sized amount lands on the fingertip." |
| Liquid defies gravity | Fluid action too complex | Simplify: single pour, single drop, cap-on hold; or cut to the result |

## Face, speech and sync

| Symptom | Likely cause | Fix |
|---|---|---|
| Mouth moves while silent | Dialogue not marked or too long | Put every spoken word in `{}`; cut words to 40-55 total; add "mouth closed during the demo beat" |
| Lips drift from audio | Face too small or turned | Medium close-up, "face toward camera, mouth unobstructed", speak before the hand action |
| Robotic / announcer voice | Voice undefined | "Voice: natural, unpolished, early-30s American, conversational, slightly breathy, recorded on the phone mic" |
| Accent flips mid-clip | Market not stated | "Consistent [American/British] English throughout" |
| Constant grin | "smiling", "happy" in prompt | Replace with cause-based reactions: "small nod", "short exhale", "brows relax" |
| Blinking absent / stare | Nothing | "Natural blinking, eyes move between the product and the lens" |

## Camera and look

| Symptom | Likely cause | Fix |
|---|---|---|
| Looks like a commercial | Cinematic adjectives, studio light | Remove them; add "smartphone front camera, mixed household light, mild grain, no beauty filter" |
| Camera orbits / drifts | No camera lock | "Camera is handheld at arm's length and stays roughly fixed; no orbit, no dolly, no zoom" |
| Slow motion creeps in | "satisfying" cues | "Real-time speed throughout, no slow motion" |
| Scene cuts too often | Over-long timeline with many beats | Keep 5 beats, "single take with at most one natural cut" |
| Background changes | Room undefined | Name 2-3 fixed background objects and the light source |
| Vertical framing cropped awkwardly | Ratio not stated or product too low | "9:16 vertical; product held at chest height, centered; keep the top 12% and bottom 20% free for UI and captions" |

## Audio

| Symptom | Likely cause | Fix |
|---|---|---|
| Music drowns the voice | Music undefined | "(no music)" or "(very quiet, under the voice)" |
| Random noises | Sfx unspecified | List the exact 2-4 sounds in `<>`, then "no other sound effects" |
| Dialogue clipped at the end | Timeline too full | Move the CTA to 17.0-19.5 and keep 19.5-20.0 silent |
| Echoey | Room not stated | "Small room, soft furnishings, slight natural reverb" |

## Text artifacts

| Symptom | Cause | Fix |
|---|---|---|
| Random captions appear | Model default | End prompt with "No subtitles, no on-screen text, no watermark." |
| Gibberish logos on clothes | Wardrobe undefined | "Plain [color] crew-neck tee, no prints" |
| Screen shows nonsense UI | Device screen in frame | "Screen shows a simple neutral interface without readable text" |

## When to stop fixing

Three drafts on the same beat without improvement means the action is too complex for the model. Simplify the beat (hold instead of operate, cut to the result, hands-only insert) or move that moment to a composited real product shot. A believable simple shot beats a flawed impressive one.
