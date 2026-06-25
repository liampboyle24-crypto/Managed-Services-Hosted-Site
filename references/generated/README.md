# Generated Asset Library — IMS Managed Services Site

This folder is the **planned asset set** for the upcoming redesign run of
`index.html`. Every slot below is intentionally typed so the next pass knows
*how* to source it — not everything is an AI photograph.

> The 2 photos already in `/references/` (`Boardroom_CollaborationSpace.png`,
> `Delegate_Assembly_colorgraded.png`) are the **brand mood anchor**. Any
> asset that does ship as a photo must feel like it could sit next to those
> two without looking out of place.

---

## Asset strategy (read this first)

The earlier draft of this folder planned 14 raster photos. That was too
photo-heavy and would have read as AI-image stock. The plan now splits each
slot into one of four types:

| Type | When we use it | Where it lives |
|---|---|---|
| 📷 **Photo** | Only where a real environment carries meaning a diagram can't (hero, NOC at night). Cap: **2 essential, 2 optional**. | Raster `.png` files in this folder. |
| 🟦 **Vector / inline SVG** | Diagrams, charts, abstract motifs, pillar icons. Anything geometric or data-driven. | Written directly into `index.html` as inline `<svg>`. No file. |
| ⬛ **Library icon** | Small UI marks (failure category icons, list bullets, nav glyphs). | Pulled from **Lucide** (primary). Inline SVG, recolored via `currentColor`. |
| 🌫 **Texture** | Surface depth on flat navy sections, gold accent on outcome card. | CSS-only `<feTurbulence>` for grain (no file). One small PNG only if foil is desired. |

Net effect: the page lands at **2 photos + ~6 inline SVG diagrams + Lucide
icons + an SVG noise filter**, instead of 14 photo slots.

---

## Brand world (applies to every type)

| Lever | Direction |
|---|---|
| Palette | Deep Navy `#001833` / `#002D56`, Precision Gold `#ECAE3D`, Technical Blue `#004B8D`, Ink Charcoal `#1A1A1A`, Soft Cream `#F9F9F9` |
| Lighting (photos) | Cinematic, controlled, cool ambient with a single warm accent. Practicals provide warmth. |
| Format (photos) | Large-format feel, 50–85mm equivalent, moderate DOF. |
| Stroke (SVG / icons) | 1.5px nominal. Square caps for technical/diagram art, round caps for icons. |
| Type | Source Serif 4 (display), Hanken Grotesk (UI). Already loaded in `index.html`. |
| Mood | Quiet competence. Editorial. Operational, not theatrical. |

### Anti-slop (applies wherever an AI is generating)

> Photos: *no glowing holographic UI, no neon, no purple/teal AI gradient,
> no lens flares, no glass orbs, no centered face portrait, no fake brand
> logos, no readable text overlays, no stock-photo handshake, no headset
> call-center cliché, no fisheye, no tilt-shift miniature, no heavy
> vignette, no oversaturation.*
>
> SVG: *no inline raster fills, no `<image>` tags, no `filter: blur` to
> fake softness, no gradients deeper than 2 stops, no rainbow palettes, no
> drop shadows pretending to be glow.*

---

## Files in this folder

- `README.md` — this file. Strategy, brand world, sourcing-type table.
- `PROMPTS.md` — prompts for the **photo** slots and the **vector/SVG** slots, grouped by type. Paste-and-go.
- `SLOTS.md` — every site section, its asset type, the filename or inline-SVG marker the redesign pass should produce, and the CSS slot it fills.

## Workflow for the redesign run

1. Open `SLOTS.md`. It is the single source of truth for what gets built per section.
2. For 📷 **Photo** rows: run the prompt in `PROMPTS.md § Photos` through any high-quality image generator. Save the PNG into this folder using the exact filename in `SLOTS.md`.
3. For 🟦 **Vector / inline SVG** rows: run the prompt in `PROMPTS.md § Vector` through Claude / GPT / Gemini, or hand-write the SVG. Paste the result directly into `index.html` at the marker; nothing lands in this folder.
4. For ⬛ **Library icon** rows: copy the named icon's SVG from lucide.dev, paste inline, set `stroke="currentColor"`.
5. For 🌫 **Texture** rows: implement directly in CSS / `<svg><filter>` — no file required unless explicitly noted.
