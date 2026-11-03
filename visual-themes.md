# Visual themes + SVG creativity (dark_shorts_skill)

## Beyondsumi + Blossom styles (pick one per topic)

| `project.json` `style` | Ground | Craft source |
|------------------------|--------|--------------|
| `sumi-original` | Painted Sumi-e narrative paper | `beyondsumi/.../styles/sumi-original.md` + `sumi-svg/.../sumi-original.md` |
| `sumi-dark` | Ink void / splash | `beyondsumi/.../styles/sumi-dark.md` |
| `sumi-light` | Warm washi + mineral washes | `beyondsumi/.../styles/sumi-light.md` + `sumi-svg/.../sumi-light.md` |
| `sumi-blossom` | **Last Blossom / Cherry Blossom Sumi** mist paper | This file (Blossom lock) + prior `last_blossom_svg` films |
| **`sumi-dark-faceless`** | Ink void on **faceless** canvas (combo) | [sumi-dark-faceless.md](sumi-dark-faceless.md) · seed `films/urdu-topic-03-absolute-unpredictability/` |
| **`tech-style`** | Cyber-Sumi charcoal / gold / cyan knowledge guides | [tech-style.md](tech-style.md) · seed `films/techspec-01-laptop-college-major/` |

**Tech-style lock (Cyber-Sumi):** product/spec buying guides — **one hero image per beat** (never 2×2 grids), typewriter + word-reveal titles, animated RAM/OS/checklist cards, Pexels/Pixabay B-roll with `SOURCES.md`. Full rules: [tech-style.md](tech-style.md).

**Sumi Original lock:** traditional Japanese Sumi-e **painted stories** — expressive economical ink forms, soft translucent tonal washes, paper texture `#eeeadd`, dark ink `#242b29`, muted red `#a34537`, olive/green-grey landscape, mist, layered mountain depth, quiet negative space. Animate painted people/cloth/expression/environment with **GSAP** — **no** Dark splash grammar. Captions: soft paper / translucent ink-tone backing. Do **not** fake Original with Light mineral candy or Dark void splash.

**Sumi Light lock:** paper `#F3EFE6`, mineral accents, wet brush masses. Captions: dark ink on soft washi backing. **GSAP** drives wash/figure/title motion.

**Sumi Dark lock (Remotion):** ink void / splash masses, selective dark crimson `#7A1622`, cinematic camera. **GSAP** drives splash, figure acting, and camera-led beats.

**Sumi Dark + Faceless combo lock (`sumi-dark-faceless`):** same Dark palette and splash-built silhouettes, but built in the **faceless-shorts** engine (capture/mix), not Remotion SVG/GSAP. Story tableaux per line; void `#0B0B0C`; selective crimson only. Full rules: [sumi-dark-faceless.md](sumi-dark-faceless.md).

**Sumi Blossom lock (Last Blossom / Cherry):** mist paper `#E5E1D8`, ink `#141414`, blossom crimson `#B55441` (scarf/petals/accents). Soft mist depth + selective cherry blossoms — **not** a recolour of Light or Dark. Captions: dark ink on soft mist backing. **GSAP** drifts petals/mist and figures. Record `style: "sumi-blossom"` and often `art_mode: "last_blossom_svg"`.

Rotate `style` when the user asks (Original / Light / Dark / Blossom) or when rotating the series.

### Motion

- Remotion styles (`sumi-original` / `light` / `dark` / `blossom`): **GSAP + advanced motion graphics** (see locked-settings.md).
- Combo `sumi-dark-faceless`: faceless cut timing + prop/silhouette acting (see combo doc) — GSAP Remotion not required.

## Theme palette catalog

Pick **one primary theme per video**, then optionally rotate **related** themes across scenes so each beat feels distinct. Never default every short to the same black/red silhouette look.

### Sumi Light mineral themes (use when `style: sumi-light`)

| Theme | Paper / ground | Accent | Text treatment |
|-------|----------------|--------|----------------|
| Washi Cinnabar | Warm Washi `#F3EFE6` | Cinnabar `#D3381C` | Ink titles + red key words |
| Washi Indigo | Warm Washi `#F3EFE6` | Deep Indigo `#1D3B58` | Cool ink captions |
| Washi Peony | Warm Washi `#F3EFE6` | Peony Magenta `#C94A6A` | Soft romance / affection traps |
| Washi Jade | Warm Washi `#F3EFE6` | Jade Verdigris `#2E6F5E` | Escape / clarity beats |
| Washi Gold | Warm Washi `#F3EFE6` | Imperial Gold `#C89B3C` | Status / bait / false gifts |

### Category A — Silence / Isolation / Cold Posture

| Theme | Background | Accent | Text treatment |
|-------|------------|--------|----------------|
| Freezing Void | Deep Obsidian `#08090C` | Ice Blue `#00E5FF` | Clean cyan glow, cold crisp |
| Toxic Fog | Dark Slate `#12151C` | Poison Mint `#00FF9D` | Neon mint highlight, sharp sans |
| Shadow Mirror | Pitch Black `#000000` | Metallic Silver `#E0E6ED` | Ultra-bold white + grey shadow |
| Fading Signal | Dark Charcoal `#181818` | Static Violet `#A855F7` | Soft lavender glow, cinematic |

### Category B — Anger / Betrayal / Power

