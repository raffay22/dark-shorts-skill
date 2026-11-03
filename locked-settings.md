# English dark shorts — locked settings

**Call name:** `dark_shorts_skill`  
**Scope:** English topic shorts only.

Also read: [visual-themes.md](visual-themes.md) · [faceless-route.md](faceless-route.md) · [sumi-dark-faceless.md](sumi-dark-faceless.md) for combo

## Faceless art engine (opt-in)

Default = Sumi Remotion. If user says `faceless skill` / `use faceless` / `2d skill`, load `faceless-shorts` (repo `faceless-shorts/` or `~/.cursor/skills/faceless-shorts/`) and keep **this file’s voice + music + brand locks**.

### Combo style: `sumi-dark-faceless` (HARD when requested)

If user asks **`faceless combo`** / **`fd combo`** / Sumi Dark + faceless / `sumi-dark-faceless` / dark faceless combo: apply [sumi-dark-faceless.md](sumi-dark-faceless.md) — faceless capture + Sumi Dark ink void (not warm parchment, not Remotion GSAP). Record `style: "sumi-dark-faceless"` in `project.json`.

Beyondsumi style specs (read when generating that style):
- Original (painted stories): `beyondsumi/skills/sumi/references/styles/sumi-original.md` + `beyondsumi/skills/sumi-svg/references/styles/sumi-original.md`
- Light: `beyondsumi/skills/sumi/references/styles/sumi-light.md` + `beyondsumi/skills/sumi-svg/references/styles/sumi-light.md`
- Dark: `beyondsumi/skills/sumi/references/styles/sumi-dark.md` + `beyondsumi/skills/sumi-svg/references/styles/sumi-dark.md`
- Blossom / Last Blossom (cherry): [visual-themes.md](visual-themes.md) Sumi Blossom lock (mist paper + crimson blossom accents)

## Voice / narration (ElevenLabs only — no Voicebox)

| Setting | Value |
|--------|--------|
| Provider | ElevenLabs only |
| Voice ID | `hgAoejldxKTXsFSP7qeO` |
| Model | `eleven_multilingual_v2` |
| Stability | `0.65` |
| Similarity boost | `0.85` |

Do not swap voice/model/stability without an explicit new user lock.  
Pass `stability=0.65`, `similarity_boost=0.85` into `generate_narration(...)`.

## Picture — Sumi styles (all first-class)

| Setting | Value |
|--------|--------|
| Style family | **`sumi-original` / `sumi-light` / `sumi-dark` / `sumi-blossom`** — record `style` in `project.json`; follow user request; rotate when unspecified |
| **Sumi Original** | Painted Sumi-e stories · paper `#eeeadd` · ink `#242b29` · muted red `#a34537` · olive/mist landscape depth · quiet negative space · **no** Dark splash grammar (see Original guide) |
| **Sumi Light** | Warm washi `#F3EFE6` · mineral washes · readable brush humans — **not** a recoloured Dark void |
| **Sumi Dark** | Ink void / splash masses · selective dark crimson · negative space · cinematic camera |
| **Sumi Blossom** | **Last Blossom / Cherry Blossom Sumi** · mist paper `#E5E1D8` · ink `#141414` · blossom crimson `#B55441` · soft mist + selective cherry blossoms — not Light/Dark recolour |
| **Human figures (HARD)** | **Professional body construction** — ~7–8 head proportions, neck, shoulders, torso, pelvis, articulated arms/legs, planted feet, structured face (brow/eyes/nose/mouth). **Banned:** cartoon circle-head + blob robe, stick limbs, emoji faces. Sumi-e paint language OK; anatomy must read as a real human silhouette. |
| Art | **Python-generated** multi-layer SVG with **stable element `id`s** for GSAP targets; rotate modes including `sumi_original_painted` + `last_blossom_svg` |
| Themes | Category A/B/C **or** Light mineral **or** Blossom mist — **new primary background every topic** (not last 2–3) |
| SVG reuse | **Never** reuse SVG files, art_mode (vs previous topic), or metaphors |
| Aspect | 9:16 → 1080×1920 @ 24fps |

## GSAP + advanced motion graphics (HARD — every style)

**Applies to Original, Light, Dark, and Blossom.** Do not ship a frozen or “camera-only” short.

