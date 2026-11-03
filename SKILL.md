---
name: dark-shorts-skill
description: >-
  Produce locked English dark-psychology shorts (default Sumi Remotion path, or
  Faceless / combo paths) plus Cyber-Sumi **tech-style** knowledge guides.
  Sumi: Original / Light / Dark / Blossom + GSAP. Faceless: faceless-shorts.
  Combo: sumi-dark-faceless (**faceless combo** / **fd combo**). Tech guides:
  **tech style** / **tech-style** / **cyber-sumi** (see tech-style.md — one hero
  per beat, typewriter titles, B-roll rules). Triggers: dark_shorts_skill,
  dark_sumi_skill, tech style, faceless combo, fd combo, faceless skill,
  english_topics.json. Not for Urdu — use bundled dark-urdu-skill/.
disable-model-invocation: true
---

# dark_shorts_skill

Personal skill for **English dark-psychology / power-dynamics shorts** and **Cyber-Sumi tech knowledge guides**. Works in **any** Cursor project when the user calls `dark_shorts_skill` or alias **`dark_sumi_skill`** (or **`tech style`** for product/spec guides).

**Do not use this skill for Urdu topics.** Urdu is bundled at [`dark-urdu-skill/`](dark-urdu-skill/SKILL.md) — install that folder as `~/.cursor/skills/dark-urdu-skill/` and call **`dark_urdu_skill`**. (Urdu tech guides may still apply [`tech-style.md`](tech-style.md) visuals while keeping Urdu voice locks.)

**Must read before generating:**
1. [locked-settings.md](locked-settings.md) — voice + **GSAP / motion graphics** + bed + end music locks
2. [visual-themes.md](visual-themes.md) — **all Sumi styles**, palettes, art_mode rotation, zero repetition
3. Beyondsumi style guides when needed: `sumi-original.md` · `sumi-light.md` · `sumi-dark.md` (+ matching `sumi-svg/references/styles/…`) · Last Blossom / cherry blossom craft in visual-themes
4. **If user says faceless / 2D skill:** also read project `faceless-shorts/SKILL.md` (or `~/.cursor/skills/faceless-shorts/SKILL.md`) + the chosen style’s `STYLE.md`
5. **If user says `faceless combo` / `fd combo` / Sumi Dark + faceless / `sumi-dark-faceless`:** read [sumi-dark-faceless.md](sumi-dark-faceless.md)
6. **If user says `tech style` / `tech-style` / `cyber-sumi` / TechSpec / laptop-or-product knowledge guide:** read [tech-style.md](tech-style.md)

Do not use Voicebox.

## Art engine routing (English)

| User signal | Engine |
|-------------|--------|
| Default / Sumi / Remotion / `sumi-original` · `sumi-light` · `sumi-dark` · `sumi-blossom` | **Sumi Remotion** + GSAP |
| **`faceless skill`**, `use faceless`, `2d skill`, Inside Out / Stick Story / Paper Atlas / Deep Dive / Night File | **`faceless-shorts`** (base styles) |
| **`faceless combo`** · **`fd combo`** · `sumi-dark-faceless` · Sumi Dark + faceless | **Combo** — faceless engine + Sumi Dark aesthetic → [sumi-dark-faceless.md](sumi-dark-faceless.md) |
| **`tech style`** · **`tech-style`** · **`cyber-sumi`** · TechSpec / specs / buying guide | **Cyber-Sumi tech guide** → [tech-style.md](tech-style.md) (one hero/beat · kinetic text · B-roll) |

When Faceless (base or combo) is selected:
1. Load **`faceless-shorts`**. For **combo**, also apply Sumi Dark palette/craft from `sumi-dark-faceless.md` (seed: `films/urdu-topic-03-absolute-unpredictability/`).
2. Keep **English channel locks**: ElevenLabs voice `hgAoejldxKTXsFSP7qeO` · model `eleven_multilingual_v2` · stability `0.65` · similarity `0.85` (do **not** switch to Kokoro unless user asks).
3. Keep **music-laybary** (or disclosed Sound Gen) bed + end loudness caps + Shadow Protocol brand → `output/topic-*`.
4. Project assets: `faceless-shorts/` in the repo.

## When invoked

1. Confirm project root.
2. Apply locked English delivery — do **not** re-ask voice/caption/motion defaults.
3. Choose art engine (Sumi default vs Faceless if user asked).
4. **Inventory prior topics** (`project.json`: `style`, `art_mode`, theme bg, `dialogue_bed`, `end_music`) — ban repeats.
5. **Analyze the script** → Sumi styles **or** Faceless style → unused theme/metaphors.
6. Sumi path: wire **GSAP + advanced motion graphics** in Remotion. Faceless path: follow `faceless-shorts` build/QA.
7. Pick **new background bed** + **new end-of-video music** from `music-laybary/` (both must differ from all prior topics and from each other).
8. Include **The Shadow Protocol** brand plate (top-right) on every English short.
9. Produce the short; **stop for user review** before the next topic.

## Locked delivery (summary)

