---
name: seedance-2.5-prompting
description: Write production-grade Seedance 2.5 video prompts for realistic UGC ads. Covers the @Image/@Video/@Audio reference-binding syntax, {dialogue} / <sfx> / (music) / 【subtitle】 markers, duration and resolution facts, 9:16 vertical framing, phone-camera realism, lip-sync-friendly staging, product and identity continuity locks, policy-safe wording that avoids moderation blocks, and a diagnosis table for failed renders. Use whenever a prompt will be pasted into Seedance 2.5 (Higgsfield, Dreamina, BytePlus or API).
---

# Seedance 2.5 prompting for realistic UGC ads

Seedance 2.5 (ByteDance) is a reference-to-video model that renders video AND synchronized audio (voice, ambience, foley, music) in one pass. It is excellent at single-shot realism, lip-synced dialogue, and holding product/character identity when references are bound correctly. It fails when prompts are keyword piles, when actions are physically ambiguous, when references are not told what they control, or when wording trips the content filter.

Known capabilities (verify the current UI before promising anything; the host may expose fewer options):
- Duration: up to 30 seconds per generation on current hosts; a 20-second ad fits in one pass.
- Resolution tiers: 480p (draft), 720p, 1080p. Always draft at 480p, approve, then render 1080p.
- Aspect ratios include 9:16 vertical.
- References: up to about 30 images, 10 videos, 10 audio clips per job on current hosts. A UGC ad needs 2-4, not 30.
- Audio: generated in-pass. Dialogue in `{curly braces}` is lip-synced to the speaking character when the face is readable.
- Text rendering in-frame is unreliable. Never rely on generated captions or label text.

Reference files:
- `references/policy-safe-prompting.md` — what triggers blocks and the neutral phrasing to use instead, by product category.
- `references/failure-modes-and-fixes.md` — symptom -> cause -> one-line prompt fix.

---

## 1. Syntax cheat sheet

| Purpose | Syntax | Example |
|---|---|---|
| Bind an image | `@Image1`, `@Image2` ... followed by a sentence saying what it controls | `@Image1 is the exact product; preserve its shape, color, cap and label layout.` |
| Bind a video | `@Video1` + role | `@Video1 only guides camera handling and pacing, not the person or product.` |
| Bind audio | `@Audio1` + role | `@Audio1 is the creator's voice timbre for all dialogue.` |
| Spoken dialogue (lip-synced) | `{text}` or `"text"` | `She says {Okay, this is the part nobody shows you.}` |
| Sound effect | `<description>` | `<soft click of the cap closing>` |
| Music | `(description)` | `(no music)` or `(very quiet lo-fi bed, under the voice)` |
| Subtitles | `【text】` | Do NOT use for UGC ads; add captions in post. Instead write: `No subtitles, no on-screen text.` |
| Pick a subject inside a multi-subject image | `Define the woman in the grey hoodie in @Image2 as Creator.` | then refer to `Creator` consistently |
| Non-English speech | state the language | `says in British English {...}` |

Rules:
- Every reference you attach must be named in the prompt with its role. Unbound references cause the model to guess and blend.
- Put the product reference first (`@Image1`) and the creator second (`@Image2`) and keep that order in the upload.
- One speaking character per clip. Two faces talking over each other breaks sync.
- Dialogue inside braces must be the exact words. No stage directions inside the braces.
- Keep total spoken words for 20s at 40-55; the model needs mouth time plus pauses.

## 2. Prompt architecture (write in this order)

1. **Deliverable line** — `Realistic vertical 9:16 UGC-style phone video, 20 seconds, single continuous take with one natural cut allowed, for a US social ad.`
2. **Reference binding** — one sentence per `@` asset stating exactly what it controls and what it must NOT control (a portrait must not define the room; a product photo must not define the lighting).
3. **Scene and light** — real room matched to the product category, time of day, one key light source with direction, ordinary background clutter, phone-camera exposure, mild grain, natural skin texture, no beauty smoothing.
4. **Camera grammar** — selfie at arm's length / phone propped on a shelf / handheld close insert / mirror / fixed POV. State lens distance, height, and the ONE motivated move (a short push-in as the hand presents the product, or a small reframe when the creator leans in).
5. **Performance and timeline** — timed beats (0-2 / 2-6 / 6-13 / 13-17 / 17-20) each with: action, hand used, product orientation, `{dialogue}`, and the cause -> visible reaction.
6. **Audio** — voice description (age, accent, pace, warmth), room tone, 2-4 specific `<sfx>`, `(music)` decision.
7. **Continuity locks** — same creator face/hair/outfit, same product variant, same room, same light direction, same hand holding the product, product never changes scale.
8. **Avoid list** — only failure modes relevant to this prompt (extra fingers, product morphing, floating object, duplicate product, text artifacts, camera orbit, slow motion, beauty filter, announcer voice).
9. **Text rule** — `No on-screen text, no subtitles, no watermarks, no logos other than the product's own label exactly as in @Image1.`

