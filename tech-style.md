# tech-style (Cyber-Sumi Tech Guide)

**Short call names:** **`tech style`** · **`tech-style`** · **`cyber-sumi`** · TechSpec / knowledge guide  
**Canonical `project.json` style id:** `"tech-style"`  
**Also record:** `"art_engine": "python-cyber-sumi"` (or Remotion equivalent if rebuilt later)

Use for **product / specs / buying-guide / knowledge** shorts (laptops, hardware, software, comparisons) — not dark-psychology moral stories.

Seed film: project `films/techspec-01-laptop-college-major/`.

---

## Palette lock (Cyber-Sumi)

| Token | Hex | Use |
|-------|-----|-----|
| Charcoal void | `#12141A` | Full-frame ground |
| Deep ink | `#0B0C10` | Bars / plates |
| Gold blueprint | `#C9A227` | Rules, frames, accents |
| Soft gold | `#E0C56A` | Secondary highlights |
| Cyan tech | `#3BC7D9` | Active states, scan lines, tags |
| Paper label | `#F2F0EA` | High-contrast titles |
| Mist rail | `#2A2E38` | Inactive UI |

- Subtle paper grain OK; keep it quiet.
- Sparse blueprint grid — do **not** crowd the frame with dense grid noise.
- Brand plate top-right (channel mark: TechSpec Vault **or** project brand if user overrides).

---

## HARD: one-by-one image rules

**Never** put 2 / 3 / 4 photos in a grid or collage on one beat for vertical shorts. That kills watchability.

| Rule | Detail |
|------|--------|
| One hero at a time | Exactly **one** primary photo or product still per beat |
| Sequence with VO | When VO lists A → B → C → D, cut visuals **in that order**, one full-frame hero each |
| Beat length | Split scene duration evenly (or by VO phrase) across N beats |
| Progress dots | Optional small cyan/gold dots under hero showing beat index |
| No dual-pane | Banned: side-by-side photos, 2×2 grids, picture-in-picture stacks of equal weight |
| Compare without photos | Spec compares (8GB → 16GB) use **motion-graphic cards**, not two photos at once |
| Checklist | Reveal **one checklist item at a time**; prior items may shrink as ✓ list |

### Examples

- Workloads VO (“documents… code… design… CAD”) → 4 sequential heroes, not a 4-up mosaic.
- CS + UI/UX → coding hero first, then design hero, then RAM motion card.
- OS compatibility → one OS card (Windows / macOS / Linux) per beat.

---

## HARD: text / title rules

| Style | When | Behavior |
|-------|------|----------|
| **Typewriter** (`type`) | Hooks, key claims, first-screen lines | Characters appear sequentially; blinking cyan caret; gold underline grows |
| **Word reveal** (`words`) | Section headings | Words enter left→right on a dark plate + gold edge bar |
| **Wipe / slide** (`wipe`) | Secondary OST | Title slides up with gold underline draw |
| Captions | Always | Bottom third; short chunks; high contrast; stop at VO end |

### Text craft locks

1. **Large, few words** — no paragraphs on screen.
2. Hook screen: typewriter the **spoken hook claim**, then reveal short OST (e.g. `YOUR MAJOR → YOUR SPECS`).
3. Prefer **2 lines max** for typewriter hooks on 9:16.
4. Spec numbers (`8GB`, `16GB`, `32GB+`) as hero motion-graphic cards, not tiny captions alone.
5. Do not stack long OST + long hook + busy photo labels at once — hierarchy: hook/title → hero → one tag.

---

## HARD: motion graphics rules

Use **original motion graphics** (Python/PIL/canvas/Remotion) for tech storytelling:

| Element | Required craft |
|---------|----------------|
| RAM tiers | Animated modules / bars for 8 / 16 / 32GB+; active = gold+cyan |
| Spec arrows | Gold measurement / upgrade arrows (8 → 16) |
| Hardware callouts | GPU / CPU / NPU cards that slide in one-by-one |
| OS cards | Full-width card with gold edge + animated arrow; rotate one OS per beat |
| Checklists | One large current item + small ✓ for completed |
| Blueprint / CAD | Rotating gold/cyan line art when no photo needed |
| Product laptop | Real still with **zoom/Ken Burns** + cyan scan line — not a static dump |
| Transitions | Slide-left, slide-up, zoom, fade — **no** generic slideshow crossfade as only motion |

### Camera / image animation (every hero)

1. Enter animation (slide / zoom / fade) over ~0.4–0.7s.
2. Slow Ken Burns (scale + micro pan) while held.
3. Optional cyan horizontal scan line.
4. Gold frame around hero plate.

Banned as the *only* motion: opacity crossfade of two stills · frozen collage · static title over still photo.

---

## HARD: B-roll / asset rules

| Rule | Detail |
|------|--------|
| Sources | Free-to-use only: Pexels, Pixabay, or verified equivalents |
| Manifest | Always write `assets/SOURCES.md` with file, URL, license note |
| Categories | Match script: study/library, coding, UI/UX, engineering/CAD, keyboard/ports, laptop product |
| Fallback | If download fails → generate Cyber-Sumi motion graphic (never leave black hole) |
| Treatment | Cyber wash (blend toward charcoal ~25–35%), slight desat, gold frame |
| Sync | Change B-roll **when the spoken idea changes**, not on a fixed slideshow timer alone |
| Logos | Avoid brand logos unless asset rights are clear |

Prefer **one strong still + motion** over weak multi-clip mosaics.

---

## Format & delivery (tech guides)

| Setting | Default |
|---------|---------|
| Aspect | 9:16 · 1080×1920 · 24fps |
| Duration | Target ~60–80s (knowledge guides); honor script if user sets range |
| VO | Clear medium-pace English (or Urdu if routed via `dark_urdu_skill` + this visual doc) |
| Music | Bed under VO; duck so music stays quieter than voice |
| Output | `output/techspec-NN-slug.mp4` (or user path) |
| Deliverables | Final MP4 · scripts · assets · SOURCES.md · VO · captions · render log |

Record in `project.json`:

```json
{
  "style": "tech-style",
  "art_engine": "python-cyber-sumi",
  "visual_combo": {
    "aesthetic": "cyber-sumi",
    "image_rule": "one-hero-per-beat",
    "text_styles": ["typewriter", "word-reveal", "wipe"],
    "broll": "pexels-or-generated"
  }
}
```

---

## Pipeline checklist

1. Parse script into scenes + beats (one idea = one beat).
2. Download B-roll/product stills → license notes.
3. Generate VO; build timeline; **map beats to VO phrases**.
4. Render sequential heroes + kinetic titles + motion cards.
5. Mix bed under VO; burn captions; brand plate.
6. QC: no multi-image grids · titles readable · duration in range · preview full cut.

---

## Do / Don’t

**Do**
- One image, then the next, synced to speech
- Typewriter hooks + motion-graphic headings
- Animated RAM / OS / checklist cards
- Quiet Cyber-Sumi charcoal + gold + cyan

**Don’t**
- 4 images on screen at once
- Walls of on-screen text
- Slideshow-only fades
- Unlicensed logos or missing source notes
