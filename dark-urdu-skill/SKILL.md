---
name: dark-urdu-skill
description: >-
  Produce locked Urdu/Urdish shorts (default Sumi Light Remotion sketch + RTL, or
  Faceless 2D/3D code path when user says faceless skill). ElevenLabs Urdu voice,
  music-laybary, Shadow Protocol brand. Triggers: dark_urdu_skill, Urdu short,
  urdu_topics.json, urdish_hook_script. Faceless: load faceless-shorts (prefer
  flat 2D styles) while keeping Urdu voice + RTL captions.
disable-model-invocation: true
---

# dark_urdu_skill

Personal skill for **Urdu / Urdish storytelling shorts** (moral-emotional Sumi Light sketch). Works in **any** Cursor project when the user calls `dark_urdu_skill` or processes `data/urdu_topics.json`.

**Do not use this skill for English topics.** English uses `dark_shorts_skill` / `dark_sumi_skill`.

**Must read before generating:**
1. [locked-settings.md](locked-settings.md) — Urdu voice + RTL + **GSAP / motion graphics** + bed + end music locks
2. [visual-themes.md](visual-themes.md) — **Sumi Light / traditional sketch only** (warm parchment storytelling)
3. Project Remotion starter: `films/_urdu_starter/` (RTL captions + Urdu fonts + GSAP)
4. **If user says faceless / 2D skill:** also read project `faceless-shorts/SKILL.md` (or `~/.cursor/skills/faceless-shorts/SKILL.md`) + the chosen style’s `STYLE.md`

Do not use Voicebox.

## Art engine routing (Urdu)

| User signal | Engine |
|-------------|--------|
| Default / Sumi Light / Remotion | **Sumi Light Remotion** (`films/_urdu_starter`) |
| **`faceless skill`**, `faceless_shorts`, `use faceless`, `2d skill`, Inside Out / Stick Story / Paper Atlas / Deep Dive / Night File | **`faceless-shorts`** 2D/3D code pipeline |

When Faceless is selected:
1. Load **`faceless-shorts`** and follow its STYLE.md (prefer **Inside Out** / **Stick Story** / **Paper Atlas** for flat 2D unless user asks 3D).
2. Keep **Urdu channel locks**: ElevenLabs voice `o0kuOa7rSjdarn7nIRbL` · `eleven_multilingual_v2` · stability `0.65` · similarity `0.85` · **RTL** captions/titles (do **not** switch to Kokoro unless user asks).
3. Keep **music-laybary** loudness caps + Shadow Protocol brand; output `output/urdu-topic-*`.
4. Skill assets: repo `faceless-shorts/` (zip included).

## When invoked

1. Confirm project root.
2. Apply locked Urdu delivery — do **not** re-ask voice/caption/RTL/motion defaults.
3. Choose art engine (Sumi Light default vs Faceless if user asked).
4. **Inventory prior Urdu topics** (`films/urdu-topic-*/project.json`: `art_mode`, theme bg, `dialogue_bed`, `end_music`) — ban repeats.
5. **Analyze** `urdish_hook_script` → Sumi Light sketch **or** Faceless style → unused metaphors.
6. Sumi path: clone `films/_urdu_starter` → `films/urdu-topic-NN-slug/` + GSAP. Faceless path: follow `faceless-shorts` build/QA with RTL text.
7. Pick **new background bed** + **new end-of-video music** from `music-laybary/`.
8. Include **The Shadow Protocol** brand plate (top-right).
9. Produce the short; **stop for user review** before the next Urdu topic.

## Locked delivery (summary)

| Area | Lock |
|------|------|
| Source | `data/urdu_topics.json` → `urdish_hook_script` |
| Narration voice | ElevenLabs `o0kuOa7rSjdarn7nIRbL` · `eleven_multilingual_v2` · stability `0.65` · similarity `0.85` · soft natural pacing |
| Background music (bed) | **MANDATORY** · `music-laybary/` · `BED_PEAK=0.28` / `BED_DUCK=0.12` / Remotion `0.85` / bed ≤35% VO · **new file every topic** |
| End-of-video music | **MANDATORY** · after VO · ~10s · **`END_GAIN≤0.55`** + end ≤55% VO · **new file every topic** (≠ bed) |
| End title | Topic `title` when end music starts · **no spoken voice** · RTL if Urdu title text |
| Brand | **The Shadow Protocol** logo top-right |
| Visual style | **`sumi-light`** + traditional sketch (warm parchment) — **not** English Sumi Dark corporate void |
| Captions | **RTL** · bottom · Urdu font stack · stop at VO end |
| Motion | **GSAP + advanced motion graphics** every video |
| Output | `output/urdu-topic-{id:02d}-{slug}.mp4` |

## Hard uniqueness rules (every Urdu topic)

1. **New SVG art_mode** (vs previous Urdu topic).
2. **New background / theme palette**.
3. **New background bed track**.
4. **New end-of-video music track**.
5. **New metaphors** — never reuse prior Urdu SVG scenes.

## Hard visual + motion rules

- Primary look: warm washi/parchment, organic ink sketches, emotional storytelling depth.
- Banned defaults for Urdu: Sumi Dark void, icy neon Freezing Void, gold-empire corporate minimalism (unless user explicitly asks).
- Humans: readable Sumi sketch anatomy; ≥3 key states/scene driven by GSAP.
- **GSAP (HARD):** paused timeline + `seek(frame/fps)` in Remotion; kinetic RTL titles; character/env motion — not frozen stills or opacity-only.
- Record `project.json` → `"motion": { "engine": "gsap", "advanced_motion_graphics": true }`.

## Pipeline

1. Read topic from `data/urdu_topics.json`.
2. Inventory prior Urdu beds/ends/art_modes/themes; choose unused set.
3. Scaffold from `films/_urdu_starter` if needed.
4. Write `visual_plan` + `music_library` + `motion` into `project.json`.
5. Python SVG generator for that topic (stable `id`s for GSAP).
6. Narrate with locked Urdu ElevenLabs settings.
7. Mix bed+end via `tools/mix_loudness_lock.py`.
8. `Film.tsx` with RTL captions/titles + GSAP + BrandIdent.
9. Render → `output/urdu-topic-…`; set `status: Rendered` only after MP4 exists.
10. Ask user to review before the next Urdu topic.
11. Never paste API keys into chat/commits/topic JSON.

## Project layout

```text
data/urdu_topics.json
config/urdu_shorts_voice.json
music-laybary/
brand/shadow-protocol-plate-220.png
films/_urdu_starter/              # clone per Urdu topic
films/urdu-topic-NN-slug/
output/urdu-topic-NN-slug.mp4
```

## Companion skills

`sumi`, `sumi-svg`, `sumi-elevenlabs` — this skill **overrides** generic defaults for Urdu shorts.  
**`faceless-shorts`** — when user says **faceless skill** / **2d skill**; repo copy `faceless-shorts/`, personal `~/.cursor/skills/faceless-shorts/`.  
**Combo `sumi-dark-faceless`:** shared craft in parent [`../sumi-dark-faceless.md`](../sumi-dark-faceless.md) (or `~/.cursor/skills/dark-shorts-skill/sumi-dark-faceless.md`) + [faceless-route.md](faceless-route.md); keep Urdu voice/output locks.  
English channel: sibling skill `dark_shorts_skill` / `dark_sumi_skill` (repo root).
