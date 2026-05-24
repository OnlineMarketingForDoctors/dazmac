# Dazmac Design System

A comprehensive visual identity for **Dazmac International Logistics** — Australia's freight forwarding and shipping specialist. The system pairs a trustworthy, professional maritime palette (deep navy and teal) with a sharp, urgent red accent that drives action. The overall feeling is **corporate, confident, and seafaring** — disciplined geometry, generous white space, and one bold call-to-action that is impossible to miss.

---

## 1. Brand Personality

| Trait | Expression |
|---|---|
| **Trustworthy** | Deep navy backgrounds, full-bleed maritime photography, certification iconography |
| **Bold & Decisive** | A single saturated red CTA that never disappears (fixed right-side button) |
| **Maritime / Industrial** | Cyan-teal accents echo ocean water; angular section cuts evoke ship hulls and containers |
| **Approachable & Clear** | Generous white sections, large headings, plain-language sub-copy, italic testimonial voice |

---

## 2. Color Palette

### Primary

| Token | HEX | RGB | Usage |
|---|---|---|---|
| `--brand-red` | `#E63329` | 230, 51, 41 | Primary CTA ("GET A QUOTE"), eyebrow labels ("ABOUT US"), decorative chevrons, list bullet arrows, accent in logo |
| `--brand-teal` | `#1A8FA8` | 26, 143, 168 | Secondary CTA ("GET INSTANT QUOTE"), numbered step rings, info card numbers, footer phone bar |
| `--brand-teal-bright` | `#15B0C9` | 21, 176, 201 | Highlight teal, top of gradient cards, link hover |
| `--brand-navy` | `#0A1E32` | 10, 30, 50 | Hero overlay, footer background, dark side of gradient cards |
| `--brand-navy-deep` | `#06121F` | 6, 18, 31 | Deepest shadow, full-bleed dark zones |

### Neutrals

| Token | HEX | Usage |
|---|---|---|
| `--ink` | `#0A0A0A` | Main heading text (H1, H2) |
| `--text` | `#1A1A1A` | Body copy |
| `--text-muted` | `#6B7280` | Sub-titles inside cards, role labels |
| `--text-on-dark` | `#FFFFFF` | All text on navy/teal backgrounds |
| `--text-on-dark-soft` | `rgba(255,255,255,0.8)` | Body copy on dark surfaces |
| `--surface` | `#FFFFFF` | Card backgrounds |
| `--surface-tint` | `#F4F7F9` | Off-white section backgrounds, alternating bands |
| `--border-soft` | `#E5E9ED` | Card edges, FAQ row dividers |

### Gradients

```css
/* Vision / Story / Hero / Testimonial overlay */
--gradient-ocean: linear-gradient(120deg, #0A1E32 0%, #0E3A52 45%, #1A8FA8 100%);

/* Bottom-of-page CTA / Footer top */
--gradient-deep: linear-gradient(180deg, #0A1E32 0%, #06121F 100%);

/* Blog band */
--gradient-teal-band: linear-gradient(180deg, #15B0C9 0%, #0E6D86 100%);

/* Subtle radial light on dark hero */
--gradient-hero-vignette: radial-gradient(ellipse at 30% 40%, rgba(26,143,168,0.25), transparent 60%);
```

---

## 3. Typography

**Font family:** Sans-serif modern geometric — the live site uses a Poppins-style face. The system specifies **Poppins** (free, Google Fonts) as the primary stack.

```css
--font-display: 'Poppins', 'Helvetica Neue', Arial, sans-serif;
--font-body:    'Poppins', 'Helvetica Neue', Arial, sans-serif;
```

### Scale