| Rule | Lock |
|------|------|
| Engine | **`gsap` required** in the film package and wired in `Film.tsx` |
| Remotion-safe pattern | Build a **paused** GSAP timeline (or per-scene timelines) and **`timeline.seek(frame / fps)`** (or equivalent) from `useCurrentFrame` — never rely on wall-clock `gsap.to` alone during render |
| Character acting | Humans **must move** — limbs, weight shift, head/gaze, breath, hands. Drive ≥3 key states per scene (anticipation / action / settle) with GSAP (pose SVGs and/or transform targets) |
| Advanced motion graphics | Use **beyond** simple opacity crossfades: kinetic word-by-word titles, prop/environment motion, camera push/pan/parallax, ink/mist/blossom/spotlight drift, staggered layer reveals, path/offset where it serves the beat |
| Style-specific MG | Original = painted cloth/mist/figure acting · Light = mineral wash / brush mass motion · Dark = splash/void + cinematic camera · Blossom = petal/mist drift + soft figure acting |
| Record | `project.json` → `"motion": { "engine": "gsap", "advanced_motion_graphics": true }` |
| Banned | Frozen still SVGs only · camera drift alone · opacity crossfade of stills as the **only** motion · shipping without GSAP · skipping GSAP because style is Original/Light/Blossom |

Pose multi-SVG layers remain useful as GSAP targets; they do **not** replace GSAP.

## Captions

| Setting | Value |
|--------|--------|
| Position | Bottom (never center) |
| Font scale | ~`width * 0.052` |
| Timing | Dynamic, speech-aligned |
| Color | Theme-accent treatment from chosen palette |
| End segment | Captions stop when VO ends |

---

## Background music (dialogue bed) — MANDATORY

**Music is required on every topic.** Never ship a video with silent/missing bed.

This is the **background music under narration** (user may call it “background voice”).

| Rule | Lock |
|------|------|
| Required | **MUST** be present and audible under VO (not silent, not blasting) |
| Source | `music-laybary/` library tracks (real music beds — not silent pads, not near-inaudible SFX alone) |
| Where it plays | From video start → VO end (under narration) |
| **Loudness (HARD CAP)** | `BED_PEAK = 0.28` · `BED_DUCK = 0.12` · Remotion `volume = 0.85` · bed RMS ≤ **35% of VO** — music quieter than video voice |
| Per-topic uniqueness | **Every new topic MUST use a different dialogue-bed file** than every previous topic |
| Do not | Skip bed · reuse last topic’s bed · leave bed silent · raise bed above these caps · use only a tiny SFX as the whole bed |

Inventory prior `films/topic-*/project.json` → `music_library.dialogue_bed` before choosing.

## End-of-video music — MANDATORY

**End music is required on every topic.** Never ship silent post-VO padding.

This is the **post-VO end music** (user may call it “end of video voice”). **Not** narration — no spoken end-title VO.

| Rule | Lock |
|------|------|
| Required | **MUST** be present and clearly musical for the full end segment |
| Source | `music-laybary/` (different file from this topic’s bed). Prefer energetic music beds/braams — not quiet heartbeats/gongs alone unless layered into a full 10s musical end. Fallback only if library empty: ElevenLabs Sound Gen `eleven_text_to_sound_v3` (disclose) |
| When it starts | **Only after VO ends** (~0.1s gap ok) |
| Duration | Full post-VO segment (locked default **10.0s**) |
| **Loudness (HARD CAP)** | `END_GAIN = 0.55` absolute max · end RMS ≤ **55% of VO** · peak ceiling `22000` · always quieter than VO · headphone-safe |
| Energy | Must fill the **entire** end segment at that capped level; if the clip dies early, loop/sustain the hot portion |
| Per-topic uniqueness | **Every new topic MUST use a different end-music file** than every previous end track **and** different from this topic’s bed |
| End title | When end music starts: show topic `title` on screen (opening-title style). **No voice / no narration** on the end title |
| Do not | Silent padding · missing end music · end louder than VO · raise above `0.72` · “match VO” without the `0.72` cap · alter VO/bed when only swapping end · reuse last topic’s end track |

**Canonical constants:** project `tools/mix_loudness_lock.py` — copy into every topic mixer. Do not raise without a new user lock.

Inventory prior `films/topic-*/project.json` → `music_library.end_music` before choosing.

## Music splice (required shape)

```text
[ducked library bed  0 → VO_end]  +  [end music @ ≤0.55  VO_end → VO_end+~10s]
        →  public/dark-bed.mp3 (or .wav)
```

Record both filenames in `project.json` → `music_library`:

```json
"music_library": {
  "folder": "music-laybary",
  "dialogue_bed": "<unique-bed-file>",
  "end_music": "<unique-end-file>",
  "end_seconds": 10.0,
  "bed_peak": 0.28,
  "bed_duck": 0.12,
  "bed_vs_vo_max": 0.35,
  "end_gain": 0.55,
  "duck_under_voice": true
}
```

---

## End title

| Setting | Value |
|--------|--------|
| When | End music starts |
| Text | Topic `title` from JSON |
| Style | Opening-title motion + **theme** colors |
| Voice | **None** (silent title card) |

## Output

`output/topic-{topic_id:02d}-{slug}.mp4` — set `Rendered` only after the MP4 exists.
