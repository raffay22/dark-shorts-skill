# Visual themes — dark_urdu_skill (Urdu channel)

Urdu shorts use **Sumi Light / traditional sketch** for moral-emotional storytelling.  
Do **not** default to English-channel Sumi Dark void aesthetics.

## Style lock

| `project.json` `style` | Ground | When |
|------------------------|--------|------|
| `sumi-light` | Warm washi `#F3EFE6` | **Default for every Urdu short** |

Optional only if user explicitly asks: other Beyondsumi styles. Default remains Light/sketch.

**Sumi Light / sketch lock:** paper `#F3EFE6`, soft mineral or ink washes, dry-brush / incomplete contours, storytelling humans and props. Captions: dark ink on soft washi backing, **RTL**.

## Theme palette catalog (Urdu — Light / parchment)

Pick **one primary theme per video**. Prefer unused in last 2–3 Urdu topics.

| Theme | Paper / ground | Accent | Feel |
|-------|----------------|--------|------|
| Washi Cinnabar | `#F3EFE6` | `#D3381C` | Warm warning / courage |
| Washi Indigo | `#F3EFE6` | `#1D3B58` | Calm wisdom |
| Washi Peony | `#F3EFE6` | `#C94A6A` | Soft emotion / heart |
| Washi Jade | `#F3EFE6` | `#2E6F5E` | Growth / clarity |
| Washi Gold | `#F3EFE6` | `#C89B3C` | Respect / value |
| Soft Parchment Mist | `#F0EBE0` | `#6B7260` | Quiet moral tone |

## SVG art modes (rotate — Urdu)

| Mode ID | Look | Prefer for |
|---------|------|------------|
| `japanese_sketch` | Dry brush, hatching, incomplete contours on washi | Observation / social lessons |
| `wet_wash_light` | Wet mineral washes on warm washi | Soft emotional beats |
| `human_ink_fill` | Soft filled sketch humans | Character-building dialogues |
| `line_architecture` | Soft room/door frames on parchment (not dark void) | Social boundaries / scarcity of attention |

**Consecutive Urdu topics must use a different `art_mode`.**

Avoid as Urdu defaults: `splash_sumi_dark`, Freezing Void neon, pure black corporate geometry.

## HARD uniqueness (Urdu series)

Inventory `films/urdu-topic-*/project.json` before generating:

1. New primary theme / bg  
2. New dialogue bed  
3. New end music  
4. New art_mode vs previous Urdu topic  
5. New metaphors  

Record in `visual_plan`: `primary_theme`, `art_mode`, `background_note`, `scene_metaphors`, `prior_avoid`.

## Motion

Every Urdu style/mode **must** use **GSAP + advanced motion graphics** (see locked-settings.md).

## Critical creativity

- ≥4 SVG layers per scene  
- New Python generator per topic  
- Zero metaphor reuse across Urdu videos  
- Emotional storytelling metaphors over dark-corporate sigils  