The prompt must stand alone. Never write "as described above".

## 3. Phone-camera realism controls

Use concrete cues, not adjectives:
- "shot on a recent smartphone front camera, slight wide-angle distortion at arm's length, autofocus breathes once when the product comes close"
- "soft daylight from a window camera-left, warm practical lamp in the background, slight mixed white balance"
- "visible skin pores and a few stray hairs, no retouching, natural under-eye shading"
- "micro hand-shake, not stabilized gimbal motion"
- "ordinary background: a towel on the rack, a charger cable, a half-open drawer"
- "fabric wrinkles move with the body; the bottle has a real contact shadow on the counter"

Avoid: "8K, hyperreal, ultra detailed, cinematic, masterpiece, volumetric lighting, bokeh, dramatic". These push the model toward commercial polish, which reads as fake UGC.

## 4. Staging for clean lip-sync and hands

- Medium close-up or close-up, face toward camera, mouth unobstructed, even light on the face.
- Have the creator finish speaking before the big hand action, or speak while the hands are still. Talking + operating a complex mechanism at once produces mouth drift and finger errors.
- Product handled with ONE clearly described grip: "right hand wraps the bottle, thumb on the pump, left hand open palm-up to receive".
- Never: object hand-offs between two people, spinning the product, throwing/catching, rapid repeated taps, fast whip pans.
- Give each action a start and end state: "cap is on -> cap is off and held in the left hand".

## 5. Timing math

Local beat durations must sum exactly to 20.0 seconds. Spoken pace for natural conversational US/UK English is about 2.3-2.8 words per second including pauses; 20 seconds of speech with breathing room is 40-55 words. If the script is longer, cut words, not pauses. Leave the last 0.5 seconds silent on a steady product frame for the end card.

## 6. Draft -> final workflow

1. Draft 480p, 9:16, 20s, audio on. Review at 100%: hands at every product contact, face at the start/middle/end, product label, mouth sync on the first and last line, sound glitches.
2. Diagnose ONE cause per failure (see `references/failure-modes-and-fixes.md`). Tighten the specific sentence. Do not add ten realism adjectives.
3. Only after the draft passes, render 1080p with the identical prompt and references. Do not change wording between draft and final.
4. If the host cannot do 20s in one pass, split 0-10 and 10-20 with the same locks and an explicit matching end/start frame description, then join in edit.

## 7. Skeleton

```text
Realistic vertical 9:16 UGC-style phone video, 20 seconds, [US/UK] social ad, single take with one natural cut allowed.

REFERENCES
@Image1 is the exact product: [variant, color, cap/lid, label position]. Preserve its silhouette, proportions relative to the hand, colors, and label layout in every frame. Do not redesign it, do not add parts, do not duplicate it.
@Image2 is the creator: [age presentation, hair, skin tone, build, outfit]. Keep face, hair and outfit identical in every frame. @Image2 does not define the room or lighting.
[Optional] @Video1 guides only handheld camera feel and pacing, not the person, product or words.

SCENE
[Room matched to product], [time of day], [one key light + direction], ordinary lived-in background: [2-3 specific objects]. Shot on a smartphone front camera at arm's length, slight wide-angle look, natural exposure, visible skin texture, no beauty filter, mild sensor grain.

TIMELINE
0.0-2.0s: [mid-action opening; product or problem visible]. Creator glances to lens and says {hook, 4-7 words}. [cause -> visible micro-reaction].
2.0-6.0s: [situation + product placement]. {line}. [reaction].
6.0-13.0s: [ONE demonstration with exact grip, start state -> end state]. {line with a natural pause}. <sfx>.
13.0-17.0s: [observable payoff the camera can actually see]. {line}. [relaxed brow / small nod / short exhale].
17.0-20.0s: Creator holds the product steady at chest height, label toward camera. {CTA, 4-7 words}. Half-second hold, silent.

AUDIO
Voice: [age, gender, accent, pace, warmth], recorded on the phone mic, slight room reverb. Room tone: [specific]. <sfx 1>, <sfx 2>. (no music) or (very quiet bed under the voice).

CONTINUITY
Same creator, outfit, hair, room, light direction, product variant and scale throughout. Product stays in the [right/left] hand for the whole demo.

AVOID
Extra or fused fingers, duplicate product, product changing size or color, floating objects, mouth moving while silent, camera orbit, slow motion, beauty smoothing, announcer voice, studio lighting. No on-screen text, no subtitles, no watermarks, no logos other than the product's own label as in @Image1.
```
