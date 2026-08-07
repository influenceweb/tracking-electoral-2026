[readme.md](https://github.com/user-attachments/files/30847230/readme.md)
# DAP — Design System
### Despacho de Asuntos Públicos · Asuntos Públicos MX

A brand and UI system for **DAP (Despacho de Asuntos Públicos)**, a Mexican
public-affairs and government-relations firm. DAP produces legislative
monitoring, political intelligence and regulatory analysis for corporate
clients — e.g. its *“Radar Legislativo Local”* weekly brief and electoral
outlook decks. The visual language is **editorial, political and confident**:
heavy geometric headlines, a high-contrast serif for feature titles, solid
**magenta + ink + neutral-gray** data rectangles, and tracked-caps eyebrows.

> **Web/Twitter/handles:** asuntospublicos.net · @dap_mex

---

## Sources provided

This system was reverse-engineered from two brand artifacts supplied by the
client (no codebase or Figma was provided):

1. `uploads/Captura de pantalla 2026-06-24 a la(s) 5.11.04 p.m..png` — an
   electoral-outlook slide *“¿Qué está en juego?”* with the signature data
   rectangles. (working copy: `uploads/shot_stats.png`)
2. `uploads/Captura de pantalla 2026-06-24 a la(s) 5.18.57 p.m..png` — the
   *“Radar Legislativo Local DAP”* Instagram-format cover. (working copy:
   `uploads/shot_radar.png`)

Brand assets (logo lockups, decorative line motifs) were cropped directly from
these screenshots — see `assets/`. **If you have the original vector logo,
brand fonts or photography, please share them** (see *Caveats*).

---

## Font substitution ⚠️

The brand fonts were not supplied. We substituted the nearest Google Fonts:

- **Display / headlines / big numbers** → **Poppins** (700–900). The DAP
  headline is a heavy, rounded geometric sans; Poppins is the closest free
  match.
- **Editorial / cover titles** → **Playfair Display** (700–800). A
  high-contrast didone matching the *“Radar Legislativo”* serif.
- **Body / UI** → **Poppins** (400–600).

Fonts load via a Google Fonts `@import` in `styles.css` (so `Fonts: (none)`
appears in the compiler — there are no self-hosted `@font-face` binaries).
**Please confirm the real typefaces** so we can swap them in.

---

## CONTENT FUNDAMENTALS

**Language.** Spanish (Mexico). Formal, institutional register aimed at
corporate decision-makers and public-affairs professionals.

**Voice & person.** Third-person, impersonal and authoritative. The firm
speaks as an analyst, not a friend: *“el monitoreo semanal identifica…”*,
*“entidades que actualmente son gobernadas por mujeres se renuevan.”* Avoid
first-person *“nosotros”* on public-facing pieces; address the client as *“su
empresa”* (usted), never *“tú”*.

**Tone.** Precise, factual, numbers-forward. Copy leans on hard quantities and
dates — *“12 de los 23”*, *“1,803 presidencias municipales”*, *“semana del 12
al 19 de junio”*. No hype, no exclamation marks, no marketing fluff.

**Casing.**
- Eyebrows / kickers: **ALL CAPS, tracked** (`SEMANA DEL 12 AL 19 DE JUNIO`,
  `ASUNTOS PÚBLICOS MX`).
- Headlines: sentence case, often a question (*“¿Qué está en juego?”*).
- Knockout emphasis bars: ALL CAPS (`PARA EMPRESAS`).
- Body: sentence case; **bold** a single key noun for scanning
  (*estados **morenistas***, *gobernadas por **mujeres***).

**Emphasis.** Bold one or two words per statement — usually the political
actor or the noun that carries the stat. Never italicize for emphasis (italics
are reserved for the web address treatment, e.g. *ASUNTOSPUBLICOS.NET*).

**Emoji.** None. The brand never uses emoji. Status and metadata are carried by
color, tags and tracked caps — not pictographs.

**Numbers.** Always numerals (never spelled out), tabular figures, Mexican
grouping (*1,803*). Pair a figure with a short qualifier: *“3 de los 4 / estados
que gobierna el PAN”*.

**Sample copy.**
- *“¿Qué está en juego?”*
- *“Iniciativas con impacto PARA EMPRESAS.”*
- *“Monitoreo Legislativo Local DAP.”*
- *“12 de los 23 estados morenistas enfrentarán elecciones en 2027.”*

---

## VISUAL FOUNDATIONS

**Color.** Magenta is the spine of the brand: `#C3236C` (primary) with a
brighter `#CF3476` for display accents and a darker `#9E1A56` for hover. It is
balanced by near-black **ink** `#111111`, pure white, and a cool **neutral-gray
ramp** (the light data card is `#E2E2E2`). A deep **wine/maroon** `#5A2A3B`
appears as an editorial ground and accent disc. Imagery skews **desaturated and
cool** (the legal photo behind the Radar cover is nearly grayscale), letting the
magenta and wine pop. No multi-stop rainbow gradients; no blue-purple tech
gradients.

**Type.** Heavy geometric sans (Poppins 800/900) for headlines and figures —
tight tracking (`-0.02em`), very tight leading (`0.95`). Playfair Display for
editorial cover titles, often two-tone (white + magenta words). Body is the
same geometric sans at 400–600. Eyebrows are tracked caps (`0.16em`).

**Backgrounds.** Three modes: (1) **white** with corner line-motifs; (2)
**solid magenta or ink** full-bleed for section dividers; (3) **dark editorial**
(ink / desaturated photo) with a **wine circle** behind a serif title. Decorative
**line patterns** — fine concentric “fingerprint” rings and parallel wave lines
in pale magenta — anchor the corners (`assets/rings.png`, `assets/waves.png`).
No noise/grain texture; lines are crisp vector-style.

**The signature motif — data rectangles.** Stats live in **solid, sharp-cornered
rectangles** alternating magenta / ink / light-gray, each a big tabular figure
over a one-line caption with a bold keyword. Laid in a 3-column grid. This is the
single most recognizable DAP device (`StatBlock` component).

**Corners.** **Sharp.** Cards and stat blocks have **0 radius** — rectangles,
not pills. Only interactive controls (buttons, inputs) get a small `4px` radius;
avatars/chips may be pill. Treat rounding as the exception.

**Borders.** Hairline `1px` gray (`#E2E2E2`) on white cards. Solid fills carry
no border. A `3px`/`4px` magenta or white rule is used as a short accent tick
under eyebrows on dividers.

**Shadows.** Minimal — the brand is flat. Product UI may use a soft
`0 4px 14px rgba(17,17,17,.10)`; brand/print pieces use none. There is no
neumorphism and no glow.

**Highlight device.** A solid **knockout bar** wraps an emphatic phrase
(`PARA EMPRESAS`) — magenta block, white text, near-square corners,
`2px 12–20px` padding. Used once per headline.

**Motion & states.** Restrained. Buttons darken their fill on hover
(`magenta → magenta-700`) and nudge down `1px` on press (no scale-bounce).
Inputs show a magenta border + soft `magenta-100` ring on focus. Easing
`cubic-bezier(0.2,0,0,1)`, durations 120–360ms. Fades over slides; no decorative
infinite loops.

**Transparency & blur.** Sparing. The wine disc sits at ~0.8–0.92 opacity over
photography; the deck player nav uses a translucent ink pill with light blur.
Otherwise fills are opaque.

**Layout.** Generous left margin (~88–96px on a 1280 stage), content anchored
top-left, logo top-right on light grounds / top-left on dark. Eyebrow → title →
content vertical rhythm. Corner motifs are fixed decoration, never behind text.

---

## ICONOGRAPHY

DAP is **logo- and typography-led, not icon-heavy.** The source materials show
almost no UI icons; meaning is carried by the **data rectangles, tracked caps and
the union-mark logo**.

- **Logo / brand mark.** The DAP lockup is a stylized union-jack-like “⊞”
  cross-mark beside the **DAP** wordmark with the tagline *DESPACHO DE ASUNTOS
  PÚBLICOS*. Lockups (cropped from the source, background keyed to transparent)
  live in `assets/`:
  - `dap-logo-magenta-transparent.png` — magenta, for white/light grounds
  - `dap-logo-magenta.png` — magenta on a white plate
  - `dap-logo-white-transparent.png` — reversed white, for ink / wine / magenta
- **Social icons.** The Radar cover shows small **white rounded-square** social
  glyphs (LinkedIn, Facebook, X, Instagram, WhatsApp). These are reproduced as
  simple white chips in the Editorial kit. If you need real glyphs, link
  **Lucide** (`https://unpkg.com/lucide`) or the official brand SVGs — *flagged
  substitution*, none were supplied.
- **No emoji, ever.** Avoid Unicode pictographs in DAP work.
- **Decorative motifs** (not icons): `rings.png`, `waves.png` — pale-magenta
  line patterns for corners/edges.

For product UIs that need a functional icon set (search, filters, chevrons),
default to **Lucide** at `1.75px` stroke to sit comfortably with Poppins —
flagged as an addition beyond the source brand.

---

## INDEX / manifest

**Root**
- `styles.css` — global entry point (consumers link this); `@import`s fonts + tokens.
- `readme.md` — this guide.
- `SKILL.md` — Agent-Skills-compatible front-matter for download/Claude Code.

**`tokens/`** — `colors.css`, `typography.css`, `spacing.css`, `effects.css`.

**`assets/`** — logo lockups, `rings.png`, `waves.png` (corner motifs), source
screenshots under `uploads/`.

**`guidelines/`** — foundation specimen cards (Colors, Type, Spacing, Brand)
shown in the Design System tab.

**`components/`** — reusable React primitives (namespace `DAPDesignSystem_621bb8`):
- `core/` — **Button**, **Card**, **Tag**, **Badge**
- `brand/` — **StatBlock** (signature data rectangle), **Eyebrow**,
  **HighlightBar**, **Logo**
- `forms/` — **Input**

**`ui_kits/`**
- `deck/` — 5 slide archetypes (`cover`, `stat-wall`, `section`, `content`,
  `closing`) + interactive `index.html` deck player.
- `social/` — `radar-cover.html`, the Instagram-format editorial cover.

**`templates/`** — copy-to-start Design Components:
- `dap-stat-slide/` — the “¿Qué está en juego?” stat-wall slide.
- `dap-cover/` — the editorial serif cover slide.

---

## Caveats / open questions

- **Fonts are substitutes** (Poppins, Playfair Display). Need the real brand
  typefaces.
- **Logo is a screenshot crop**, not vector. A clean SVG/PNG would sharpen every
  surface.
- **Editorial photography** (scales/gavel) is represented by a neutral
  placeholder layer — supply real imagery for production covers.
- **Functional/status colors** (success/warning/danger) are **inferred** — not
  seen in the source. Confirm before using in product UI.
- Only two artifacts were provided; **more decks, posts or a live URL** would
  let us expand the kit (charts, tables, document layouts, web nav).