| Area | Lock |
|------|------|
| Narration voice | ElevenLabs `hgAoejldxKTXsFSP7qeO` · `eleven_multilingual_v2` · stability `0.65` · similarity `0.85` |
| Background music (bed) | **MANDATORY** every topic · `music-laybary/` · `BED_PEAK=0.28` / `BED_DUCK=0.12` / Remotion `0.85` / bed ≤35% VO · **music quieter than voice** · **new file every topic** |
| End-of-video music | **MANDATORY** every topic · after VO · ~10s · **`END_GAIN≤0.55`** + end ≤55% VO · **new file every topic** (≠ bed) |
| End title | Topic `title` on screen when end music starts · **no spoken voice** |
| Brand | **The Shadow Protocol** logo top-right · every English VO short |
| Visual style | Remotion: **`sumi-original` / `sumi-light` / `sumi-dark` / `sumi-blossom`**. Combo: **`sumi-dark-faceless`**. Record `style` in `project.json` |
| Motion | Remotion styles: **GSAP + advanced motion graphics**. Combo/faceless: faceless shot cuts + timed props (see combo doc) |
| Visual | Remotion: Python SVG · ≥4 layers. Combo: ink-void splash tableaux · **new metaphors every topic** |
| Captions | Bottom · font ≈ `width * 0.052` · theme accents · stop at VO end |
| Output | `output/topic-{id:02d}-{slug}.mp4` |

## Sumi styles (all first-class)

| `style` | Look | Notes |
|---------|------|--------|
| `sumi-original` | Painted Sumi-e stories · paper `#eeeadd` · ink `#242b29` · muted red `#a34537` | Mist/landscape depth; **no** Dark splash grammar |
| `sumi-light` | Mineral washi `#F3EFE6` | Wet washes; not a recoloured Dark void |
| `sumi-dark` | Ink void / splash · selective dark crimson | Remotion + GSAP; Beyondsumi Dark craft |
| `sumi-blossom` | **Last Blossom / Cherry Blossom Sumi** · mist paper `#E5E1D8` · ink `#141414` · blossom crimson `#B55441` | Soft mist + selective cherry blossoms/scarf accents; not plain Light recolour |
| **`sumi-dark-faceless`** | **Combo** — Sumi Dark ink void on **faceless** capture | Say **`faceless combo`** / **`fd combo`**; see [sumi-dark-faceless.md](sumi-dark-faceless.md) |
| **`tech-style`** | **Cyber-Sumi** charcoal / gold blueprint / cyan · product + B-roll knowledge guides | Say **`tech style`** / **`cyber-sumi`**; see [tech-style.md](tech-style.md) — **one image per beat**, typewriter titles, motion-graphic specs |

Do **not** fake a style by only swapping hex colours. Follow Beyondsumi craft for Original / Light / Dark Remotion; follow visual-themes Blossom lock for `sumi-blossom`; follow combo doc for `sumi-dark-faceless`; follow tech-style.md for product guides.

## Hard uniqueness rules (every topic)

1. **New SVG art_mode** (not same as previous topic).
2. **New background / theme palette**.
3. **New background bed track** (dialogue bed under narration).
4. **New end-of-video music track** (post-VO segment).
5. **New metaphors** — never reuse prior SVG scenes.

See locked-settings.md sections **GSAP / motion graphics**, **Background music**, and **End-of-video music**.

## Hard visual + motion rules

- Rotate styles and art modes including `sumi_original_painted` and `last_blossom_svg` (visual-themes.md).
- Zero reuse of prior topic SVG files or main metaphors.
- Banned: generic ghost, plain stick figure, **cartoon circle-head + blob body**, same maroon/crimson default every time.
- Humans: professional ~7–8 head proportions — Sumi paint OK, cartoon anatomy not OK.
- **GSAP + advanced motion graphics (HARD — all styles):** every English short must animate with **GSAP** timelines (Remotion-safe seek-by-frame) **and** advanced motion-graphics craft — articulated character motion, kinetic titles, prop/environment motion, camera pushes/pans, ink/mist/blossom drift. **Banned:** frozen still SVGs only · camera drift alone · opacity crossfade of two stills as the *only* motion · shipping without `gsap` wired in `Film.tsx`.
- Still generate **≥3 pose / key states per scene** as GSAP targets (anticipation / action / settle). Pose SVGs + GSAP tweens together; not poses without GSAP.
- Titles/captions follow **this** topic’s theme only.

## Pipeline

1. Read topic from `data/english_topics.json`.
2. Inventory prior beds/ends/art_modes/themes/styles; choose unused set.
3. Write `visual_plan` + `music_library` + `motion: { engine: "gsap", … }` into `project.json`.
4. Run a **Python SVG generator** for that topic only (layered groups with stable `id`s for GSAP).
5. Narrate with locked ElevenLabs settings.
6. Build bed+end splice → `dark-bed.mp3` using `tools/mix_loudness_lock.py` (bed ≤35% VO; end ≤0.55 / 55% VO).
7. Implement `Film.tsx` with **GSAP** motion + Remotion audio/captions + **BrandIdent**.
8. Opening + bottom captions + **silent** closing title when end music starts.
9. Render H.264 → `output/…`; set `status: Rendered` only after MP4 exists.
10. Ask user to review before starting the next topic.
11. Never paste API keys into chat/commits/topic JSON.

## Project layout

```text
data/english_topics.json
music-laybary/                    # background beds + end music library
brand/shadow-protocol-plate-220.png
config/english_shorts_voice.json
films/topic-NN-slug/
output/topic-NN-slug.mp4
beyondsumi/
```

## Companion skills

`sumi`, `sumi-svg`, `sumi-elevenlabs` — this skill **overrides** generic voice/sound/visual/motion defaults for English shorts.  
**`faceless-shorts`** — faceless / 2d / **sumi-dark-faceless** combo; repo `faceless-shorts/`, personal `~/.cursor/skills/faceless-shorts/`.  
Combo lock: [sumi-dark-faceless.md](sumi-dark-faceless.md) · [faceless-route.md](faceless-route.md).  
Tech / Cyber-Sumi guides: [tech-style.md](tech-style.md).
