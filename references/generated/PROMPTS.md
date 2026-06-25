# Generation Prompts — IMS Managed Services Site

Split by asset type. See `SLOTS.md` for which section each one fills and
`README.md` for the brand world and the negative-prompt block to append.

---

# § Photos

Raster PNGs that land in this folder. Append the shared photo negative
prompt (see `README.md`) to every prompt below.

## 01 · `hero.png` — Hero, 21:9 cinematic banner  *(essential)*

Cinematic editorial photograph of a quiet, premium executive briefing
centre, shot from a slight low angle three-quarter view. A long walnut
conference table runs into the frame. At the far wall, a clean ultra-wide
LED video wall glows soft cool white, with abstract participant tiles too
soft to read. Acoustic felt walls in deep navy, brushed graphite accents,
recessed warm linear lighting, concealed cable runs disappearing into the
floor. Empty room, no people in frame. Faint atmospheric haze. Large-format
camera feel, 50mm lens, f/4, calm and quiet. Subtle film grain.

Palette: deep navy `#001833`, brushed graphite, warm precision-gold accent
`#ECAE3D` only in the practical wall sconces, soft cream tabletop
highlights.

Aspect: 21:9. Mood: quiet competence. Read: *the AV you never notice.*

## 04 · `shift.png` — Operational pivot, 3:2  *(essential)*

Photograph of a network / AV operations centre at night, shot in
three-quarter from behind a single seated operator. The operator wears a
neutral dark technical jumper, headset off and resting on the desk. In
front: a curved triple-monitor setup showing abstract dashboard panels (no
readable text), and beyond that a wall of softly glowing room-health tiles.
Workspace is clean, no clutter, no posters. Cool ambient lighting with a
single warm desk lamp on the right of the operator.

Palette: deep navy back wall, charcoal desk, cool blue monitor wash, single
warm precision-gold desk lamp glow.

Aspect: 3:2 landscape. Mood: *we don't install AV, we run it.* Operational,
unglamorous, awake.

## 13 · `promise.png` — End-of-day bookend, 21:9  *(optional)*

Counterpoint to the hero. Cinematic photograph of a wide, empty executive
collaboration floor at end-of-day. Long sightline through a hallway of
glass-walled meeting rooms, each one slightly lit, displays in standby.
Polished concrete floor reflects the linear ceiling lighting. Shot dead
straight down the corridor, with strong one-point perspective. No people,
no movement.

Palette: deep navy walls beyond the glass, brushed steel mullions, cream
floor reflections, single precision-gold accent light deep at the vanishing
point.

Aspect: 21:9. Mood: *we measure our success by yours.* Quiet, ordered,
end-of-day calm.

---

# § Vector / inline SVG

Prompts you paste into Claude / GPT / Gemini to generate inline `<svg>`
markup, or that you (or I) hand-write directly into `index.html`. Output
should be self-contained SVG: no external fonts, no `<image>`, no filter
blurs, no gradients deeper than 2 stops.

Append to every SVG prompt:

> Return only an inline `<svg>` element. Use `viewBox` for scaling, no
> width/height attributes. Stroke colors must be CSS variables
> (`var(--navy)`, `var(--gold)`). No raster fills, no `<image>` tags, no
> blur filters, no drop shadows. Keep total node count under 60.

## 03 · `uptime-stripe` — Reliability strip chart

Generate an inline SVG, `viewBox="0 0 800 120"`, that draws a 30-day uptime
strip. Thirty thin vertical bars across the full width, evenly spaced, each
~12px wide. Twenty-eight bars are filled `var(--navy)` at full height
(80px). Two bars (around day 9 and day 22) are filled `var(--gold)` at
slightly shorter height (60px), representing detected-and-resolved
incidents. Below the bars, one thin baseline rule in `var(--navy)` at 30%
opacity. A small label area on the left for "30 day uptime — 99.2%" — but
text comes from HTML, not the SVG. Stroke-less, fills only.

## 05 · Failure point icons — `volume-2 monitor wifi plug terminal`