| Role | Size | Weight | Line-height | Letter-spacing | Case |
|---|---|---|---|---|---|
| **H1 (hero)** | 48–56 px | 700 | 1.15 | -0.01em | Title |
| **H2 (section)** | 36–44 px | 700 | 1.2 | -0.005em | Title |
| **H3 (card)** | 22–24 px | 700 | 1.3 | 0 | Title |
| **Eyebrow label** | 13–14 px | 600 | 1.2 | 0.22em | UPPERCASE, red |
| **Body large** | 17–18 px | 400 | 1.65 | 0 | Sentence |
| **Body** | 15–16 px | 400 | 1.65 | 0 | Sentence |
| **Caption / role** | 13 px | 400 | 1.4 | 0 | Sentence, muted |
| **Button label** | 14 px | 700 | 1 | 0.18em | UPPERCASE |
| **Testimonial / Bio** | 16 px | 400 *italic* | 1.7 | 0 | Sentence |

### Typographic rules

- **Section eyebrow labels are always red, all-caps, heavily letter-spaced** (e.g. `ABOUT US`, `OUR ADVANTAGES`, `TRANSPORT GALLERY`, `FAQ`, `BLOG`, `QUOTE TODAY`, `TESTIMONIALS`, `SHIPPING SERVICES`, `HOW IT WORKS`).
- Section headings (H2) appear **immediately below** the red eyebrow, in heavy black.
- Below the H2, a **small red downward chevron** (~24×12 px) appears as a decorative separator.
- **Testimonials and team bios are set in italic** for tonal warmth.

---

## 4. The Signature Red Chevron

The single most recognisable motif. A small downward-pointing red "V" with a subtle glow, placed **between an H2 and the description paragraph**, acting as the visual punctuation that ties every section together.

```html
<svg class="chevron" viewBox="0 0 62 31" width="36" height="18">
  <path d="M0 0 L31 26 L62 0 L31 8 Z" fill="#E63329" />
</svg>
```

- Size: 32–40 px wide on desktop, 24 px on mobile.
- Color: `--brand-red`.
- A second, lower-opacity copy can be placed below it offset by a few px to fake a soft glow / drop shadow.
- A **white** variant of the same chevron appears under H2s on dark backgrounds (testimonials, quote band, blog band).

---

## 5. Decorative Arrow Bullets

Bulleted feature lists use a **red right-pointing arrow** instead of a dot — picking up the ">>" motif from the logotype.

```
▸  No Hidden costs
▸  Competitive import & export rates
▸  Licensed customs and Quarantine brokerage
```

- Arrow glyph: filled red triangle / play-icon shape.
- Inside cards on light backgrounds, an alternative is a **red check-tick** (✓) for the affirmative lists (e.g. "Recommended Dealers & Brokers", "Customs clearance").

---

## 6. Buttons

### Primary CTA — "GET A QUOTE" (the fixed floating button)

```css
.btn-quote-fixed {
  position: fixed;
  right: 0;
  top: 50%;
  transform: translateY(-50%);
  background: #E63329;
  color: #fff;
  padding: 22px 26px;
  font-weight: 700;
  letter-spacing: 0.18em;
  text-transform: uppercase;
  font-size: 14px;
  border: none;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 10px;
  box-shadow: 0 10px 30px rgba(230,51,41,0.35);
  z-index: 100;
}
.btn-quote-fixed::before {
  content: "";
  width: 32px; height: 32px;
  border: 2px solid #fff;
  border-radius: 50%;
  background: url("data:image/svg+xml,...checkmark...") center/14px no-repeat;
}
```

- Sticks to the right edge of the viewport, vertically centred.
- Always visible. Never obscured. White circular check-mark icon stacked above the label.

### Secondary CTA — "GET INSTANT QUOTE"

```css
.btn-instant {
  background: #1A8FA8;
  color: #fff;
  padding: 18px 36px;
  font-weight: 700;
  letter-spacing: 0.18em;
  text-transform: uppercase;
  font-size: 14px;
  border: none;
  border-radius: 0;          /* sharp corners */
  box-shadow: 0 8px 22px rgba(26,143,168,0.25);
  transition: background .25s ease, transform .25s ease;
}
.btn-instant:hover { background: #15B0C9; transform: translateY(-1px); }
```

- Sharp rectangular corners (no border-radius) — matches the red CTA shape.
- Wide horizontal padding, condensed vertical padding.
- A subtle teal drop shadow grounds it.

