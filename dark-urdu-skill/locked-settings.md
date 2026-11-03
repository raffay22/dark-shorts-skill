# Urdu shorts — locked settings

**Call name:** `dark_urdu_skill`  
**Scope:** Urdu / Urdish topic shorts only (`data/urdu_topics.json`).

Also read: [visual-themes.md](visual-themes.md) · [faceless-route.md](faceless-route.md) when user says **faceless skill** / **2d skill**

## Faceless art engine (opt-in)

Default = Sumi Light Remotion. If user says `faceless skill` / `use faceless` / `2d skill`, load `faceless-shorts` (repo `faceless-shorts/` or `~/.cursor/skills/faceless-shorts/`) and keep **this file’s Urdu voice + RTL + music + brand locks**.

English channel uses a **different** skill (`dark_shorts_skill` / `dark_sumi_skill`). Do not mix locks.

Beyondsumi craft for Light/sketch:
- Light: `beyondsumi/skills/sumi/references/styles/sumi-light.md` + `beyondsumi/skills/sumi-svg/references/styles/sumi-light.md`
- Prefer sketch modes in visual-themes (not Dark void splash)

Project Remotion starter: `films/_urdu_starter/`

## Voice / narration (ElevenLabs only — no Voicebox)

| Setting | Value |
|--------|--------|
| Provider | ElevenLabs only |
| Voice ID | `o0kuOa7rSjdarn7nIRbL` |
| Model | `eleven_multilingual_v2` |
| Stability | `0.65` (soft, natural, emotional — not theatrical) |
| Similarity boost | `0.85` |
| Script field | `urdish_hook_script` |

Do not swap voice/model/stability without an explicit new user lock.  
Pass `stability=0.65`, `similarity_boost=0.85` into `generate_narration(...)`.

Canonical prefs: project `config/urdu_shorts_voice.json` and skill `urdu_shorts_voice.json`.

## Picture — Sumi Light / traditional sketch

| Setting | Value |
|--------|--------|
| Style family | **`sumi-light`** primary (warm parchment storytelling) |
| Ground | Warm washi / parchment `#F3EFE6` family |
| Look | Organic hand-drawn ink sketches, soft washes, emotional depth — **not** English dark-corporate minimalism |
| Preferred art modes | `japanese_sketch` · `wet_wash_light` · soft `human_ink_fill` |
| Avoid unless user asks | Sumi Dark void · Freezing Void neon · Gold Empire corporate geometry as default |
| Human figures | Readable sketch anatomy; Sumi paint OK |
| Art | Python multi-layer SVG with stable `id`s for GSAP; ≥4 layers |
| SVG reuse | Never reuse prior **Urdu** SVG files, art_mode, or metaphors |
| Aspect | 9:16 → 1080×1920 @ 24fps |

## Captions / titles — RTL Urdu (HARD)

| Setting | Value |
|--------|--------|
| Direction | **`rtl`** (Right-to-Left) |
| Position | Bottom (never center over art) |
| Font scale | ~`width * 0.048`–`0.052` (Nastaliq needs slightly careful line height) |
| Font stack | Noto Nastaliq Urdu → Jameel Noori Nastaleeq → Segoe UI → Tahoma |
| Timing | Dynamic, speech-aligned; stop when VO ends |
| End title | Silent; RTL if text is Urdu; theme accents |

Starter implements RTL in `Film.tsx` (`direction: 'rtl'`, `unicodeBidi: 'plaintext'`).

## GSAP + advanced motion graphics (HARD)

| Rule | Lock |
|------|------|
| Engine | **`gsap` required** |
| Remotion-safe | Paused timeline + **`seek(frame / fps)`** from `useCurrentFrame` |
| Character acting | ≥3 key states per scene (anticipation / action / settle) |
| Advanced MG | Kinetic RTL titles, prop/env motion, camera push/pan, ink/wash drift — not opacity-only stills |
| Record | `project.json` → `"motion": { "engine": "gsap", "advanced_motion_graphics": true }` |
| Banned | Frozen stills only · camera drift alone · shipping without GSAP |

## Background music (dialogue bed) — MANDATORY

| Rule | Lock |
|------|------|
| Source | `music-laybary/` |
| Loudness | `BED_PEAK=0.28` · `BED_DUCK=0.12` · Remotion `volume=0.85` · bed RMS ≤ **35% of VO** |
| Uniqueness | New bed file every Urdu topic |
| Character | Soft emotional underscore under narration (duck under voice) |

## End-of-video music — MANDATORY

| Rule | Lock |
|------|------|
| When | Only after VO ends |
| Duration | ~10.0s full segment |
| Loudness | `END_GAIN≤0.55` · end RMS ≤ **55% of VO** · peak ≤22000 |
| Uniqueness | New end file every Urdu topic (≠ this topic’s bed) |
| End title | Topic `title` on screen · **no voice** |

Canonical mixer: project `tools/mix_loudness_lock.py`.

## Brand identity

**The Shadow Protocol** logo top-right on every Urdu short (`brand/shadow-protocol-plate-220.png` / `BrandIdent`).

## Output

`output/urdu-topic-{topic_id:02d}-{slug}.mp4` — set `Rendered` only after the MP4 exists.
