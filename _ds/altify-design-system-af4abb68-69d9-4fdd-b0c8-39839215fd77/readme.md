# Altify Design System

The brand + UI system for **Altify** — positioned here as *"the AI Operating System for revenue teams."* Altify runs the administrative and analytical work of selling (data ingestion, mapping, contextual record analysis, reconciliation) so that humans are freed for the high-impact work only humans do: communication, relationships, and strategic thought. The through-line of the brand is one sentence:

> **Humans aren't replaced. Humans are unlocked.**

This repository is the single source of truth for building **on-brand decks, slides, and product/marketing UI** for Altify. It ships brand assets, color + type + spacing foundations, reusable React UI primitives, a library of slide specimens, and a ready-to-edit deck template.

---

## Sources

This system was reverse-engineered from the brand assets provided by the user (no codebase or Figma was attached):

| Source | What it gave us |
|---|---|
| `uploads/` → `assets/logo/altify-logo.png` | The **ALTIFY** wordmark — navy letters with two orange accent strokes. Drives the navy + orange palette. |
| `uploads/Altify AI Operating System.pdf` → `assets/reference/altify-os-quadrant.png` | The signature **"Altify as an AI Powered OS"** quadrant diagram. Source of the positioning trio (AI red / Human blue / Collaboration purple), the messaging, and the soft-glow visual language. |
| `uploads/Style.png` → `assets/reference/altify-feature-grid.png` | The **"What Happens When Teams Execute"** four-up benefits slide. Source of the soft-gray card style, navy line-icon treatment, and display type. |

> ⚠️ **No live product surface (app/website) was provided.** The UI kit here is therefore the **deck/slide system** the brand actually uses. Reusable product screens are intentionally omitted rather than invented — attach a codebase or Figma and we'll add a product UI kit.

---

## ⚠️ Font substitution — please confirm

The deck headlines use a bold geometric sans. Because the only sources were a flattened PDF and PNGs, the **exact headline typeface could not be extracted**. We substituted the closest high-quality match on Google Fonts and self-hosted it:

- **Display / headlines → Poppins** (ExtraBold/Bold) — geometric, matches the wordmark and slide titles closely.
- **Body / UI → DM Sans** — a clean geometric-humanist companion, highly legible small.
- **Mono → JetBrains Mono** — data, metrics, code.

**If you have the real brand font files, send them** and we'll swap them in (drop them in `assets/fonts/` and update `tokens/fonts.css`).

---

## Content fundamentals — how Altify writes

**Voice:** confident, plain-spoken, and human. Altify sells *unlocking people*, not replacing them, so the copy is optimistic and respectful of the reader's expertise — never hype, never fear.

- **Person:** speaks to **"you"** and **"your team"**; refers to itself as **"Altify"** (third person) or **"we"** in narrative. Customers are *revenue teams*, *reps*, *sellers*.
- **Casing:** **Title Case for headlines and labels** ("Align the Buying Group", "Drive Predictable Revenue Growth"); sentence case for body. UPPERCASE only for short letter-spaced eyebrows/labels ("AI WORK", "HUMAN WORK").
- **Sentence shape:** short, declarative, verb-first. Headlines are often a parallel *verb + object*: "Align the buying group." "Execute with discipline." "Drive predictable revenue growth."
- **Signature rhetorical move:** the *antithesis* — a crisp before/after or human-vs-AI contrast. The hero line is the template: **"Humans aren't replaced. Humans are unlocked."**
- **Concreteness:** name the work. Copy lists real artifacts of the job — *Emails, Calls & Chats, Notes & Transcripts, Data Mapping, Contextual Record Analysis* — rather than abstractions.
- **Numbers:** outcomes are framed as lift and time returned ("+38% win rate", "11 hrs per rep per week", "3.2× faster ramp"). Always tie a stat to a human benefit.
- **No emoji.** No exclamation-point energy. No buzzword salad. Calm authority.

**Example copy in-voice:**
> *Eyebrow:* THE AI OPERATING SYSTEM
> *Headline:* Humans aren't replaced. **Humans are unlocked.**
> *Body:* Altify runs the administrative and analytical work of revenue, so your team spends its time where it counts — with customers.

---

## Visual foundations

**Palette.** Two brand colors do the heavy lifting: **deep navy `#103860`** (primary, text, dark surfaces) and **Altify orange `#E87830`** (accent — used sparingly, one CTA per view). A **positioning trio** color-codes the operating model everywhere it appears: **coral red `#F0504D` = AI work**, **sky blue `#3E96E0` = human work**, **violet `#7B6CF0` = human + AI collaboration**. Neutrals are a **cool gray** ramp; the signature surface is `#F1F3F5`. Full ramps + semantic aliases live in `tokens/colors.css`.

**Type.** Poppins display over DM Sans body (see substitution note). Headlines are **ExtraBold, tight tracking (−0.03em), balanced wrap**, often navy (`--text-heading`) or near-black ink. Eyebrows are 13px **bold, uppercase, +0.14em**, frequently with a leading color dot. Body runs 16–22px at 1.5–1.6 line-height. Scale in `tokens/typography.css`.

**Backgrounds.** Two modes only: **clean white/`#F1F3F5`** for content, and a **deep navy gradient** (`--gradient-navy`, ~155°, navy-800→navy-950) for title/section/quote/closing slides. No photography-as-background, no busy textures. Depth comes from **soft radial color "glows"** (`--glow-ai/human/collab`) — large, low-opacity blobs bleeding off-edge — and from very faint quadrant **wash tints**. Imagery, where used, should be cool-toned and calm to sit beside the navy.