### Ghost / Link button

For "Read more" inside blog cards: a **small teal square (≈44×44 px) containing a circled white arrow** docked to the bottom-right corner of the image. Geometric, not chromed.

---

## 7. Cards

### Standard service / advantage card

```css
.card {
  background: #fff;
  border-radius: 14px;
  padding: 36px 32px;
  box-shadow: 0 6px 24px rgba(10, 30, 50, 0.06);
  border: 1px solid #EDEFF2;
}
```

- Numbered cards use a **large outlined teal circle** (≈48 px diameter, 2 px stroke) holding a teal numeral, placed at the top-left of the card next to the title.

### Team / director card

- White card, rounded 14 px, generous 40 px+ padding.
- **Circular grayscale portrait** (~140 px diameter) overlaps the top edge of the card by ~50% of its diameter.
- Inside: name (bold), role (muted), italic bio.
- Hover: lift by 6 px, deepen shadow.

### Blog card

- Image with rounded corners (12–16 px).
- Heading overlaid on a darkened gradient at the bottom of the image, white text.
- Teal square with arrow tucked into the bottom-right corner.

### Testimonial card

- Dark teal translucent background (e.g. `rgba(10, 50, 70, 0.6)`) over the hero photograph backdrop.
- Italic body copy, centred.
- Avatar circle + name + small light-blue role line at the bottom.

---

## 8. Gradient Feature Blocks (Vision / Story)

The "OUR VISION" and "OUR STORY" panels are the signature pair: two large rectangular blocks placed edge-to-edge, each with a **left-to-right gradient running from deep navy into bright teal**, white outline-icon centred above the heading, all text white and centred.

```css
.gradient-block {
  background: linear-gradient(120deg, #0A1E32 0%, #0E3A52 45%, #1A8FA8 100%);
  color: #fff;
  padding: 64px 56px;
  text-align: center;
  min-height: 320px;
}
.gradient-block h3 {
  letter-spacing: 0.22em;
  text-transform: uppercase;
  font-weight: 700;
}
```

- Icons are line-only, ~64 px, in white.
- Body copy is centred and italic-leaning weight.

---

## 9. Section Separators (Diagonal Cuts)

The site's most distinctive layout feature. Every full-bleed coloured section ends with an **angled, asymmetric cut** that evokes the prow of a ship or a folded paper envelope.

Two patterns alternate:

**Pattern A — Hero bottom cut**
- A subtle wedge: the bottom edge slopes from full-height on the left to ~85% height on the right, then a tiny notch back up. Implemented via `clip-path`.

```css
.section-hero {
  clip-path: polygon(0 0, 100% 0, 100% 90%, 60% 100%, 40% 92%, 0 100%);
}
```

**Pattern B — Footer / CTA top cut**
- The dark band begins with an upward-pointing peak around 40% width.

```css
.section-footer-band {
  clip-path: polygon(0 12%, 40% 0, 100% 12%, 100% 100%, 0 100%);
}
```

Use these sparingly — only at major section transitions where the background colour changes.

---

## 10. Iconography

- **Line-only**, 1.5–2 px stroke, rounded caps and joins.
- White on dark surfaces, soft teal (`#15B0C9`) on light surfaces.
- Subjects: lightbulb-head (vision), certificate-with-ribbon (story), boat silhouette, car silhouette, motorhome, trailer, motorbike, machinery digger. Each service category gets one.
- Service-tab icons sit at the **bottom** of vertical tab columns, not the top — a deliberate inversion of the usual pattern.

---

## 11. Imagery Treatment

| Context | Treatment |
|---|---|
| Hero photography | Full-bleed aerial / maritime shot, dark navy gradient overlay on the text side, no overlay on the image side |
| Team portraits | Desaturated (grayscale or near-grayscale), circular crop |
| Gallery photos | Rounded corners (12 px), 4-up grid on desktop, equal hover scale (1.03) |
| Blog thumbnails | Rounded 14 px, with text overlay gradient at the foot |
| Service tab backgrounds | Heavy teal-to-navy gradient over a related photograph; photo is reduced to ~30% opacity |