| Theme | Background | Accent | Text treatment |
|-------|------------|--------|----------------|
| Crimson Rage | Jet Black `#000000` | Blood Red `#FF0033` | Heavy red highlight, high contrast |
| Burnt Empire | Smoky Dark Grey `#141113` | Ember Orange `#FF5500` | Fiery orange + dark stroke |
| Crown Betrayal | Deep Velvet Maroon `#1A0A0F` | Royal Crimson `#E60049` | Bold gold-red outline |
| Venomous Control | Obsidian `#0D0D0D` | Acid Lime `#84CC16` | Bright lime kinetic text |

### Category C — Wealth / Success / Ambition

| Theme | Background | Accent | Text treatment |
|-------|------------|--------|----------------|
| Gold Empire | Rich Charcoal `#0F0F10` | Dull Metallic Gold `#FFD700` | Elegant gold fill, subtle shine |
| Emerald Reserve | Deep Midnight Green `#05140E` | Bright Emerald `#10B981` | Sharp emerald highlight |
| Digital Monopoly | Dark Cyber Blue `#0A0F1D` | Electric Cyan `#06B6D4` | Tech font + blue outline |
| High-Roller Vault | Matte Black `#121212` | Platinum Silver `#F1F5F9` | Crisp white + silver badge on key words |

---

## HARD RULE — every topic must be unique (no sameness)

Before generating a topic, inventory prior `films/topic-*/project.json` and **refuse** any of these repeats:

1. **Background / primary theme** — do **not** reuse the last topic’s primary `theme_colors.bg` or primary theme name. Prefer a palette unused in the last 2–3 topics.
2. **Dialogue bed track** — different file than every prior topic bed.
3. **End music track** — different file than every prior topic end (and different from *this* topic’s bed).
4. **SVG art mode** — rotate; do **not** reuse the same mode as the previous topic (see modes below).
5. **Metaphors** — new nouns/actions only; never copy prior SVG scenes.

Record in `project.json` → `visual_plan`:
`primary_theme`, `art_mode`, `background_note`, `dialogue_bed`, `end_music`, `prior_avoid`.

### SVG art modes (rotate across the series)

Borrow craft from Beyondsumi `sumi-svg` (Original / Light / Dark) but **vary the drawing language** each topic:

| Mode ID | Look | When to use |
|---------|------|-------------|
| `human_ink_fill` | Full Sumi humans, filled cloak/skin masses | People-heavy scripts (alternate — not every topic) |
| `japanese_sketch` | Dry brush, hatching, incomplete contours, sketch humans — on **dark void** (Dark) or **warm washi** (Light) | Observation / envy / affection traps |
| `geometric_shapes` | Circles, shards, grids, sigils, abstract machines — minimal or no humans | Systems, traps, choice illusions |
| `splash_sumi_dark` | Broad ink splash masses, negative space, Beyondsumi Dark energy | Horror / impact beats |
| `wet_wash_light` | Full **Sumi Light** wet washes on warm washi (pooling mineral pigment) | Soft menace / Light documentary beats |
| `sumi_original_painted` | **Sumi Original** painted Sumi-e: misty mountains, tonal washes, muted red accent, narrative figures | Storytelling / patience / landscape emotion |
| `last_blossom_svg` | **Sumi Blossom** mist paper + cherry blossom crimson accents | Soft menace / longing / traps under blossom mist |
| `line_architecture` | Architectural frames, doors, rooms, sightlines | Social rooms, absence, status |
| `cutout_mask_shapes` | Masked cutouts + geometric shapes on Dark grounds | Systems / false vulnerability / abstract power |

**Rule of thumb:** consecutive topics must use **different** `art_mode`. Humans are allowed often, but not as the only forever style — interleave sketch / shapes / splash / blossom.

### Background variety

- Change paper/void treatment every video: solid void ≠ cracked ice ≠ velvet drape ≠ washi grain ≠ cyber grid ≠ scorched earth.
- Title/caption colors must follow the **new** theme (not last video’s crimson/maroon by default).

### Music variety (`music-laybary/`) — background bed + end-of-video music

Full lock lives in [locked-settings.md](locked-settings.md). Summary agents must obey:

| Segment | User name | Must change every topic? | Notes |
|---------|-----------|--------------------------|-------|
| Dialogue bed under VO | “background voice / background music” | **YES — new file every topic** | Duck under narration; VO span only |
| Post-VO end track | “end of video voice / end music” | **YES — new file every topic** | ≠ this topic’s bed; full ~10s @ ~0.72; silent end title (no speech) |

- Prefer tracks never used; if library exhausted, reuse only a track that was used in a *different role* (bed vs end) **and** pair with a never-used partner.
- End segment must stay energetic for full ~10s (loop/sustain short hits if needed).
- Never alter VO or the bed stem when only regenerating end music.

---

## CRITICAL VISUAL CREATIVITY RULE

### 1. Zero visual repetition

- **NEVER** repeat the same main SVG concept, character, or object metaphor across videos.
- Do **not** default to generic ghosts, static silhouettes, or simple circles-as-hero.
- Banned: `generic ghost`, `plain stick figure`, copying prior topic human pose sets.

### 2. Dynamic script analysis

- Extract **2–3 core nouns/actions** from the script.
- Invent a **brand-new** metaphor set; write them into `visual_plan.scene_metaphors`.

### 3. Rich SVG construction (Python)

**≥4 layers** per scene. New Python generator per topic (never copy prior SVG files).

| Layer | Role |
|-------|------|
| 1 | Unique background texture for *this* art_mode |
| 2 | Secondary atmosphere (drips / hatch / grid / wash) |
| 3 | Main subject (human *or* shape *or* sketch — per mode) |
| 4 | Foreground particles / ink / glow |

### 4. Text / caption theme binding

Opening title, end title, and captions use the **current** theme accents only.
