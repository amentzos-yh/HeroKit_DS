# HeroKit — Styleguide

> **Version:** 1.0
> **Last updated:** 20 April 2026

---

## Table of Contents

1. [Logo](#1-logo)
2. [Colours](#2-colours)
3. [Typography](#3-typography)
4. [Sizes](#4-sizes)
5. [Shadows](#5-shadows)
6. [Breakpoints](#6-breakpoints)
7. [Icons](#7-icons)

---

## 1. Logo

The product operates under three brand names depending on market. All share the same icon mark; the wordmark and colour treatment differ per brand.

| Brand | Market |
|-------|--------|
| **Douleutaras** | Greece, Cyprus |
| **YourPro** | Ireland |
| **HourHero** | Parent company |

The logo appears in two additional colour variations under Douleutaras and YourPro — **orange** for the Pros App and **turquoise** for the Cleaners App. These variations do not apply to HourHero.

### 1.1 Variants

The Logo component in HeroKit has four properties that combine to produce all variants:

| Property | Values |
|----------|--------|
| `Logo` | `Douleutaras` · `YourPro` · `YourHero` |
| `Light Mode` | `On` (light backgrounds) · `Off` (dark backgrounds) |
| `Wordmark` | `On` · `Off` |
| `Tagline` | `On` · `Off` |
| `Customer/Pro` | `On` (customer-facing) · `Off` (pro-facing) |

---

---

## 2. Colours

The colour system is built on four palettes — **Neutral**, **Blue** (primary/brand), **Purple** (accent), and **Yellow** (highlight/trial). Each palette uses HSL-based steps where lower numbers are lighter and higher numbers are darker.

---

### 2.1 Neutral — Saturated Shades `H209–238`

| Step | Hex | H | S | L |
|------|-----|---|---|---|
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
| 95 | `#111113` | 235 | 004 | 007 |

---

### 2.2 Blue / Primary `H213–240`

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

---

### 2.3 Purple / Secondary `H238–240`

| Step | Hex | H | S | L |
|------|-----|---|---|---|
| 10 | `#F4F4F9` | 240 | 029 | 097 |
| 20 | `#B1B2D5` | 238 | 030 | 076 |
| 30 | `#6466AA` | 238 | 029 | 053 |
| 40 | `#202383` | 238 | 061 | 032 |

---

### 2.4 Yellow / Tertiary `H047–050`

| Step | Hex | H | S | L |
|------|-----|---|---|---|
| 10 (Trial) | `#FFFCEB` | 050 | 100 | 096 |
| 15 | `#FFF8D6` | 050 | 100 | 092 |
| 20 | `#FFF2B2` | 050 | 100 | 085 |
| 30 | `#FFEA80` | 050 | 100 | 075 |
| 50 | `#FFC700` | 047 | 100 | 050 |

### 2.5 Orange / Warning `H033–040`

| Step | Hex | H | S | L |
|------|-----|---|---|---|
| 10 | `#FEFBF5` | 040 | 082 | 098 |
| 30 | `#FBEBC2` | 040 | 088 | 087 |
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
| 40 | `#F27B74` | 002 | 083 | 070 |
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
| 40 | `#84C3DD` | 194 | 057 | 069 |

---

### 2.9 Turquoise `H190–195`

| Step | Hex | H | S | L |
|------|-----|---|---|---|
| 10 | `#F9FCFD` | 195 | 050 | 098 |
| 20 | `#A6DFEB` | 190 | 063 | 079 |
| 30 | `#4CBFD7` | 190 | 063 | 057 |
| 40 | `#00A4C6` | 190 | 100 | 039 |

> **Note:** Green, Mint, and Turquoise are currently used sparingly across the product. These three scales are candidates to be merged into a single unified palette that will replace Purple as the secondary colour in a future update.

---

### 2.10 Gradients

Four linear gradients used across the product for decorative surfaces, badges, and premium UI elements.

| Name | Stops | Direction |
|------|-------|-----------|
| Purple | `#2E306B` → `#202383` | Top to bottom |
| Blue | `#006BFF` → `#00A4C6` | Diagonal (≈10°) |
| Gold Smooth | `#FFC700` → `#FFF2B2` → `#FFC700` | Diagonal (135°) |
| Gold Sharp | `#FFD11A` → `#FFF5CC` → `#FFD11A` | Diagonal (135°), tight midpoint |

#### CSS

```css
--gradient-purple:     linear-gradient(180deg, #2E306B 0%, #202383 100%);
--gradient-blue:       linear-gradient(10deg, #006BFF 0%, #00A4C6 100%);
--gradient-gold-smooth: linear-gradient(135deg, #FFC700 23%, #FFF2B2 50%, #FFC700 79%);
--gradient-gold-sharp:  linear-gradient(135deg, #FFD11A 40%, #FFF5CC 50%, #FFD11A 60%);
```

---

### 3.1 Typeface

**IBM Plex Sans**

```
Font family:  'IBM Plex Sans', sans-serif
Font stack:   font-family: 'IBM Plex Sans', 'Helvetica Neue', Arial, sans-serif;
Weights:      400 (Regular) · 600 (SemiBold)
```

---

### 3.2 Type Scale

#### Headings

| Token | Weight | Size | Line-height | Letter-spacing |
|-------|--------|------|-------------|----------------|
| `heading/42` | SemiBold (600) | 42px | 130% | 0% |
| `heading/36` | SemiBold (600) | 36px | 130% | 0% |
| `heading/28-semibold` | SemiBold (600) | 28px | 132% | 0% |
| `heading/28-regular` | Regular (400) | 28px | 132% | 0% |
| `heading/24-semibold` | SemiBold (600) | 24px | 138% | 0% |
| `heading/24-regular` | Regular (400) | 24px | 138% | 0% |
| `heading/20-semibold` | SemiBold (600) | 20px | 142% | 0% |
| `heading/20-regular` | Regular (400) | 20px | 142% | 0% |

#### Body

| Token | Weight | Size | Line-height | Letter-spacing |
|-------|--------|------|-------------|----------------|
| `body/18-semibold` | SemiBold (600) | 18px | 150% | 0% |
| `body/18-regular` | Regular (400) | 18px | 150% | 0% |
| `body/16-semibold` | SemiBold (600) | 16px | 150% | 0% |
| `body/16-regular` | Regular (400) | 16px | 150% | 0% |
| `body/14-semibold` | SemiBold (600) | 14px | 150% | 0% |
| `body/14-regular` | Regular (400) | 14px | 150% | 0% |
| `body/14-caps` | Regular (400) | 14px | 150% | 3% — UPPERCASE |
| `body/12-semibold` | SemiBold (600) | 12px | 160% | 0.5% |
| `body/12-regular` | Regular (400) | 12px | 160% | 0.5% |
| `body/12-caps` | Regular (400) | 12px | 160% | 5% — UPPERCASE |

#### Labels

| Token | Weight | Size | Line-height | Letter-spacing |
|-------|--------|------|-------------|----------------|
| `label/10-semibold` | SemiBold (600) | 10px | 160% | 2% |
| `label/10-regular` | Regular (400) | 10px | 160% | 2% |
| `label/9-regular` | Regular (400) | 9px | 160% | 3% |

---

### 3.3 Usage Notes

1. Type colour should be carefully considered, with legibility and accessibility as paramount concerns. Keep type colour neutral in running text.
2. Other use cases for coloured type are code snippets, warnings, alerts, etc.

---

## 4. Sizes

The size scale can be applied to `margin`, `padding`, and `border-radius` properties, as well as to both vertical and horizontal edges. The token takes the place of the values normally assigned to these properties.

| Name | Value (px) |
|------|-----------|
| 00 | 0 |
| 01 | 2 |
| 02 | 4 |
| 03 | 6 |
| 04 | 8 |
| 05 | 12 |
| 06 | 16 |
| 07 | 24 |
| 08 | 32 |
| 09 | 40 |
| 10 | 48 |
| 11 | 64 |
| 12 | 80 |
| 13 | 96 |
| 14 | 128 |
| 15 | 160 |
| Full | 999 |

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

| Name | X | Y | Blur | Spread | Colour |
|------|---|---|------|--------|--------|
| Elevation 1 | 0 | 0 | 4px | 0 | `rgba(0,0,0,0.16)` |
| Elevation 2 | 0 | 2px | 8px | 0 | `rgba(0,0,0,0.15)` |
| Elevation 3 | 0 | 4px | 12px | 0 | `rgba(0,0,0,0.30)` |

### 5.2 Focus Effects

| Name | X | Y | Blur | Spread | Colour |
|------|---|---|------|--------|--------|
| Input Focus | 0 | 0 | 4px | 0 | `rgba(0,107,255,0.50)` |
| Input Error | 0 | 0 | 4px | 0 | `rgba(245,34,45,0.50)` |

### 5.3 CSS Tokens

```css
/* Elevation */
--shadow-elevation-1: 0 0 4px rgba(0, 0, 0, 0.16);
--shadow-elevation-2: 0 2px 8px rgba(0, 0, 0, 0.15);
--shadow-elevation-3: 0 4px 12px rgba(0, 0, 0, 0.30);

/* Focus */
--shadow-focus: 0 0 4px rgba(0, 107, 255, 0.50);
--shadow-error: 0 0 4px rgba(245, 34, 45, 0.50);
```

---

## 6. Breakpoints

| Breakpoint | Range (dp) | Columns | Gutters | Margin |
|------------|-----------|---------|---------|--------|
| Phone | 320–767 | 4 | 16 | 16 |
| Tablet | 768–1023 | 8 | 16 | 30 |
| Tablet Big | 1024–1279 | 12 | 16 | 50 |
| Desktop | 1280–1679 | 12 | 16 | 75 |
| Notebook | 1680+ | 12 | 16 | — |

> **Note:** Beyond 1680px, the grid keeps the same gutters and column width but is centred.

---

## 7. Icons

Icons are visual symbols used to represent ideas, objects, or actions. They communicate messages at a glance, afford interactivity, and draw attention to important information.

**Library source:** `🌈 DS — Product` — [Icons frame](https://www.figma.com/design/khiQfKjMEgUuFH3nkfPL3M/%F0%9F%8C%88-DS-%E2%80%94-Product?node-id=3144-11339)

### 7.1 Properties

| Property | Value |
|----------|-------|
| Library | Custom — HeroKit |
| Size | 24px |
| Format | SVG |

### 7.2 Alignment

When used next to text, icons should be center-aligned.

### 7.3 Icon List

| Name |
|------|
| Icon/Add Big |
| Icon/Add Small |
| Icon/Apple |
| Icon/Arrow Down |
| Icon/Arrow Up |
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
| Icon/Chat Bubble |
| Icon/Chat Bubble Outline |
| Icon/Check Big |
| Icon/Check Flower |
| Icon/Check Small |
| Icon/Chevron Down |
| Icon/Chevron Left |
| Icon/Chevron Right |
| Icon/Chevron Up |
| Icon/Circle Arrow Down Outline |
| Icon/Circle Arrow Down Solid |
| Icon/Circle Arrow Right Outline |
| Icon/Circle Arrow Right Solid |
| Icon/Circle Check Solid |
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
| Icon/Currency Coins |
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
| Icon/Exclamation |
| Icon/Exclamation Star Outline |
| Icon/Exclamation Star Solid |
| Icon/Exclamation Triangle |
| Icon/Eye Outline |
| Icon/Eye Solid |
| Icon/Eye Solid Slash |
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
| Icon/Google |
| Icon/Google Coloured |
| Icon/GPS |
| Icon/Guarantee |
| Icon/Hand Outline |
| Icon/Hand Solid |
| Icon/Hand Wave |
| Icon/Heart Solid |
| Icon/Heartbroken |
| Icon/Hexagon Close |
| Icon/History |
| Icon/Hoover |
| Icon/Hourglass Solid |
| Icon/House |
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
| Icon/Logout |
| Icon/Magnifying Glass |
| Icon/Mail |
| Icon/Mail Outline |
| Icon/Mary |
| Icon/Mary Sparkles |
| Icon/Microphone |
| Icon/More Horizontal |
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