---

## 12. Layout & Spacing

- **Max content width:** 1240 px, with 24 px gutters on mobile, 64 px on desktop.
- **Section vertical padding:** 96–120 px desktop, 64 px mobile.
- **Grid:** primarily 12-col, but the layout favours **3-up card grids** and **2-up gradient blocks**.
- **Vertical rhythm inside a section:** eyebrow → 16 px → H2 → 16 px → chevron → 24 px → body → 40 px → content.

---

## 13. Header

- Dark navy bar (almost black), full-width.
- Logo on the left (white wordmark `DAZMAC` with red `>>` prefix).
- Inline menu on the right: `ABOUT US · SERVICES · TESTIMONIALS · GALLERY · RESOURCES · TRACKING · CONTACT US · BLOG`, white, semibold, slightly letter-spaced.
- Far right: a **teal angled tab** containing a phone icon and the phone number — the tab's left edge cuts at ~30° to echo the section separators.
- Active link uses brand teal.

---

## 14. Footer

- Dark navy (`#0A1E32` → `#06121F`).
- Four columns: logo + addresses, Shipping Services, Quick Links, social.
- Address rows prefixed with a small red map-pin icon.
- All link text white at 80% opacity, hover to 100%.
- Bottom rule with copyright, very small (12 px), 50% opacity.

---

## 15. Motion

Restraint is the rule. Allowed motion:

- Card hover: `transform: translateY(-4px)` + softer/deeper shadow, `transition: all .3s ease`.
- Button hover: 1 px lift + slight brightness shift on the background.
- Section reveals on scroll: `opacity 0 → 1`, `translateY 24px → 0`, staggered children at 80 ms each.
- The fixed red CTA pulses subtly every 6 s — `box-shadow` grows then settles — to call attention without being annoying.

No carousel auto-rotation faster than 7 s. No bouncing icons. No parallax scrolling.

---

## 16. Voice & Microcopy

- **Direct and reassuring.** "Get Your Bespoke Quote Today." "Six compelling reasons why we're Australia's preferred freight forwarding partner."
- **Numbers as proof.** "Over 15 years," "<0.5% damage rate," "Six compelling reasons."
- **Concrete verbs:** "ship", "handle", "deliver", "import", "clear", "track".
- Section titles use Title Case; eyebrows and button labels use UPPERCASE.

---

## Quick Reference — CSS Variable Stub

```css
:root {
  /* Color */
  --brand-red: #E63329;
  --brand-teal: #1A8FA8;
  --brand-teal-bright: #15B0C9;
  --brand-navy: #0A1E32;
  --brand-navy-deep: #06121F;

  --ink: #0A0A0A;
  --text: #1A1A1A;
  --text-muted: #6B7280;
  --surface: #FFFFFF;
  --surface-tint: #F4F7F9;
  --border-soft: #E5E9ED;

  --gradient-ocean: linear-gradient(120deg, #0A1E32 0%, #0E3A52 45%, #1A8FA8 100%);
  --gradient-deep:  linear-gradient(180deg, #0A1E32 0%, #06121F 100%);
  --gradient-teal-band: linear-gradient(180deg, #15B0C9 0%, #0E6D86 100%);

  /* Typography */
  --font-display: 'Poppins', system-ui, sans-serif;
  --font-body:    'Poppins', system-ui, sans-serif;

  /* Radius */
  --radius-sm: 8px;
  --radius-md: 14px;
  --radius-lg: 20px;

  /* Shadow */
  --shadow-card: 0 6px 24px rgba(10, 30, 50, 0.06);
  --shadow-lift: 0 16px 40px rgba(10, 30, 50, 0.12);
  --shadow-red:  0 10px 30px rgba(230, 51, 41, 0.35);

  /* Spacing */
  --section-y-desktop: 112px;
  --section-y-mobile:  64px;
}
```
