# HeroKit — Styleguide

> **Version:** 1.4
> **Last updated:** 24 November 2026
> **Source:** `🌈 DS . HeroKit` → page `1. Styleguide`. Figma is the source of truth when this doc and Figma disagree.
> **Naming:** tables use the Figma names of variables and styles (`Shades/80`, `Body/14 Semibold`). Where developers need them, a CSS column gives the code token.

---

## Table of Contents

1. [Logo](#1-logo)
2. [Colours](#2-colours)
3. [Typography](#3-typography)
4. [Sizes](#4-sizes)
5. [Shadows](#5-shadows)
6. [Breakpoints](#6-breakpoints)
7. [Icons](#7-icons)
8. [Illustrations](#8-illustrations)

---

## 1. Logo

The product operates under different brand names depending on market. All share the same icon mark; the wordmark and colour treatment differ per brand.

| Brand | Market |
|-------|--------|
| **Douleutaras** | Greece, Cyprus |
| **YourPro** | Ireland |
| **YourHero** (HourHero) | Parent company |

The logo appears in two additional colour variations under Douleutaras and YourPro — **orange** for the Pros App and **turquoise** for the Cleaners App. These variations do not apply to the parent brand.

> ⚠️ The parent company name appears as "HourHero" in older docs and as "YourHero" in the Logo component. Confirm which one the docs should use.

### 1.1 Logo component

The `Logo` component has five properties that combine to produce all variants:

| Property | Values |
|----------|--------|
| `Logo` | `Douleutaras` · `YourPro` · `YourHero` |
| `Light Mode` | `On` (light backgrounds) · `Off` (dark backgrounds) |
| `Wordmark` | `On` · `Off` |
| `Tagline` | `On` · `Off` |
| `Customer/Pro` | `On` (customer-facing) · `Off` (pro-facing) |

### 1.2 App icons & avatars

| Component | Values |
|-----------|--------|
| `iOS & Android Icons` | `D Transparent` · `YH Transparent` · `D Orange` · `YH Orange` · `D Turquoise` · `YH Turquoise` |
| `iOS & Android Avatars` | `Variant`: `D Customer App` · `YH Customer App` · `Pro App` · `Cleaner App` · `Mode`: `Light` · `Dark` |

Figma frame: `Company Logos` — node `6307:75726`.

---

## 2. Colours

All colours are variables in the `Colour Palette` collection. Each scale uses HSL-based steps: lower numbers are lighter, higher numbers are darker.

| Scale | Role |
|-------|------|
| **Shades** | Neutrals: text, borders, backgrounds |
| **Blue** | Primary / brand |
| **Purple** | Secondary |
| **Yellow** | Tertiary |
| **Orange** | Warning |
| **Coral** | Error |
| **Green** | Success |
| **Mint**, **Turquoise** | Mostly illustrations |
| **Red** | Legacy error — to be replaced by Coral |

> Values follow the Colour Palette frame in the HeroKit Figma file (node `6074:8721`), which is the source of truth.

---

### 2.1 Shades `H209–238`

Renamed in Nov 2026: the former "Saturated Shades" group is now **Shades**. The old greys are kept as **[Archived] Shades** (see 2.12).

| Step | Hex | H | S | L |
|------|-----|---|---|---|
| 0 (White) | `#FFFFFF` | — | — | 100 |
| 5 | `#F9FAFB` | 209 | 019 | 098 |
| 10 | `#F3F5F7` | 210 | 019 | 096 |
| 20 | `#E3E8ED` | 211 | 022 | 091 |
| 30 | `#D5DBE2` | 213 | 019 | 086 |
| 40 | `#B2BBC7` | 214 | 016 | 074 |
| 50 | `#929CAB` | 215 | 013 | 062 |
| 60 | `#717C8E` | 218 | 011 | 050 |
| 70 | `#515867` | 221 | 012 | 036 |
| 80 | `#3A3D46` | 226 | 010 | 025 |
| 90 | `#232429` | 231 | 007 | 015 |
| 95 (Black) | `#111113` | 235 | 004 | 007 |
| 100 (Total Black) | `#000000` | — | — | 000 |

All Semibold product text uses `Shades/95 (Black)`.

---

### 2.2 Blue / Primary `H208–240`

| Step | Hex | H | S | L |
|------|-----|---|---|---|
| 5 | `#F5FAFF` | 208 | 100 | 098 |
| 10 | `#E5F2FF` | 210 | 100 | 095 |
| 20 | `#CFE6FF` | 211 | 100 | 091 |
| 30 | `#A6D0FF` | 212 | 100 | 083 |
| 40 | `#4297FF` | 213 | 100 | 063 |
| **50 (Logo)** | **`#006BFF`** | **215** | **100** | **050** |
| 60 | `#004BE0` | 220 | 100 | 044 |
| 70 | `#042CC8` | 228 | 096 | 040 |
| 80 | `#060F93` | 236 | 092 | 030 |
| 90 | `#01016F` | 240 | 098 | 022 |
| 95 | `#030236` | 241 | 093 | 011 |

**Overlay variables** — used for Hover and Pressed tints.

| Variable | Value | Use |
|----------|-------|-----|
| `Blue/50 (Logo) 5%` | `#006BFF` at 5% | Hover |
| `Blue/50 (Logo) 10%` | `#006BFF` at 10% | Pressed |

Place a white layer (`Shades/0 (White)`) under the tint. Exception: Button Secondary / Tertiary Hover and Pressed use the tint with no white layer.

---

### 2.3 Purple / Secondary `H238–240`

| Step | Hex | H | S | L |
|------|-----|---|---|---|
| 10 | `#F4F4F9` | 240 | 029 | 097 |
| 20 | `#B1B2D5` | 238 | 030 | 076 |
| 30 | `#6466AA` | 238 | 029 | 053 |
| 40 | `#202383` | 238 | 061 | 032 |

`Purple/40` is the step used in about 90% of cases.

---

### 2.4 Yellow / Tertiary `H047–050`

| Step | Hex | H | S | L |
|------|-----|---|---|---|
| 10 (Trial) | `#FFFCEB` | 050 | 100 | 096 |
| 15 | `#FFF8D6` | 050 | 100 | 092 |
| 20 | `#FFF2B2` | 050 | 100 | 085 |
| 30 | `#FFEA80` | 050 | 100 | 075 |
| 50 | `#FFC700` | 047 | 100 | 050 |

> Yellow is to be filled out to a full scale with a hue shift like Blue, ideally making the Orange scale unnecessary. First take is in DS Lab; not in the DS file yet.

### 2.5 Orange / Warning `H033–040`

| Step | Hex | H | S | L |
|------|-----|---|---|---|
| 10 | `#FEFBF5` | 040 | 082 | 098 |
| 30 | `#FBE8C2` | 040 | 088 | 087 |
| 40 | `#FFB017` | 040 | 100 | 055 |
| 50 | `#EF9E00` | 040 | 100 | 047 |
| 60 | `#DB7900` | 033 | 100 | 043 |

---

### 2.6 Coral / Error `H000–002`

| Step | Hex | H | S | L |
|------|-----|---|---|---|
| 10 | `#FEF8F8` | 000 | 075 | 098 |
| 15 | `#FDEDED` | 000 | 080 | 096 |
| 20 | `#FAD0CE` | 003 | 081 | 089 |
| 30 | `#F6A09E` | 001 | 083 | 079 |
| 40 | `#F27874` | 002 | 083 | 070 |
| 50 | `#E65651` | 002 | 075 | 061 |

---

### 2.7 Green `H165–167`

| Step | Hex | H | S | L |
|------|-----|---|---|---|
| 10 | `#E6F4F1` | 167 | 039 | 093 |
| 20 | `#6CFBCE` | 161 | 095 | 070 |
| 25 | `#18D8A1` | 163 | 080 | 047 |
| 30 | `#1FC198` | 165 | 072 | 044 |
| 40 | `#008A65` | 164 | 100 | 027 |

---

### 2.8 Mint `H194–195`

| Step | Hex | H | S | L |
|------|-----|---|---|---|
| 10 | `#F9FCFD` | 195 | 050 | 098 |
| 20 | `#D4ECF3` | 194 | 056 | 089 |
| 30 | `#A9D8E7` | 195 | 056 | 078 |
| 40 | `#84C8DD` | 194 | 057 | 069 |

---

### 2.9 Turquoise `H190–195`

| Step | Hex | H | S | L |
|------|-----|---|---|---|
| 10 | `#F9FCFD` | 195 | 050 | 098 |
| 20 | `#A6DFEB` | 190 | 063 | 079 |
| 30 | `#4CBFD7` | 190 | 063 | 057 |
| 40 | `#00A4C6` | 190 | 100 | 039 |

Mint and Turquoise are mostly used in illustrations.

> ⚠️ An older note said Green, Mint and Turquoise may be merged into one palette that replaces Purple as the secondary colour. This conflicts with current usage (Purple/40 is the main secondary). Confirm whether the plan still stands.

---

### 2.10 Red `H011`

| Step | Hex | H | S | L |
|------|-----|---|---|---|
| 60 Error | `#FF4820` | 011 | 100 | 056 |

> **Note:** Red is to be replaced by Coral at some point.

---

### 2.11 Gradients

Each gradient is a paint style in the HeroKit Figma file.

| Name | Figma style | Stops | Direction |
|------|-------------|-------|-----------|
| Light Blue | `Gradient/Light Blue` | `#E5F2FF` 10% → `#F5FAFF` 100% | Top to bottom |
| Light Blue Invert | `Gradient/Light Blue Invert` | `#F5FAFF` 0% → `#E5F2FF` 90% | Top to bottom |
| Gold Smooth | `Gradient/Gold Smooth` | `#FFC700` → `#FFF2B2` → `#FFC700` | Diagonal (225°) |
| Gold Sharp | `Gradient/Gold Sharp` | `#FFD11A` → `#FFF5CC` → `#FFD11A` | Diagonal (225°), tight midpoint |
| AI | `Gradient/AI` | `#C5C2FF` → `#B3D7FF` | Depends on the shape (see note) |
| AI 80% | `Gradient/AI 80%` | Same as AI, 80% opacity | Depends on the shape |
| AI 50% | `Gradient/AI 50%` | Same as AI, 50% opacity | Depends on the shape |
| Purple (archived) | `Gradient/[Archived] Purple` | `#2E306B` → `#202383` | Top to bottom |

> **Note:** The Purple gradient is archived and kept for legacy layouts only. Do not use it in new layouts. There is no Blue gradient (obsolete).

> **Note:** Figma stretches the AI gradient with the shape it fills, so the CSS angle changes with the box: −71.77° on a square or circle, −22.16° on the 328×44 AI Input Field, −44.99° on the 328×108 field. The stops stay at 11.81% and 87.61%. The AI colours `#C5C2FF` and `#B3D7FF` have no colour variable.

#### CSS

```css
--gradient-light-blue:        linear-gradient(180deg, #E5F2FF 10%, #F5FAFF 100%);
--gradient-light-blue-invert: linear-gradient(180deg, #F5FAFF 0%, #E5F2FF 90%);
--gradient-gold-smooth:       linear-gradient(225deg, #FFC700 23%, #FFF2B2 50%, #FFC700 79%);
--gradient-gold-sharp:        linear-gradient(225deg, #FFD11A 40%, #FFF5CC 50%, #FFD11A 60%);
/* AI: angle shown is for a square or circle */
--gradient-ai:                linear-gradient(-71.77deg, #C5C2FF 11.81%, #B3D7FF 87.61%);
--gradient-ai-80:             linear-gradient(-71.77deg, rgba(197, 194, 255, .8) 11.81%, rgba(179, 215, 255, .8) 87.61%);
--gradient-ai-50:             linear-gradient(-71.77deg, rgba(197, 194, 255, .5) 11.81%, rgba(179, 215, 255, .5) 87.61%);
/* Archived — legacy layouts only */
--gradient-purple-archived:   linear-gradient(180deg, #2E306B 0%, #202383 100%);
```

---

### 2.12 Archived colours

`[Archived] Shades` holds the older greys (`[Archived] Shades/10 White` … `[Archived] Shades/80 Black`). They stay in the file for legacy instances and are duplicated in the `🗄️ DS . Archive` file. **Don't use them in new work.**

> No component uses `[Archived] Shades/10 White` anymore (replaced with `Shades/0 (White)` on 24 Nov 2026). Some documentation frame backgrounds on the Updated Components page still do.

---

## 3. Typography

### 3.1 Typeface

**IBM Plex Sans**

```
Font family:  'IBM Plex Sans', sans-serif
Font stack:   font-family: 'IBM Plex Sans', 'Helvetica Neue', Arial, sans-serif;
Weights:      400 (Regular) · 600 (SemiBold)
```

---

### 3.2 Type Scale

Text styles are named by size during scale calibration. A name without a weight is Regular.

#### Headings

| Figma style | CSS token | Weight | Size | Line-height | Letter-spacing |
|-------------|-----------|--------|------|-------------|----------------|
| `Heading/42 Semibold` | `heading/42` | SemiBold (600) | 42px | 130% | 0% |
| `Heading/36 Semibold` | `heading/36` | SemiBold (600) | 36px | 130% | 0% |
| `Heading/28 Semibold` | `heading/28-semibold` | SemiBold (600) | 28px | 132% | 0% |
| `Heading/28` | `heading/28-regular` | Regular (400) | 28px | 132% | 0% |
| `Heading/24 Semibold` | `heading/24-semibold` | SemiBold (600) | 24px | 138% | 0% |
| `Heading/24` | `heading/24-regular` | Regular (400) | 24px | 138% | 0% |
| `Heading/20 Semibold` | `heading/20-semibold` | SemiBold (600) | 20px | 142% | 0% |
| `Heading/20` | `heading/20-regular` | Regular (400) | 20px | 142% | 0% |

#### Body

| Figma style | CSS token | Weight | Size | Line-height | Letter-spacing |
|-------------|-----------|--------|------|-------------|----------------|
| `Body/18 Semibold` | `body/18-semibold` | SemiBold (600) | 18px | 150% | 0% |
| `Body/18` | `body/18-regular` | Regular (400) | 18px | 150% | 0% |
| `Body/16 Semibold` | `body/16-semibold` | SemiBold (600) | 16px | 150% | 0% |
| `Body/16` | `body/16-regular` | Regular (400) | 16px | 150% | 0% |
| `Body/14 Semibold` | `body/14-semibold` | SemiBold (600) | 14px | 150% | 0% |
| `Body/14` | `body/14-regular` | Regular (400) | 14px | 150% | 0% |
| `Body/14 Caps` | `body/14-caps` | Regular (400) | 14px | 150% | 3% — UPPERCASE |
| `Body/12 Semibold` | `body/12-semibold` | SemiBold (600) | 12px | 160% | 0.5% |
| `Body/12` | `body/12-regular` | Regular (400) | 12px | 160% | 0.5% |
| `Body/12 Caps` | `body/12-caps` | Regular (400) | 12px | 160% | 5% — UPPERCASE |

#### Labels

| Figma style | CSS token | Weight | Size | Line-height | Letter-spacing |
|-------------|-----------|--------|------|-------------|----------------|
| `Label/10 Semibold` | `label/10-semibold` | SemiBold (600) | 10px | 160% | 2% |
| `Label/10` | `label/10-regular` | Regular (400) | 10px | 160% | 2% |

`Label/9` is obsolete and has been removed. It is kept only in the Figma "Obsolete Styles" table.

#### Archived

Kept in Figma for legacy instances. Don't use them in new work.

| Figma style | Weight | Size | Line-height | Letter-spacing |
|-------------|--------|------|-------------|----------------|
| `Archived/20 Semibold` | SemiBold (600) | 20px | 25px | 0% |
| `Archived/20` | Regular (400) | 20px | 25px | 0% |
| `Archived/12 Semibold` | SemiBold (600) | 12px | 16px | 0.5% |
| `Archived/12` | Regular (400) | 12px | 16px | 0.32% |

---

### 3.3 Usage Notes

1. Type colour should be carefully considered, with legibility and accessibility as paramount concerns. Keep type colour neutral in running text.
2. Other use cases for coloured type are code snippets, warnings, alerts, etc.
3. Semibold text uses `Shades/95 (Black)`; running text uses `Shades/80`.

---

## 4. Sizes

The size scale can be applied to `margin`, `padding`, and `border-radius` properties, as well as to both vertical and horizontal edges. The token takes the place of the values normally assigned to these properties. Variables live in the `Size` collection.

| Figma variable | CSS token | Value (px) |
|----------------|-----------|-----------|
| `Sizes/00` | `--size-00` | 0 |
| `Sizes/01` | `--size-01` | 2 |
| `Sizes/02` | `--size-02` | 4 |
| `Sizes/03` | `--size-03` | 6 |
| `Sizes/04` | `--size-04` | 8 |
| `Sizes/05` | `--size-05` | 12 |
| `Sizes/06` | `--size-06` | 16 |
| `Sizes/07` | `--size-07` | 24 |
| `Sizes/08` | `--size-08` | 32 |
| `Sizes/09` | `--size-09` | 40 |
| `Sizes/10` | `--size-10` | 48 |
| `Sizes/11` | `--size-11` | 64 |
| `Sizes/12` | `--size-12` | 80 |
| `Sizes/13` | `--size-13` | 96 |
| `Sizes/14` | `--size-14` | 128 |
| `Sizes/15` | `--size-15` | 160 |
| `Sizes/Full` | `--size-full` | 999 |

### 4.1 CSS Tokens

```css
--size-00:   0px;
--size-01:   2px;
--size-02:   4px;
--size-03:   6px;
--size-04:   8px;
--size-05:   12px;
--size-06:   16px;
--size-07:   24px;
--size-08:   32px;
--size-09:   40px;
--size-10:   48px;
--size-11:   64px;
--size-12:   80px;
--size-13:   96px;
--size-14:   128px;
--size-15:   160px;
--size-full: 999px;
```

---

## 5. Shadows

### 5.1 Elevation

| Figma style | X | Y | Blur | Spread | Colour |
|-------------|---|---|------|--------|--------|
| `Elevation 1` | 0 | 0 | 4px | 0 | `rgba(0,0,0,0.16)` |
| `Elevation 2` | 0 | 2px | 8px | 0 | `rgba(0,0,0,0.15)` |
| `Elevation 3` | 0 | 4px | 12px | 0 | `rgba(0,0,0,0.30)` |
| `Elevation Widget` | 0 / 0 | 3px / 0 | 7px / 25px | 0 | `rgba(0,0,0,0.20)` — two shadows |

### 5.2 Legacy

Kept as legacy styles. **Don't use them in new designs** — Input Field and Drop Down no longer have a glow; focus is shown with the focus ring.

| Figma style | X | Y | Blur | Spread | Colour |
|-------------|---|---|------|--------|--------|
| `[Legacy] Input Focus` | 0 | 0 | 4px | 0 | `rgba(0,107,255,0.50)` |
| `[Legacy] Input Error` | 0 | 0 | 4px | 0 | `rgba(245,34,45,0.50)` |

### 5.3 Focus ring

Not a shadow: a child rectangle with a 2px `Blue/50 (Logo)` stroke, 1px outside the shape, corner radius matching the shape.

### 5.4 CSS Tokens

```css
/* Elevation */
--shadow-elevation-1:      0 0 4px rgba(0, 0, 0, 0.16);
--shadow-elevation-2:      0 2px 8px rgba(0, 0, 0, 0.15);
--shadow-elevation-3:      0 4px 12px rgba(0, 0, 0, 0.30);
--shadow-elevation-widget: 0 3px 7px rgba(0, 0, 0, 0.20), 0 0 25px rgba(0, 0, 0, 0.20);

/* Focus ring (not a shadow) */
/* outline: 2px solid #006BFF; outline-offset: 1px; */

/* Legacy — don't use in new designs */
--shadow-focus-legacy: 0 0 4px rgba(0, 107, 255, 0.50);
--shadow-error-legacy: 0 0 4px rgba(245, 34, 45, 0.50);
```

---

## 6. Breakpoints

| Breakpoint | Range (dp) | Columns | Gutters | Margin |
|------------|-----------|---------|---------|--------|
| Phone | 320–767 | 4 | 16 | 16 |
| Tablet | 768–1023 | 8 | 16 | 30 |
| Tablet Big | 1024–1279 | 12 | 16 | 50 |
| Desktop | 1280–1679 | 12 | 16 | 75 |
| Notebook | 1680+ | 12 (column width 105px) | 16 | 122px – ∞ |

> **Note:** Beyond 1680px, the grid keeps the same gutters and column width but is centred.

Figma frame: `Grids & Breakpoints` — node `6314:1194`.

---

## 7. Icons

Icons are visual symbols used to represent ideas, objects, or actions. They communicate messages at a glance, afford interactivity, and draw attention to important information. They are simple, modern and approachable, often with a touch of quirkiness.

**Library source:** `🌈 DS . HeroKit` — [Icons frame](https://www.figma.com/design/khiQfKjMEgUuFH3nkfPL3M/%F0%9F%8C%88-DS-.-HeroKit?node-id=3144-11339)

### 7.1 Properties

| Property | Value |
|----------|-------|
| Library | Custom — HeroKit |
| Count | 229 |
| Size | 24px (3 exceptions, see note) |
| Colour | One colour (1 exception, see note) |
| Format | SVG |

> **Note:** `Icon/Credit Card Sparkles`, `Icon/Mary Sparkles` and `Icon/Tools Sparkles` export larger than 24px (35×32 and 35×33), because the sparkles sit outside the 24px frame.

> **Note:** `Icon/Google Coloured` is the only multi-colour icon. It keeps the four Google brand colours (`#4285F4`, `#34A853`, `#FBBC05`, `#EA4335`) and must not be recoloured.

### 7.2 Alignment

When used next to text, icons should be center-aligned.

### 7.3 Categories

In Figma the icons are also grouped by use (e.g. Navigation, Chat, Jobs, Stat Center & Mary, Credit Cards, Social Media). Icons whose use is unknown sit in **Unsorted**.

Header icons with number badges (`Icon/Web Nav/…`) live on the Layouts page — see `HeroKit_Layouts.md`.

### 7.4 Icon List

| Name |
|------|
| Icon/Add Big |
| Icon/Add Small |
| Icon/Angles Left |
| Icon/Angles Right |
| Icon/Apple |
| Icon/Arrow Down |
| Icon/Arrow Turn Down Right Solid |
| Icon/Arrow Up |
| Icon/Arrow Up Right Outline |
| Icon/Arrow Up Right Solid |
| Icon/Atlas |
| Icon/Attach |
| Icon/Badge Outline |
| Icon/Badge Solid |
| Icon/Bell Outline |
| Icon/Bell Solid |
| Icon/Brush |
| Icon/Burger |
| Icon/Calendar |
| Icon/Calendar Meeting |
| Icon/Camera |
| Icon/Chat Bubble Outline |
| Icon/Chat Bubble Solid |
| Icon/Check Big |
| Icon/Check Flower |
| Icon/Check Small |
| Icon/Chevron Down |
| Icon/Chevron Left |
| Icon/Chevron Right |
| Icon/Chevron Up |
| Icon/Circle Add Outline |
| Icon/Circle Add Solid |
| Icon/Circle Arrow Down Outline |
| Icon/Circle Arrow Down Solid |
| Icon/Circle Arrow Left Outline |
| Icon/Circle Arrow Left Solid |
| Icon/Circle Arrow Right Outline |
| Icon/Circle Arrow Right Solid |
| Icon/Circle Check Solid |
| Icon/Circle Chevron Down Outline |
| Icon/Circle Chevron Down Solid |
| Icon/Circle Close Outline |
| Icon/Circle Close Solid |
| Icon/Circle Pause Outline |
| Icon/Circle Pause Solid |
| Icon/Circle Play Outline |
| Icon/Circle Play Solid |
| Icon/Circles Overlap Outline |
| Icon/Circles Overlap Solid |
| Icon/Close Big |
| Icon/Close Small |
| Icon/Coins |
| Icon/Copy Outline |
| Icon/Copy Solid |
| Icon/Counter Outline |
| Icon/Counter Solid |
| Icon/Credit Card |
| Icon/Credit Card Shield |
| Icon/Credit Card Sparkles |
| Icon/Credit Card Tick |
| Icon/Crown Outline |
| Icon/Crown Solid |
| Icon/Cup |
| Icon/Currency Banknote Solid |
| Icon/Currency Coins Outline |
| Icon/Currency Coins Solid |
| Icon/Currency Dollar Off |
| Icon/Currency Dollar On |
| Icon/Currency Euro |
| Icon/Currency Euro Bubble |
| Icon/Currency Lock |
| Icon/Dashboard |
| Icon/Diamond |
| Icon/Done |
| Icon/Done All |
| Icon/Door |
| Icon/Download |
| Icon/Edit Outline |
| Icon/Edit Solid |
| Icon/Edit Pen Outline |
| Icon/Edit Pen Solid |
| Icon/Exclamation |
| Icon/Exclamation Star Outline |
| Icon/Exclamation Star Solid |
| Icon/Exclamation Triangle Outline |
| Icon/Exclamation Triangle Solid |
| Icon/Eye Outline |
| Icon/Eye Solid |
| Icon/Eye Slash Outline |
| Icon/Eye Slash Solid |
| Icon/Face Happy |
| Icon/Face Neutral Outline |
| Icon/Face Neutral Solid |
| Icon/Face Sad Outline |
| Icon/Face Sad Solid |
| Icon/Face Smile Outline |
| Icon/Face Smile Solid |
| Icon/Facebook 1 |
| Icon/Facebook 2 |
| Icon/Facebook Messenger |
| Icon/File |
| Icon/Filters Outline |
| Icon/Filters Solid |
| Icon/Fire |
| Icon/Flag |
| Icon/Fullscreen Close |
| Icon/Fullscreen Open |
| Icon/GPS |
| Icon/Google |
| Icon/Google Coloured |
| Icon/Grid 2 Outline |
| Icon/Grid 2 Solid |
| Icon/Guarantee |
| Icon/Hand Outline |
| Icon/Hand Solid |
| Icon/Hand Wave |
| Icon/Headset Outline |
| Icon/Headset Solid |
| Icon/Heart Solid |
| Icon/Heartbroken |
| Icon/Hexagon Close |
| Icon/History |
| Icon/Hoover |
| Icon/Hourglass Solid |
| Icon/House Outline |
| Icon/House Solid |
| Icon/House Solid 2 |
| Icon/Image Outline |
| Icon/Image Solid |
| Icon/Info Circle |
| Icon/Info Circle Outline |
| Icon/Instagram 1 |
| Icon/Instagram 2 |
| Icon/Invoice |
| Icon/Ironing |
| Icon/Ironing No |
| Icon/Job Add |
| Icon/Job Check |
| Icon/Lightbulb Outline |
| Icon/Lightning Solid |
| Icon/Linkedin 1 |
| Icon/Linkedin 2 |
| Icon/Logo Heart |
| Icon/Logout |
| Icon/Magnifying Glass |
| Icon/Mail |
| Icon/Mail Outline |
| Icon/Mary |
| Icon/Mary Sparkles |
| Icon/Microphone |
| Icon/More Horizontal |
| Icon/Notebook Outline |
| Icon/Offer |
| Icon/Party |
| Icon/Percent |
| Icon/Person Walking Solid |
| Icon/Pets |
| Icon/Pets No |
| Icon/Phone |
| Icon/Phone Mobile |
| Icon/Phone Talking |
| Icon/Photocamera |
| Icon/Pin |
| Icon/Pin User |
| Icon/Pinterest |
| Icon/Power |
| Icon/Quote Left Solid |
| Icon/Radio |
| Icon/Ranking Star |
| Icon/Referral Club |
| Icon/Refresh |
| Icon/Remove Big |
| Icon/Remove Small |
| Icon/Repeat Solid |
| Icon/Review Outline |
| Icon/Review Solid |
| Icon/Ruler |
| Icon/Send |
| Icon/Settings |
| Icon/Share Outline |
| Icon/Share Solid |
| Icon/Skroutz |
| Icon/Sort |
| Icon/Sparkles Solid |
| Icon/Square List |
| Icon/Square Plus Regular |
| Icon/Square Plus Solid |
| Icon/Star Empty |
| Icon/Star Full |
| Icon/Star Half Empty |
| Icon/Stats |
| Icon/Thumbs Down Outline |
| Icon/Thumbs Down Solid |
| Icon/Thumbs Up Outline |
| Icon/Thumbs Up Solid |
| Icon/Thumbtack Outline |
| Icon/Thumbtack Solid |
| Icon/TikTok |
| Icon/TikTok 2 |
| Icon/Toggle Off Outline |
| Icon/Toggle Off Solid |
| Icon/Toggle On Outline |
| Icon/Toggle On Solid |
| Icon/Tool Solid |
| Icon/Toolbox Outline |
| Icon/Toolbox Solid |
| Icon/Tools |
| Icon/Tools Outline |
| Icon/Tools Sparkles |
| Icon/Trash Can Outline |
| Icon/Trash Can Solid |
| Icon/Trending Down |
| Icon/Trending Up |
| Icon/Truck |
| Icon/Update |
| Icon/Upload |
| Icon/User Circle Outline |
| Icon/User Circle Solid |
| Icon/User Outline |
| Icon/User Plus Outline |
| Icon/User Plus Solid |
| Icon/User Pro Outline |
| Icon/User Pro Solid |
| Icon/User Solid |
| Icon/Users Outline |
| Icon/Users Solid |
| Icon/Washing Machine |
| Icon/Watch Later |
| Icon/YouTube |

---

## 8. Illustrations

Illustration components live in the `Illustrations` frame (node `6315:44534`).

| Component | Values |
|-----------|--------|
| `Illustration/Services/Douleutaras` · `Illustration/Services/YourHero` | `Name`: service categories (cleaning, renovations, removals, etc.) · `State`: `off` · `on` |
| `Illustration/Services/Dashboard` | `Category`: 8 service categories |
| `Illustration/Categories` | `Category`: DoorsWindows · Events · HomeAppliances · Removals · Renovations · Technical Jobs · Cleaning · Urgent Jobs · External · `Bg`: `Blue` · `White` |
| `Illustration/Countries` | `Country`: GR · UK · CY · IE · PT · `Size`: `Small` · `Big` |
| `Illustration/Numbers` | `Number`: 1 · 2 · 3 |
| `Illustration/Moneyback Guarantee` | Single illustration |
| `Mary` | `Variation`: `Normal` · `Sad` · `Happy` · `Notifications` |
| `icon/Payment Methods` | `Method`: Klarna · Card · Cash · `Size`: `Big` · `Medium` · `Small` |
| `AI _ Sparkle` · `AI _ Circle` | AI marks (`Variation` — `AI _ Circle`: `Gray` · `White`) |
| `Illustration/round/…` | Round spot illustrations (single components) |

> ⚠️ Naming to clean up: `icon/Payment Methods` (lowercase), Greek-transliterated option names on the Services sets.