These are library icons, not custom. Pull from Lucide
(https://lucide.dev/icons) using the names above. Each rendered inline at
32×32, stroke `var(--navy)`, 1.5px, no fill. Wrap each in a small
`.failure-icon` container with a 1px navy border at 12% opacity and 6px
radius. Order in the strip: `volume-2`, `monitor`, `wifi`, `plug`,
`terminal`.

## 07 · `growth-arc` — Growth motif

Generate an inline SVG, `viewBox="0 0 480 360"`, depicting a calm upward
arc connecting three labeled nodes left-to-right. Node 1 (bottom-left) at
~(80, 280), Node 2 (middle) at ~(240, 180), Node 3 (top-right) at
~(400, 80). A smooth cubic Bezier curve, stroke `var(--navy)`, 1.5px,
no fill, slightly dashed (`stroke-dasharray="6 4"`). Each node is a
circle r=10, fill `var(--navy)`, *except node 3* which is fill
`var(--gold)`. Around node 3 only, a thin outer ring r=18, stroke
`var(--gold)`, 1px, no fill. No text inside the SVG — labels come from
adjacent HTML.

## 08–11 · Pillar icon set  *(generate all four in one go for consistency)*

Generate four inline SVGs, each `viewBox="0 0 64 64"`, sharing the same
stroke weight (1.5px), same line caps (round), and the same single-gold-
accent rule: most strokes are `var(--navy)`, exactly one stroke per icon
is `var(--gold)` to signal the active layer.

- **`pillar-icon-01` — Service & Support (Foundation)**: a stylised
  radar-style concentric arc — three concentric quarter-arcs in the lower-
  left quadrant, one small filled dot at the origin (gold). Reads as
  monitoring sweep.
- **`pillar-icon-02` — AVaaS (Lifecycle)**: a closed loop of four arrows
  forming a square cycle (procure → deploy → support → refresh). All four
  arrows navy except the top arrow which is gold.
- **`pillar-icon-03` — Staff Augmentation (Human Layer)**: two stacked
  rectangles offset diagonally, suggesting overlapping teams. The top
  (smaller) rectangle is gold-stroked; the bottom navy.
- **`pillar-icon-04` — Reporting / 4Sight (Intelligence)**: three
  ascending vertical bars of increasing height with a single horizontal
  axis line, and one thin trend-line crossing them. Bars navy; trend-line
  gold.

Set rule: same padding inside each viewBox (8px), same 1.5px stroke, same
round caps, same line-join. If one drifts off-system, regenerate all four.

## T2 · `gold-mark` — Outcome card accent

Generate an inline SVG, `viewBox="0 0 24 24"`. Replace the existing `✓`
glyph on the `.outcome-card__mark` with a small geometric mark: a
24×24 square rotated 45°, drawn as a hollow diamond, stroke `var(--gold)`,
1.5px, no fill, with a single shorter diagonal stroke inside from the
top vertex to the centre, same stroke. Calm, precise, not a checkmark.

---

# § Library icons

For all small UI marks not listed above (nav glyphs, list bullets, contact
links), use **Lucide** as the default family. Pull each icon's SVG from
lucide.dev, paste inline, and set `stroke="currentColor"` so it inherits
the surrounding text color. Do not mix icon families.

Naming convention in markup: add `data-icon="<lucide-name>"` to the
wrapper so a later pass can swap families in one find-and-replace if the
brand evolves.

---

# § Textures

## T1 · `texture-grain` — Subtle grain on navy

Implement as an inline SVG filter inside `index.html`, *not* as a PNG.

```html
<svg width="0" height="0" style="position:absolute">
  <filter id="texture-grain">
    <feTurbulence type="fractalNoise" baseFrequency="0.9"
                  numOctaves="2" stitchTiles="stitch"/>
    <feColorMatrix values="0 0 0 0 0
                           0 0 0 0 0
                           0 0 0 0 0
                           0 0 0 0.14 0"/>
  </filter>
</svg>
```

Apply to navy sections via a pseudo-element overlay with
`filter:url(#texture-grain)` and `mix-blend-mode: multiply`. Tunable knobs:
`baseFrequency` for grain density, the last column of the color matrix for
opacity. No file, no request, no asset weight.