**Cards.** The signature card is **flat**: soft-gray fill (`#F1F3F5`), **generous radius (`--radius-xl`, 24px)**, **no border, no shadow**. Surfaces separate by *fill*, not elevation. Variants: `elevated` (white + soft shadow) for floating UI, `outline` (white + 1px gray border), `dark` (navy). The system is low-shadow overall.

**Shadows.** Soft, **cool navy-tinted**, low opacity (`rgba(11,37,64,…)`), used only when something genuinely floats. Plus optional **colored glows** echoing the positioning trio. See `tokens/spacing.css`.

**Corners & borders.** Rounding is consistent and friendly: chips/buttons `--radius-md` (12px) or pill; cards `--radius-xl` (24px); icon tiles `--radius-lg/xl`. Borders are hairline `#DDE1E5`; on dark, `rgba(255,255,255,.16)`.

**Spacing & layout.** 4px base grid. Slides are **1280×720** with **80px gutters / 64px top-bottom** and a consistent chrome: **logo top-left, footer + page number bottom**. Content is vertically centered. Diagrams use a clear coordinate logic (axes, nodes, labeled lists).

**Motion.** Calm and professional — quick fades and small lifts, **no bounce**. Standard ease-out (`--ease-standard`), 120–320ms. Card hover = `translateY(-3px)` + soft shadow. Buttons darken on hover and nudge 1px down on press. Reduced-motion friendly; slide content has no infinite loops.

**Hover / press.** Hover = a step **darker** for solids (navy-700→800, orange-500→600) or a faint navy-50 wash for quiet buttons; press = one step darker still + 1px translate. Focus = a 3px **orange** focus ring (`--shadow-focus`).

**Transparency & blur.** Used lightly: white-on-navy buttons at ~10–14% opacity for secondary actions on dark; glow blobs rely on alpha. No heavy glassmorphism.

---

## Iconography

- **Set:** **[Lucide](https://lucide.dev)** — thin, consistent **1.6px stroke**, rounded line icons. This matches the navy line-icon look in the source feature slide (handshake, magnifier, funnel, growth chart). The original deck's exact icons were flattened into the PNG and could not be extracted, so **Lucide is a documented substitute** chosen for matching weight and style. *(Flagged — swap if the brand has its own set.)*
- **How to use:** load Lucide from CDN (`https://unpkg.com/lucide@0.460.0/dist/umd/lucide.min.js`), drop `<i data-lucide="handshake"></i>` placeholders, call `lucide.createIcons()`. Icons inherit `currentColor` and pair with the **`IconTile`** component (navy icon on a soft-gray/white tile).
- **Color:** icons are **navy by default**, or take a positioning-trio color when tagging AI/human/collab content. Never multicolor.
- **No emoji. No unicode glyphs as icons** (one exception: ▲/▼ trend arrows and the typographic “ ” quote mark in specimens).
- The **logo** is an image asset, never redrawn. Light (navy) and dark (white) variants in `assets/logo/`; also embedded path-free in the `Logo` component.

---

## What's in here (index)

**Foundations**
- `styles.css` — the entry point consumers link (an `@import` manifest only).
- `tokens/colors.css` · `tokens/typography.css` · `tokens/spacing.css` · `tokens/fonts.css` — all CSS custom properties + `@font-face`.
- `guidelines/*.html` — foundation specimen cards (Colors, Type, Spacing, Brand) shown in the Design System tab.

**Components** (`components/<group>/` — React, `window.AltifyDesignSystem_af4abb`)
- `buttons/` → **Button** (primary/accent/secondary/ghost/subtle/inverse)
- `labels/` → **Eyebrow**, **Badge**
- `surfaces/` → **Card**, **IconTile**, **StatCard**, **Bullet**
- `brand/` → **Logo** (wordmark, embedded)
- Each has a `.d.ts` contract, `.prompt.md` usage note, and a `@dsCard` showcase HTML.

**Slides** (`slides/`) — self-contained 1280×720 specimens, one per type: `title`, `agenda`, `section`, `feature-grid`, `quadrant` (the signature diagram), `comparison`, `stats`, `quote`, `closing`. Shared layout in `slides/deck.css`.

**Templates** (`templates/altify-deck/`) — **Altify Deck**, a ready-to-edit `.dc.html` deck (title → agenda → feature → metrics → quote → closing) built on the deck-stage shell with keyboard nav, thumbnail rail, and print/PPTX export. Copy it to start a real presentation.

**Assets** (`assets/`) — `logo/` (light + white wordmark), `fonts/` (self-hosted woff2), `reference/` (the original source images, for fidelity checks).

---

## Quick start

```html
<!-- 1. link the system -->
<link rel="stylesheet" href="styles.css" />

<!-- 2. use tokens -->
<h1 style="font-family:var(--font-display);color:var(--navy-700);">Humans are unlocked.</h1>

<!-- 3. or mount a component (after loading _ds_bundle.js) -->
<script>const { Button, Card } = window.AltifyDesignSystem_af4abb;</script>
```

To build a deck, copy the **Altify Deck** template; to build a slide from scratch, copy any `slides/*.html` specimen.
