# Combo style: `sumi-dark-faceless`

**First-class English (and Urdu) option.** Prefer the **short call names** in chat:

| Short (preferred) | Also accepted |
|-------------------|---------------|
| **`faceless combo`** | `dark faceless combo` (long — avoid in chat) |
| **`fd combo`** | `sumi-dark-faceless` · `sumi dark + faceless` · `combo style` (Dark) |

Canonical `project.json` style id stays **`sumi-dark-faceless`**.

Approved seed: project `films/urdu-topic-03-absolute-unpredictability/` (Absolute Unpredictability).

## What it is

| Layer | Choice |
|-------|--------|
| **Engine** | **`faceless-shorts`** (canvas → Chrome capture → ffmpeg). Not Remotion/GSAP-first. |
| **Aesthetic** | **Sumi Dark** — ink void, wet splash masses, selective crimson `#7A1622`, neutral greys. |
| **Not** | Warm paper-atlas parchment as the whole look · stick-body-only kits · recoloured Light washi |

Record in `project.json`:

```json
{
  "style": "sumi-dark-faceless",
  "art_engine": "faceless-shorts+sumi-dark",
  "visual_combo": {
    "engine": "faceless-shorts",
    "aesthetic": "sumi-dark",
    "palette": {
      "void": "#0B0B0C",
      "ink": "#111111",
      "wash": "#5C5C5C",
      "mist": "#2A2A2A",
      "paper": "#E8E8E8",
      "white": "#FFFFFF",
      "accent": "#7A1622"
    }
  }
}
```

## Palette lock (Sumi Dark)

- Void ground `#0B0B0C` (not cream washi).
- Structure ink `#111111` · dilution `#5C5C5C`.
- **Selective** crimson `#7A1622` only for story accents (eyes, fault marks, caution, path forks) — never a full-screen red tint.
- No gold / jade / indigo candy accents unless the user overrides.

## Faceless base

1. Clone a faceless starter (`paper-atlas` example is fine as **engine** seed).
2. **Override** warm parchment/rooms with `voidPage` + `splashBlob` + ink silhouette figures (wet masses, not stick lines).
3. Follow `faceless-shorts/SKILL.md` for VO timing, `capture.mjs`, mix, QA sheet.
4. Prefer story tableaux that **match each line** (not abstract circles alone).

## Craft rules (make it “more good”)

1. **One metaphor system per topic** (e.g. predictable path → shattered forks → caution freeze) — unique vs prior combo films.
2. **≥3 readable states per beat** (anticipate → hit → settle) via shot cuts + timed props.
3. **Camera**: punch-in / push on reveals (faceless camera already punches on cuts); add intentional zoom notes in shots.
4. **Figures**: splash-built silhouettes with facing/gesture; crimson eye only when threat/caution.
5. **Captions**: English channel = English bottom captions; Urdu channel = English matched to Urdu VO (or RTL Urdu if user asks). High contrast on dark — paper slip / dark bar OK.
6. **Audio**: channel voice locks + new bed/end every topic + brand plate + silent end title.

## Channel locks still apply

- English: voice `hgAoejldxKTXsFSP7qeO` · output `output/topic-*`
- Urdu: voice `o0kuOa7rSjdarn7nIRbL` · output `output/urdu-topic-*`
- Loudness: `BED_*` / `END_GAIN≤0.55` · Shadow Protocol top-right

## When to pick this combo

- User says **`faceless combo`**, **`fd combo`**, sumi dark + faceless, or wants Dark dread **without** Remotion SVG this round.
- Power / dread / unpredictability / trap topics fit especially well.
- Otherwise rotate Remotion Sumi family or other faceless styles as usual.
