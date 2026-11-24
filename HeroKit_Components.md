# HeroKit — Components

> **Version:** 1.6
> **Last updated:** 24 November 2026
> **Source:** `🌈 DS . HeroKit` → page `✨ Updated Components`. Figma is the source of truth when this doc and Figma disagree.
> **Naming:** colours and text styles use their Figma names (`Shades/80`, `Body/14 Semibold`). Hex values are given for reference.
> Layouts (Header, Footer, Modals, Loaders, Nav bars) are documented in `HeroKit_Layouts.md`.

---

## Table of Contents

1. [Accordion](#1-accordion)
2. [AI Form](#2-ai-form)
3. [Alert](#3-alert)
4. [App Notifications](#4-app-notifications)
5. [Badge _ Lila](#5-badge-_-lila)
6. [Banner](#6-banner)
7. [Breadcrumb](#7-breadcrumb)
8. [Button](#8-button)
9. [Button Group](#9-button-group)
10. [Button Segmented](#10-button-segmented)
11. [Card _ Selection](#11-card-_-selection)
12. [Checkbox](#12-checkbox)
13. [Chip _ Choice](#13-chip-_-choice)
14. [Counter](#14-counter)
15. [Date Picker](#15-date-picker)
16. [Drop Down](#16-drop-down)
17. [Input _ Phone](#17-input-_-phone)
18. [Input _ Price](#18-input-_-price)
19. [Input _ Text](#19-input-_-text)
20. [Input _ Text _ Chat](#20-input-_-text-_-chat)
21. [Pagination](#21-pagination)
22. [Progress Bar](#22-progress-bar)
23. [Purple Background Curve](#23-purple-background-curve)
24. [Quick Action Button](#24-quick-action-button)
25. [Radio Button](#25-radio-button)
26. [Search Bar](#26-search-bar)
27. [Snackbar](#27-snackbar)
28. [Tabs](#28-tabs)
29. [Toggle](#29-toggle)
30. [Toggle Button](#30-toggle-button)
31. [Tooltip](#31-tooltip)

---

## Shared conventions

| Rule | Value |
|------|-------|
| Focus ring | Child rectangle, 2px `Blue/50 (Logo)` stroke, 1px outside the shape, radius matches the shape. Not a drop shadow. |
| Hover / Pressed tint | `Blue/50 (Logo) 5%` / `Blue/50 (Logo) 10%` over a white layer (`Shades/0 (White)`). Exception: Button Secondary / Tertiary use the tint with no white layer. |
| Selected in single-select groups | Not clickable: no Hover / Pressed. Focus is kept for keyboard users. |
| Disabled in single-select groups | Every option looks the same, selected or not. |
| Semibold text | `Shades/95 (Black)` |

---

## 1. Accordion

Expands and collapses sections of content. Two icon styles: a leading chevron (lists, price lists, nested info) and a trailing +/− (FAQ).

---

### 1.1 Components

| Component | Node | Description |
|-----------|------|-------------|
| `Accordion` | `7861:51551` | Group. Put items in the `Items` slot. |
| `Accordion _ Item _ Contained` | `7846:33873` | Item for accordions inside a container with a stroke (card, modal) |
| `Accordion _ Item _ Flush` | `8142:5270` | Item for accordions placed directly on the page |
| `Accordion _ Carousel` | `7847:33678` | FAQ carousel. Goes in an item's `Content` slot. |
| `Accordion _ Carousel _ Card` | `7851:33777` | FAQ card used in the carousel and in the full-answer modal |

---

### 1.2 Properties

**Accordion**

| Property | Type | Values / Default |
|----------|------|------------------|
| `Padding` | Variant | `Contained` · `Flush` |
| `Items` | Slot | Accordion items |

**Accordion _ Item _ Contained / Flush** — 20 variants each

| Property | Type | Values / Default |
|----------|------|------------------|
| `State` | Variant | `Closed` · `Open` |
| `Icon` | Variant | `Chevron` · `Plus-Minus` |
| `Interaction` | Variant | `Default` · `Hover` · `Focus` · `Pressed` · `Disabled` |
| `Title` | Text | `Accordion title` |
| `Content` | Slot | Any content: text, lists, links, or `Accordion _ Carousel` |

---

### 1.3 Anatomy & Specs

| Element | Contained | Flush |
|---------|-----------|-------|
| Header padding (V / H) | 12px / 16px | 12px / 0 |
| Gap (icon ↔ title) | 8px | 8px |
| Closed height | 48px | 48px |
| Divider | Bottom stroke `Shades/30` | Bottom stroke `Shades/30` |
| Background | `Shades/0 (White)` | `Shades/0 (White)` |

- **Title** — `Body/16 Semibold`. Titles are always Semibold; there is no weight property.
- **Content** — `Body/16`, `Shades/80`.
- **Icon** — `Icon=Chevron`: leading `Icon/Chevron Right`. `Icon=Plus-Minus`: trailing +/−.

---

### 1.4 States

No background change on any state.

| Interaction | Title colour | Content colour |
|-------------|--------------|----------------|
| `Default` | `Shades/95 (Black)` `#111113` | `Shades/80` `#3A3D46` |
| `Hover` | `Blue/50 (Logo)` `#006BFF` | `Shades/80` |
| `Focus` | `Blue/50 (Logo)` + focus ring | `Shades/80` |
| `Pressed` | `Blue/70` `#042CC8` | `Shades/80` |
| `Disabled` | `Shades/40` `#B2BBC7` | `Shades/40` |

---

### 1.5 Accordion _ Carousel _ Card

| Property | Type | Values / Default |
|----------|------|------------------|
| `State` | Variant | `Preview` · `Full` |
| `Interaction` | Variant | `Default` · `Hover` · `Focus` · `Pressed` (Preview only) |
| `Title` | Text | `Question title` |
| `Link label` | Text | `Read more` (text property so it can be translated) |
| `Content` | Slot | Answer content |

| Spec | Value |
|------|-------|
| Preview size | 320 × 400px desktop · 260px wide mobile (fill the container) |
| Padding / gap | 24px / 16px |
| Corner radius | 8px |
| Border | 1px `Shades/40` |
| Hover border | `Blue/40` |
| Focus | 2px `Blue/50 (Logo)` ring |
| Pressed border | `Blue/70` |
| Overflow | Content fades out at the bottom (gradient layer) |

- **Preview** — the whole card is the tap target. It opens `State=Full` in a modal.
- **Full** — title + content, no card chrome. Place it in the `Modal _ Web` / `Modal _ App` content slot. The modal header has no title.

**Accordion _ Carousel** — `Breakpoint=Desktop`: `Pagination _ PrevNext` arrows, 320px cards, 16px gap. `Breakpoint=Mobile`: swipe, no arrows, 260px cards with the next card peeking.

---

### 1.6 Usage

1. **Contained** — use inside a container with a stroke (card, modal). Fill the `Items` slot with `Accordion _ Item _ Contained`.
2. **Flush** — use when the accordion sits directly on the page. Fill the `Items` slot with `Accordion _ Item _ Flush`.
3. Don't mix the two item types in one accordion: titles, icons and content won't line up.
4. **Plus-Minus** is mostly used for FAQs, with `Accordion _ Carousel` in the content.

---

## 2. AI Form

Prompt field for AI features. Gradient ring around a white field, with a sparkle icon and a Send button.

---

### 2.1 Properties

| Property | Type | Values / Default |
|----------|------|------------------|
| `Variation` | Variant | `Default` (one line) · `Expanded` (multi-line) |
| `Breakpoint` | Variant | `Mobile` · `Desktop` |
| `State` | Variant | `Default` · `Hover` · `Filled` · `Disabled` · `Focused` |
| `Placeholder Text` | Text | `Placeholder text` |
| `Prompt` | Text | Prompt copy |

Total variants: **12**

---

### 2.2 Specs

| Spec | Value |
|------|-------|
| Ring | `Gradient/AI`, 2px padding around the field |
| Height — Default | 44px mobile · 40px desktop |
| Height — Expanded (minimum) | 108px mobile (3 lines) · 80px desktop (2 lines) |
| Corner radius | Full (999px) in Default |
| Text | `Body/16` — placeholder `Shades/60`, typed text `Shades/80` |
| Sparkle segment | `Shades/10` background |

---

### 2.3 States

| State | Field border | Placeholder / text | Send icon |
|-------|--------------|--------------------|-----------|
| `Default` | `Shades/40` | `Shades/60` | `Shades/40` |
| `Hover` | `Blue/60` | `Shades/60` | `Shades/40` |
| `Filled` | `Shades/40` | `Shades/80` | `Blue/50 (Logo)` |
| `Focused` (Expanded) | `Shades/40` + focus ring | `Shades/80` | `Blue/50 (Logo)` |
| `Disabled` | `Shades/40`, field `Shades/10` | `Shades/50` | `Shades/50` (sparkle also `Shades/50`) |

---

### 2.4 Usage

1. Send is enabled only when the field has text.
2. When active, the field opens to a minimum height: mobile 3 lines (108px), desktop 2 lines (80px). It grows 24px per line.
3. Past a 134px text area (mobile 140px, desktop 136px) it scrolls.

---

### 2.5 Figma

| Resource | Node |
|----------|------|
| Component set | `AI Form` — node `8011:35849` (frame "AI Text Input") |

---

## 3. Alert

An inline notification that communicates status, feedback, or required attention within the flow of a page. Used for non-blocking messages such as confirmations, warnings, and errors related to the user's current task.

---

### 3.1 Properties

| Property | Type | Values / Default |
|----------|------|------------------|
| `Breakpoint` | Variant | `Mobile` · `Desktop` |
| `Kind` | Variant | `Info` · `Success` · `Warning` · `Alert` |
| `Title` | Boolean | `true` — shows / hides the title |
| `CTA` | Boolean | `true` — shows / hides the Action link |
| `Close` | Boolean | `true` — shows / hides the Close Container |
| `Title Text` | Text | `Notification title` |
| `Text` | Text | Message copy |
| `CTA Label` | Text | `Action` |

Total variants: **8** (4 kinds × 2 breakpoints)

---

### 3.2 Anatomy

```
Alert Notice
└── Container
    ├── Icon Container      16×21 · kind icon 16px, centre/centre
    ├── Content
    │   ├── Text Container  Title + Message
    │   └── Action
    └── Close Container     16×21 · Icon/Close Big 16px, centre/centre
```

- **Alert Notice** — 1px border (inside), tinted background per kind, no shadow
- **Icon Container / Close Container** — 21px high to match the line height of the title's first line (`Body/14 Semibold`, 150%), so both icons align to the centre of the first text line
- **Text Container** — Title (`Body/14 Semibold`) stacked on Message (`Body/14`), no gap
- **Action** — text link, `Body/14`, `Blue/50 (Logo)`, underlined

---

### 3.3 Kind → Tokens

| Kind | Icon | Icon colour | Background | Border |
|------|------|-------------|------------|--------|
| `Info` | `Icon/Info Circle` | `Blue/40` `#4297FF` | `Blue/10` `#E5F2FF` | `Blue/40` `#4297FF` |
| `Success` | `Icon/Circle Check Solid` | `Green/30` `#1FC198` | `Green/10` `#E6F4F1` | `Green/30` `#1FC198` |
| `Warning` | `Icon/Exclamation Triangle Solid` | `Orange/50` `#EF9E00` | `Yellow/10` `#FFFCEB` | `Orange/50` `#EF9E00` |
| `Alert` | `Icon/Circle Close Solid` | `Coral/50` `#E65651` | `Coral/10` `#FEF8F8` | `Coral/40` `#F27874` |

**Shared across all kinds**

| Element | Token |
|---------|-------|
| Title | `Body/14 Semibold`, `Shades/90` `#232429` |
| Message | `Body/14`, `Shades/80` `#3A3D46` |
| Action | `Body/14`, `Blue/50 (Logo)` `#006BFF`, underlined |
| Close icon | `Shades/80` `#3A3D46` |
| Border | 1px, inside |
| Border-radius | `Sizes/04` (8px) |

---

### 3.4 Breakpoint Specs

| Spec | Mobile | Desktop |
|------|--------|---------|
| Padding | `Sizes/06` (16px) all sides | `Sizes/06` (16px) all sides |
| Gap (icon ↔ content ↔ close) | `Sizes/05` (12px) | `Sizes/05` (12px) |
| Content layout | Stacked — Action below the text | Inline — Action to the right of the text, top-aligned |
| Gap (text ↔ action) | `Sizes/06` (16px) | `Sizes/06` (16px) |
| Icon alignment | Centred on the first text line | Centred on the first text line |
| Documentation width | 328px | 690px |

---

### 3.5 Usage

1. **Width** — In the design system file, variants are drawn at fixed widths (328px mobile, 690px desktop) for documentation. **In product use, set the Alert to fill its container.**
2. **Dismissible** — Show or hide the Close Container with the `Close` boolean, depending on whether the alert should be dismissible.
3. **Title and CTA** — Show or hide the title and the Action link with the `Title` and `CTA` booleans.
4. **Link in text** — The link can also sit inline at the end of the message text instead of as a separate Action. It keeps the Action style: `Body/14`, `Blue/50 (Logo)`, underlined.

   > Example: *"HTML has several restrictions that developers must adhere to in order to ensure proper functionality. [Action]"* — shown with `Title`, `CTA` and `Close` off.
   >
   > **Note:** Not available as a component option in Figma — documented here only.

---

### 3.6 Figma

| Resource | Node |
|----------|------|
| Component set | `Alert Notice` — node `863:23836` |

---

## 4. App Notifications

Three app-only notification components, grouped under the "Alerts" label on the page. They are older components and still use archived colours (see 4.4).

---

### 4.1 App _ Snackbar

| Property | Type | Values / Default |
|----------|------|------------------|
| `Kind` | Variant | `No CTA` · `Short CTA` · `Long CTA` · `Inline CTA` |
| `Close` | Boolean | `false` |
| `Text` | Text | Message copy |
| `CTA Label` | Text | `Action` |

| Spec | Value |
|------|-------|
| Width | 328px |
| Padding / gap | 12px / 8px |
| Corner radius | 4px |
| Background | `#232323` (no token) |
| Message | `Body/14`, `Shades/0 (White)` |
| CTA | `Body/14 Semibold`, `Blue/30` |
| Shadow | `(Archived) Elevation 1` |

---

### 4.2 App _ Notification Banner

| Property | Type | Values / Default |
|----------|------|------------------|
| `Variation` | Variant | `Default` |
| `Text` | Text | Notification copy |

| Spec | Value |
|------|-------|
| Size | 328 × 56px |
| Padding / gap | 16px / 12px |
| Corner radius | 4px |
| Icon | `Icon/Pin User`, `Blue/40` |
| Text | `Body/14 Bold`, `[Archived] Shades/70` |

**Behaviour:** Incoming notifications sit on top of the header and the rest of the content. They move in and out from the top, stay on screen for 7 seconds and can be dismissed with a swipe. They can appear on top of banners.

---

### 4.3 App _ Top Banner

| Property | Type | Values / Default |
|----------|------|------------------|
| `Variation` | Variant | `Default` |
| `Text` | Text | `You have a new job!` |
| `CTA 1` / `CTA 2` | Text | `DISMISS` / `VIEW` |
| `Icon` · `CTAs` · `CTA 3` | Boolean | `true` |

| Spec | Value |
|------|-------|
| Size | 360 × 88px |
| Padding | 16px |
| Background | `#212486` (no token) |
| Text | `Body/16`, `[Archived] Shades/10 White` |
| CTAs | `Body/16 Semibold`, `#A6CBFF` (no token) |

**Behaviour:** Animates in from the top of the layout, on top of the header. Stays until the user dismisses it. Doesn't follow the user to other pages or modals. Only one at a time; a new banner dismisses the previous one.

---

### 4.4 Open items

> ⚠️ Still use some archived or hard-coded colours (`[Archived] Shades/70`, `#232323`, `#212486`, `#A6CBFF`), `(Archived) Elevation 1`, and `App _ Top Banner` contains an `[OBSOLETE] icon/Bell`. `App _ Notification Banner` uses a `Body/14 Bold` style that isn't in the current type scale.

---

### 4.5 Figma

| Resource | Node |
|----------|------|
| `App _ Snackbar` | node `4274:13043` |
| `App _ Notification Banner` | node `4540:46882` |
| `App _ Top Banner` | node `4517:56365` |

---

## 5. Badge _ Lila

Small label with an icon, used for short hints and statuses.

---

### 5.1 Properties

| Property | Type | Values / Default |
|----------|------|------------------|
| `Variation` | Variant | `Info` · `Tip` · `Warning` |
| `Icon` | Boolean | `true` |
| `Text Label` | Text | `TEXT LABEL` |

Total variants: **3**

---

### 5.2 Variations

| Variation | Background | Icon | Icon colour |
|-----------|-----------|------|-------------|
| `Info` | `Blue/10` | `Icon/Info Circle Outline` | `Blue/50 (Logo)` |
| `Tip` | `Yellow/20` | `Icon/Lightbulb Outline` | `Orange/60` |
| `Warning` | `Coral/15` | `Icon/Exclamation Triangle Outline` | `Coral/50` |

---

### 5.3 Specs

| Spec | Value |
|------|-------|
| Height | 24px |
| Padding (V / H) | 4px / 6px |
| Gap | 4px |
| Corner radius | 4px |
| Icon | 12px |
| Label | `Label/10`, `Shades/80` |

---

### 5.4 Figma

| Resource | Node |
|----------|------|
| Component set | `Badge _ Lila` — node `7533:45778` |

---

## 6. Banner

A full-width notification that communicates high-priority information at a page level. Unlike Alerts, Banners are not inline — they sit at the top of the page and are seen before any content.

---

### 6.1 Properties

| Property | Type | Values / Default |
|----------|------|------------------|
| `Breakpoint` | Variant | `Mobile` · `Desktop` |
| `Kind` | Variant | `Info` · `Success` · `Warning` · `Alert` |
| `Title` | Boolean | `true` — shows / hides the title |
| `CTA` | Boolean | `true` — shows / hides the Action link |
| `Close` | Boolean | `true` — shows / hides the Close Container |
| `Title Text` | Text | `Notification title` |
| `Text` | Text | Message copy |
| `CTA Label` | Text | `Action` |

Total variants: **8** (4 kinds × 2 breakpoints)

---

### 6.2 Anatomy

```
Banner Notice
└── Container
    ├── Icon Container      16×21 · kind icon 16px, centre/centre
    ├── Content
    │   ├── Text Container  Title + Message
    │   └── Action
    └── Close Container     16×21 · Icon/Close Big 16px, centre/centre
```

- **Banner Notice** — tinted background per kind, no border, no corner radius, no shadow
- **Icon Container / Close Container** — 21px high to match the line height of the title's first line (`Body/14 Semibold`, 150%), so both icons align to the centre of the first text line
- **Text Container** — Title (`Body/14 Semibold`) stacked on Message (`Body/14`), no gap
- **Action** — text link, `Body/14`, `Blue/50 (Logo)`, underlined

---

### 6.3 Kind → Tokens

| Kind | Icon | Icon colour | Background |
|------|------|-------------|------------|
| `Info` | `Icon/Info Circle` | `Blue/40` `#4297FF` | `Blue/10` `#E5F2FF` |
| `Success` | `Icon/Circle Check Solid` | `Green/30` `#1FC198` | `Green/10` `#E6F4F1` |
| `Warning` | `Icon/Exclamation Triangle Solid` | `Orange/50` `#EF9E00` | `Yellow/10` `#FFFCEB` |
| `Alert` | `Icon/Circle Close Solid` | `Coral/50` `#E65651` | `Coral/10` `#FEF8F8` |

**Shared across all kinds**

| Element | Token |
|---------|-------|
| Title | `Body/14 Semibold`, `Shades/90` `#232429` |
| Message | `Body/14`, `Shades/80` `#3A3D46` |
| Action | `Body/14`, `Blue/50 (Logo)` `#006BFF`, underlined |
| Close icon | `Shades/80` `#3A3D46` |
| Border | None |
| Border-radius | `Sizes/00` (0px) |

---

### 6.4 Breakpoint Specs

| Spec | Mobile | Desktop |
|------|--------|---------|
| Padding | `Sizes/06` (16px) all sides | `Sizes/06` (16px) all sides |
| Gap (icon ↔ content ↔ close) | `Sizes/05` (12px) | `Sizes/05` (12px) |
| Content layout | Stacked — Action below the text | Inline — Action to the right of the text, top-aligned |
| Gap (text ↔ action) | `Sizes/06` (16px) | `Sizes/06` (16px) |
| Icon alignment | Centred on the first text line | Centred on the first text line |
| Documentation width | 328px | 690px |

---

### 6.5 Variations

| Variation | `Title` | `CTA` | `Close` | Description |
|-----------|---------|-------|---------|-------------|
| Text only | Off | Off | Off | Message only — no title, no action, no close button |
| Title | On | Off | Off | Title and message — no action, no close button |
| Title & Close Button | On | Off | On | Title, message and close button |
| Title, CTA & Close Button | On | On | On | Title, message, action link and close button |
| Link inline text | Off | Off | Off | Message with an inline link at the end — see 6.6 Usage, item 6 |

---

### 6.6 Usage

1. **Width** — In the design system file, variants are drawn at fixed widths (328px mobile, 690px desktop) for documentation. **In product use, set the Banner to fill its container.**
2. Banners remain on screen until dismissed by the user. If there is no close button, the banner cannot be dismissed — use this variation to display a persistent status.
3. Banners do not follow the user to other pages or modals.
4. If a new banner appears, the previous one is dismissed automatically.
5. Only one banner can be displayed at a time.
6. **Link in text** — The link can also sit inline at the end of the message text instead of as a separate Action. It keeps the Action style: `Body/14`, `Blue/50 (Logo)`, underlined.

   > Example: *"HTML has several restrictions that developers must adhere to in order to ensure proper functionality. [Action]"* — shown as `Kind=Success` with `Title`, `CTA` and `Close` off.
   >
   > **Note:** Not available as a component option in Figma — documented here only.
7. **Truncation** — Long messages are truncated with an ellipsis (`…`) at the end of the last visible line.

   | Breakpoint | Max lines (message) |
   |------------|---------------------|
   | Mobile | 3 |
   | Desktop | 2 |

---

### 6.7 Figma

| Resource | Node |
|----------|------|
| Component set | `Banner Notice` — node `6618:41005` |

---

## 7. Breadcrumb

A navigation aid that shows the user's current location within the page hierarchy. Helps users understand where they are and navigate back to parent pages.

---

### 7.1 Component Set: `Breadcrumb`

The `Breadcrumb` component composes up to 4 `Breadcrumb Link` instances separated by a `/` divider.

| Property | Type | Values / Default |
|----------|------|------------------|
| `State` | Variant | `Default` |
| `3rd` | Boolean | Shows / hides the 3rd link |
| `4th` | Boolean | Shows / hides the 4th link |

Depth: 2 to 4 links, set with the `3rd` and `4th` booleans.

---

### 7.2 Sub-component: `Breadcrumb Link`

| Property | Type | Values / Default |
|----------|------|------------------|
| `State` | Variant | `Default` · `Hover` · `Active` · `Disabled` |
| `Default Label` · `Hover Label` · `Active Label` · `Disabled Label` | Text | One label per state |

**State definitions:**

| State | Colour | Hex | Underline | Notes |
|-------|--------|-----|-----------|-------|
| `Default` | `Blue/50 (Logo)` | `#006BFF` | No | Standard unvisited link |
| `Hover` | `Blue/60` | `#004BE0` | Yes | On mouse hover |
| `Active` | `Shades/80` | `#3A3D46` | No | Current page in the trail |
| `Disabled` | `Shades/40` | `#B2BBC7` | No | Non-interactive |

**Typography:** `Body/14`

---

### 7.3 Anatomy

```
[Link label] / [Link label] / [Link label] / [Link label]
```

- Each segment is a `Breadcrumb Link` instance
- Segments are separated by a plain text `/` divider
- The last segment typically uses the `Active` state to indicate the current page

---

### 7.4 Figma

| Resource | Link |
|----------|------|
| Component set | `Breadcrumb` — node `3276:32813` |
| Sub-component | `Breadcrumb Link` — node `4721:36827` |

---

## 8. Button

The primary interactive element for triggering actions. Three types, three hierarchies, three sizes and two modes. Button stays one component (Pill / Icon / Link) because it is nested in many other components.

---

### 8.1 Properties

| Property | Type | Values / Default |
|----------|------|------------------|
| `Mode` | Variant | `Light` · `Dark` |
| `Type` | Variant | `Pill` · `Icon` · `Link` |
| `Hierarchy` | Variant | `Primary` · `Secondary` · `Tertiary` (all types) |
| `Size` | Variant | `Large` · `Medium` · `Small` |
| `State` | Variant | `Default` · `Hover` · `Pressed` · `Disabled` · `Focused` |
| `Text Label` | Text | `Button` |
| `Left Icon` | Boolean | `false` |
| `Right Icon` | Boolean | `false` |
| `Left Icon Swap` | Instance swap | Icon on the left |
| `Right Icon Swap` | Instance swap | Icon on the right |

Total variants: **270** (3 types × 3 hierarchies × 3 sizes × 5 states × 2 modes)

---

### 8.2 Types

**Pill** — the standard button. Primary is filled, Secondary is outlined, Tertiary has no fill and no border. One icon per Pill, left or right, picked with `Left Icon Swap` / `Right Icon Swap`.

**Icon** — a circular icon-only button. Same hierarchies as Pill.

**Link** — a label-only button with no background. Primary is blue; Secondary and Tertiary share the same grey colours. Link can take a left or right icon.

---

### 8.3 States — Light mode (Pill & Icon)

| Hierarchy | State | Background | Label / Icon | Border |
|-----------|-------|-----------|--------------|--------|
| Primary | `Default` | `Blue/50 (Logo)` `#006BFF` | `Shades/0 (White)` | — |
| Primary | `Hover` | `Blue/60` `#004BE0` | `Shades/0 (White)` | — |
| Primary | `Pressed` | `Blue/70` `#042CC8` | `Shades/0 (White)` | — |
| Primary | `Disabled` | `Shades/10` `#F3F5F7` | `Shades/60` `#717C8E` | — |
| Secondary | `Default` | None | `Blue/50 (Logo)` | 1px `Blue/50 (Logo)` |
| Secondary | `Hover` | `Blue/50 (Logo)` @5% | `Blue/60` | 1px `Blue/60` |
| Secondary | `Pressed` | `Blue/50 (Logo)` @10% | `Blue/70` | 1px `Blue/70` |
| Secondary | `Disabled` | None | `Shades/60` | 1px `Shades/40` |
| Tertiary | `Default` | None | `Blue/50 (Logo)` | — |
| Tertiary | `Hover` | `Blue/50 (Logo)` @5% | `Blue/60` | — |
| Tertiary | `Pressed` | `Blue/50 (Logo)` @10% | `Blue/70` | — |
| Tertiary | `Disabled` | None | `Shades/60` | — |
| All | `Focused` | `Blue/50 (Logo)` (solid) | `Shades/0 (White)` | Focus ring |

Secondary / Tertiary Hover and Pressed use the tint with **no white layer**.

---

### 8.4 States — Dark mode (Pill & Icon)

| Hierarchy | State | Background | Label / Icon | Border |
|-----------|-------|-----------|--------------|--------|
| Primary | `Default` | `Shades/0 (White)` | `Blue/50 (Logo)` | — |
| Primary | `Hover` | White + `Blue/50 (Logo)` @5% | `Blue/70` | — |
| Primary | `Pressed` | White + `Blue/50 (Logo)` @10% | `Blue/70` | — |
| Primary | `Disabled` | `Shades/20` `#E3E8ED` | `Shades/70` `#515867` | — |
| Secondary | `Default` | None | `Blue/30` `#A6D0FF` | 1px `Blue/30` |
| Secondary | `Hover` | `#E7F2FF` @10% | `Blue/10` | 1px `Blue/10` |
| Secondary | `Pressed` | `#E7F2FF` @20% | `Blue/10` | 1px `Blue/5` |
| Secondary | `Disabled` | None | `Shades/40` | 1px `Shades/50` |
| Tertiary | — | Same as Secondary | Same as Secondary | — |
| All | `Focused` | `Blue/50 (Logo)` (solid) | `Shades/0 (White)` | Focus ring |

> Need a solid light button next to a Primary? Use `Mode=Dark`, `Hierarchy=Primary` (white). The product has no dark mode; "Dark" means "on a dark or coloured background".

---

### 8.5 States — Link

| Mode | Hierarchy | Default | Hover | Pressed | Disabled |
|------|-----------|---------|-------|---------|----------|
| Light | Primary | `Blue/50 (Logo)` | `Blue/60` | `Blue/70` | `Shades/50` |
| Light | Secondary / Tertiary | `Shades/60` | `Blue/50 (Logo)` | `Blue/70` | `Shades/50` |
| Dark | Primary | `Blue/30` | `Blue/20` | `Shades/0 (White)` | `Shades/40` |
| Dark | Secondary / Tertiary | `Shades/20` | `Shades/10` | `Shades/0 (White)` | `Shades/60` |

`Focused` keeps the Default label colour and adds the focus ring.

---

### 8.6 Sizes

**Pill**

| Size | Height | Padding (V / H) | Gap | Text style | Corner radius |
|------|--------|-----------------|-----|-----------|---------------|
| `Large` | 48px | 12px / 24px | 12px | `Body/16` | 48px |
| `Medium` | 34px | 6.5px / 16px | 8px | `Body/14` | 48px |
| `Small` | 27px | 4px / 12px | 8px | `Body/12` | 48px |

**Icon**

| Size | Dimensions | Padding |
|------|-----------|---------|
| `Large` | 48×48px | 12px |
| `Medium` | 34×34px | 12px |
| `Small` | 27×27px | 5.5px |

**Link** — no padding, hugs its label.

| Size | Height | Gap | Text style |
|------|--------|-----|-----------|
| `Large` | 24px | 8px | `Body/16` |
| `Medium` | 21px | 4px | `Body/14` |
| `Small` | 19px | 4px | `Body/12` |

---

### 8.7 Usage

1. One icon per Pill, left or right. Pick it from `Left Icon Swap` / `Right Icon Swap`; no need to open the nested layer.
2. Pill labels wrap to two lines, then end with "…". Set the instance to Fill or Fixed width to make it wrap. Link always hugs its label and stays on one line.
3. Focused: solid `Blue/50 (Logo)`, white label and icon, plus a 2px `Blue/50 (Logo)` focus ring 1px outside.
4. A 32px margin is often too restrictive on mobile; it is 24px.

---

### 8.8 Figma

| Resource | Node |
|----------|------|
| Component set | `Button` — node `4921:37343` |

---

## 9. Button Group

A single-select set of options that switches content in place (e.g. Score / Summary). One option is always selected. Replaces the old `Button _ Group _ Horizontal` / `_ Vertical` components (now `[OBSOLETE]`).

---

### 9.1 Components

| Component | Node | Description |
|-----------|------|-------------|
| `Button Group` | `7900:43882` | Wrapper. Put items in the `Options` slot. |
| `Button Group _ Item _ Horizontal` | `7899:4138` | Pill option, icon + label side by side |
| `Button Group _ Item _ Vertical` | `7899:43835` | Icon container with the label below |

---

### 9.2 Properties

**Button Group** — 5 variants

| Property | Type | Values |
|----------|------|--------|
| `Type` | Variant | `Horizontal` · `Vertical` |
| `Size` | Variant | `Large` · `Medium` · `N/A` (Vertical) |
| `Width` | Variant | `Hug` · `Fill` |
| `Options` | Slot | Button Group items |

**Button Group _ Item _ Horizontal** — 14 variants

| Property | Type | Values / Default |
|----------|------|------------------|
| `Size` | Variant | `Medium` · `Large` |
| `Selected` | Variant | `False` · `True` |
| `State` | Variant | `Default` · `Hover` · `Focus` · `Pressed` · `Disabled` |
| `Label` | Text | `Label` |
| `Show icon` | Boolean | `true` |
| `Icon` | Instance swap | Leading icon |

**Button Group _ Item _ Vertical** — 7 variants: `Selected` × `State` (as above), `Label`, `Icon`.

Selected options have only `Default` and `Focus` (not clickable).

---

### 9.3 States (both items)

| State | Background | Border | Icon | Label |
|-------|-----------|--------|------|-------|
| `Default` | `Shades/0 (White)` | 1px `Shades/40` | `Blue/50 (Logo)` | `Shades/80` |
| `Hover` | White + `Blue/50 (Logo) 5%` | — | `Blue/60` | `Shades/80` |
| `Focus` | Hover + focus ring | — | as Hover | `Shades/80` |
| `Pressed` | White + `Blue/50 (Logo) 10%` | — | `Blue/70` | `Blue/70` |
| `Disabled` | `Shades/10` | — | `Shades/50` | `Shades/60` |
| Selected `Default` | `Blue/10` | — | `Blue/60` | `Shades/80` |
| Selected `Focus` | `Blue/10` + focus ring | — | `Blue/60` | `Shades/80` |

---

### 9.4 Sizes

| Item | Height | Padding (H) | Gap | Text style | Icon |
|------|--------|-------------|-----|-----------|------|
| Horizontal `Medium` | 34px | 16px | 8px | `Body/14` | 16px |
| Horizontal `Large` | 48px | 24px | 8px | `Body/16` | 24px |
| Vertical | 75px total (48px icon container + 8px + label) | 12px in the container | 8px | `Body/12` | 24px |

Corner radius: Full (999px).

---

### 9.5 Layout

| Rule | Value |
|------|-------|
| Gap between items | `Sizes/05` (12px) |
| Horizontal, `Width=Hug` | Items hug their label (min 55px Medium / 80px Large, no max width). On mobile the row scrolls sideways; it never wraps. |
| Horizontal, `Width=Fill` | The row takes the full width; items share it equally (e.g. page-level tabs). |
| Vertical | Items share the width equally. Icon container stretches to max 70px. One size. |

---

## 10. Button Segmented

Segmented control: 2–5 short options of equal weight, flush in a pill track, exactly one selected.

---

### 10.1 Properties

**Button Segmented** — 8 variants

| Property | Type | Values |
|----------|------|--------|
| `Size` | Variant | `Medium` · `Large` |
| `Options` | Variant | `2` · `3` · `4` · `5` |

Option instances are exposed: set `Selected`, `State` and `Label` from the parent.

**Button Segmented _ Item** — 14 variants

| Property | Type | Values / Default |
|----------|------|------------------|
| `Size` | Variant | `Medium` · `Large` |
| `Selected` | Variant | `False` · `True` |
| `State` | Variant | `Default` · `Hover` · `Focus` · `Pressed` · `Disabled` |
| `Label` | Text | `Label` |

Label only, no icon. Not used on its own.

---

### 10.2 Specs

| Spec | Value |
|------|-------|
| Track | `Shades/0 (White)`, 1px `Shades/40` inside border, no padding, no gaps or dividers, radius Full. Clips the end options. |
| Height | 34px (`Medium`) · 48px (`Large`), same as Button |
| Item padding (H) | 12px |
| Text style | `Body/14` (Medium) · `Body/16` (Large) |
| Width | Fills its container (358px = mobile default). Options share the width equally. |

---

### 10.3 States

| State | Background | Label |
|-------|-----------|-------|
| `Default` | None (track shows) | `Shades/80` |
| `Hover` | White + `Blue/50 (Logo) 5%` | `Shades/80` |
| `Focus` | Hover + 2px `Blue/50 (Logo)` inside ring | `Shades/80` |
| `Pressed` | White + `Blue/50 (Logo) 10%` | `Blue/70` |
| `Disabled` | None | `Shades/60` |
| Selected `Default` | `Blue/10` | `Shades/80` |
| Selected `Focus` | `Blue/10` + inside ring | `Shades/80` |

---

### 10.4 Usage

1. Keep labels to one or two words.
2. The five-option version is mainly for numbers.
3. More than 5 options, long labels or icons on every option → use Button Group.

---

### 10.5 Figma

| Resource | Node |
|----------|------|
| `Button Segmented` | node `7900:4202` |
| `Button Segmented _ Item` | node `7900:4167` |

---

## 11. Card _ Selection

Selectable card with a radio control, a label and an optional content slot.

---

### 11.1 Properties

| Property | Type | Values / Default |
|----------|------|------------------|
| `State` | Variant | `Default` · `Hover` · `Pressed` · `Selected` |
| `Text Label` | Text | `Text Label` |
| `Slot Visible` | Boolean | `true` |
| `Slot` | Slot | Extra content |

Total variants: **4**

---

### 11.2 Specs

| Spec | Value |
|------|-------|
| Size | 312 × 120px (doc size) |
| Padding / gap | 24px / 24px |
| Corner radius | 8px |
| Label | `Body/16`, `Shades/80` (`Body/16 Semibold` when Selected) |
| Radio control | 24px, gap 12px from the label |

---

### 11.3 States

| State | Border | Radio |
|-------|--------|-------|
| `Default` | 1px `Shades/40` | White, 1px `Shades/50` |
| `Hover` | 1px `Blue/60` | White, 1px `Shades/50` |
| `Pressed` | 1px `Blue/70` | White, 1px `Shades/50` |
| `Selected` | 1px `Blue/40` | `Blue/50 (Logo)` fill, white dot |

> There is no Focus or Disabled state.

---

### 11.4 Figma

| Resource | Node |
|----------|------|
| Component set | `Card _ Selection` — node `7694:40432` |

---

## 12. Checkbox

A form control that allows users to select one or multiple options from a set.

---

### 12.1 Properties

| Property | Type | Values / Default |
|----------|------|------------------|
| `State` | Variant | `Default` · `Hover` · `Pressed` · `Focused Unselected` · `Selected` · `Focused Selected` · `Error` · `Disabled` |
| `Size` | Variant | `Medium` · `Large` |
| `Text` | Text | `Label` |
| `Label` | Boolean | `true` — shows / hides the label |
| `Icon` | Instance swap | Check icon |

Total variants: **16**

---

### 12.2 Anatomy

- A square control box with a border and optional fill
- A checkmark icon (visible in `Selected` and `Focused Selected` only)
- A focus ring rectangle (visible in `Focused Unselected` and `Focused Selected`)
- An optional text label

---

### 12.3 States

| State | Box background | Box border | Label colour | Checkmark | Notes |
|-------|---------------|------------|--------------|-----------|-------|
| `Default` | `Shades/0 (White)` | `Shades/40` `#B2BBC7` | `Shades/80` `#3A3D46` | — | |
| `Hover` | White + `Blue/50 (Logo) 5%` | `Blue/60` | `Blue/60` | — | |
| `Pressed` | White + `Blue/50 (Logo) 10%` | `Blue/70` | `Blue/70` | — | |
| `Focused Unselected` | White + `Blue/50 (Logo) 5%` | `Blue/60` | `Blue/60` | — | + focus ring |
| `Selected` | `Blue/50 (Logo)` | `Blue/50 (Logo)` | `Blue/60` | White | |
| `Focused Selected` | `Blue/50 (Logo)` | `Blue/50 (Logo)` | `Blue/60` | White | + focus ring |
| `Error` | `Shades/0 (White)` | `Coral/50` | `Coral/50` | — | |
| `Disabled` | `Shades/0 (White)` | `Shades/40` | `Shades/50` | — | |

---

### 12.4 Sizes

| Size | Control box | Gap (box ↔ label) | Text style | Alignment |
|------|------------|-------------------|-----------|-----------|
| `Medium` | 16×16px | 8px | `Body/14` | Top-aligned |
| `Large` | 24×24px | 12px | `Body/16` | Top-aligned |

Corner radius on control box: **2px**

---

### 12.5 Figma

| Resource | Node |
|----------|------|
| Component set | `Checkbox` — node `3130:36530` |

---

## 13. Chip _ Choice

Pill-shaped choice chip, e.g. for picking a service category.

---

### 13.1 Properties

| Property | Type | Values / Default |
|----------|------|------------------|
| `State` | Variant | `Default` · `Hover` · `Pressed` · `Selected` |
| `Text label` | Text | `Text label` |

Total variants: **4**

---

### 13.2 States

| State | Background | Border | Label |
|-------|-----------|--------|-------|
| `Default` | `Shades/0 (White)` | 1px `Blue/30` | `Shades/80` |
| `Hover` | `Blue/10` | — | `Shades/80` |
| `Pressed` | `Blue/30` | — | `Blue/70` |
| `Selected` | `Blue/20` | — | `Blue/70` |

---

### 13.3 Specs

| Spec | Value |
|------|-------|
| Height | 29px |
| Padding (V / H) | 4px / 12px |
| Corner radius | Full (999px) |
| Text style | `Body/14` |

> ⚠️ Chip _ Choice and Button Group look alike; they are kept as separate components and still need to be visually differentiated. No Focus or Disabled state yet.

---

### 13.4 Figma

| Resource | Node |
|----------|------|
| Component set | `Chip _ Choice` — node `7694:40481` |

---

## 14. Counter

A stepper input that lets users increment or decrement a numeric value using `+` and `−` buttons. Used when the value is bounded and users are unlikely to need large jumps.

---

### 14.1 Properties

| Property | Type | Values / Default |
|----------|------|------------------|
| `State` | Variant | `Default` · `Hover Plus` · `Hover Minus` · `Minimum` · `Maximum` |
| `Num Label` | Text | Current value |

Total variants: **5**

---

### 14.2 Anatomy

Three sections in a horizontal row:
- **Minus** — decrement button with `Icon/Remove Big`
- **Number** — current value display
- **Plus** — increment button with `Icon/Add Big`

---

### 14.3 States

| State | Minus bg | Minus border | Minus icon | Plus bg | Plus border | Plus icon | Number | Notes |
|-------|---------|-------------|-----------|--------|------------|----------|--------|-------|
| `Default` | White | `Shades/50` | `Shades/80` | White | `Shades/50` | `Shades/80` | `Shades/80` | Both buttons active |
| `Hover Minus` | White + `Blue/50 (Logo) 5%` | `Blue/60` | `Blue/60` | White | `Shades/50` | `Shades/80` | `Shades/80` | Minus hovered |
| `Hover Plus` | White | `Shades/50` | `Shades/80` | White + `Blue/50 (Logo) 5%` | `Blue/60` | `Blue/60` | `Shades/80` | Plus hovered |
| `Minimum` | White | `Shades/40` | `Shades/40` | White | `Shades/50` | `Shades/80` | `Shades/80` | Lower bound reached — Minus disabled |
| `Maximum` | White | `Shades/50` | `Shades/80` | White | `Shades/40` | `Shades/40` | `Shades/80` | Upper bound reached — Plus disabled |

---

### 14.4 Usage Notes

1. Use when the selectable range is up to 10–15 items. For larger numbers use quick-action inputs instead.
2. The user cannot type a number directly — increment/decrement only.
3. The component has a **fixed width** — do not stretch it to fill containers.

---

### 14.5 Specs

| Property | Value |
|----------|-------|
| Width | 134px |
| Height | 32px |
| Number | `Body/18 Semibold` |
| Gap between label and counter | `Sizes/07` (24px) |
| Gap between counter rows | `Sizes/06` (16px) |

---

### 14.6 Figma

| Resource | Node |
|----------|------|
| Component set | `Counter` — node `4396:51463` |

---

## 15. Date Picker

A calendar UI that allows users to select a date. Composed of a `Date Picker _ Day` sub-component assembled into a parent `Date Picker` component.

---

### 15.1 Date Picker _ Day

| Property | Type | Values |
|----------|------|--------|
| `Kind` | Variant | `Current Month` · `Another Month` |
| `State` | Variant | `Default` · `Hover` · `Pressed` · `Selected` |

Total variants: **8**

| Kind | State | Background | Text | Notes |
|------|-------|-----------|------|-------|
| Current Month | `Default` | White | `Shades/80` | In-range day |
| Another Month | `Default` | White | `Shades/50` | Out-of-range day |
| Both | `Hover` | `Blue/5` | `Blue/60` | |
| Both | `Pressed` | `Blue/10` | `Blue/70` | |
| Both | `Selected` | `Blue/50 (Logo)` | White | |

Dimensions: **40×40px** · Typography: `Body/16`

---

### 15.2 Parent: `Date Picker`

One variant (`Kind=Default`). Three sections:

| Section | Height | Description |
|---------|--------|-------------|
| `Month` | 48px | Month/year header with prev/next navigation |
| `Days` | 272px | 7-column calendar grid of `Date Picker _ Day` instances |
| `CTA` | 46px | Confirm / cancel actions |

Overall dimensions: **312×366px**

---

### 15.3 Figma

| Resource | Node |
|----------|------|
| Component set | `Date Picker` — node `6537:41204` |
| Sub-component | `Date Picker _ Day` — node `6505:45807` |

---

## 16. Drop Down

A field that opens a list of options. Box and Pill shapes have the same use. Time picking is a Drop Down too (24h format, list opens at the top). Behaves the same on web and app.

---

### 16.1 Components

| Component | Node | Description |
|-----------|------|-------------|
| `Drop Down` | `2397:68407` | The field (trigger) |
| `Drop Down _ Menu Flyout` | `7105:2052` | The floating list. Put rows in its slot. |
| `Drop Down _ Item` | `7105:2067` | A row in the list |
| `Drop Down _ Search` | `7579:3053` | Search field at the top of the flyout |

---

### 16.2 Drop Down — Properties

| Property | Type | Values / Default |
|----------|------|------------------|
| `State` | Variant | `Empty` · `Hover` · `Error` · `Focused` · `Selected` · `Focused Selected` · `Disabled` · `Open` |
| `Shape` | Variant | `Pill` · `Box` |
| `Text Label` | Text | `Select a service` |

Total variants: **16**

| Spec | Pill | Box |
|------|------|-----|
| Height | 40px | 40px |
| Padding (T / R / B / L) | 8 / 12 / 8 / 24px | 8 / 8 / 8 / 12px |
| Corner radius | 24px | 2px |
| Text style | `Body/16` | `Body/16` |
| Chevron | 24px | 24px |

---

### 16.3 Drop Down — States

| State | Background | Border | Text | Chevron |
|-------|-----------|--------|------|---------|
| `Empty` | `Shades/0 (White)` | 1px `Shades/40` | `Shades/40` (placeholder) | `Blue/50 (Logo)` |
| `Selected` | `Shades/0 (White)` | 1px `Shades/40` | `Shades/80` | `Blue/50 (Logo)` |
| `Hover` | `Shades/0 (White)` | 1px `Blue/50 (Logo)` | `Shades/80` | `Blue/60` |
| `Open` | `Shades/0 (White)` | 1px `Blue/50 (Logo)` | `Shades/80` | `Icon/Chevron Up`, `Blue/50 (Logo)` |
| `Focused` | `Shades/0 (White)` | 1px `Shades/40` + focus ring | `Shades/40` | `Blue/50 (Logo)` |
| `Focused Selected` | `Shades/0 (White)` | 1px `Shades/40` + focus ring | `Shades/80` | `Blue/50 (Logo)` |
| `Error` | `Shades/0 (White)` | 1px `Coral/50` | `Shades/40` | `Coral/50` |
| `Disabled` | `Shades/5` | 1px `Shades/40` | `Shades/40` | `Shades/40` |

No Error glow. Hover looks the same as Open.

---

### 16.4 Drop Down _ Menu Flyout

| Property | Type | Values / Default |
|----------|------|------------------|
| `Variation` | Variant | `Default` · `[Legacy] 5 Rows` (don't use for new work) |
| `Search` | Boolean | `true` — on by default so it stays discoverable; turn off when not needed |
| `Scroll` | Boolean | `true` |
| `Slot` | Slot | `Drop Down _ Item` rows |

| Spec | Value |
|------|-------|
| Width | Same as the field (328px doc size) |
| Background | `Shades/0 (White)` |
| Corner radius | 4px |
| Shadow | `Elevation 2` |
| Rows max height | 240px (5 rows), then the rows scroll |
| Scrollbar | Thumb overlays the rows |

---

### 16.5 Drop Down _ Item

| Property | Type | Values / Default |
|----------|------|------------------|
| `State` | Variant | `Default` · `Hover` · `Pressed` · `Selected` |
| `Icon` | Variant | `No` · `Yes` (leading icon) |
| `Text Label` | Text | `Text Label` |

| State | Background | Label | Leading icon | Trailing |
|-------|-----------|-------|--------------|----------|
| `Default` | `Shades/0 (White)` | `Shades/80` | `Shades/60` | — |
| `Hover` | `Blue/50 (Logo)` @5% | `Blue/60` | `Blue/60` | — |
| `Pressed` | `Blue/50 (Logo)` @10% | `Blue/70` | `Blue/70` | — |
| `Selected` | `Shades/0 (White)` | `Blue/50 (Logo)` | `Blue/50 (Logo)` | `Icon/Check Big`, `Blue/50 (Logo)` |

Height 48px · padding 12px · gap 8px · `Body/16`. Prefer outline icons.

---

### 16.6 Drop Down _ Search

| State | Border | Text | Icons |
|-------|--------|------|-------|
| `Default / Placeholder` | Bottom stroke `Shades/30` | `Shades/40` | `Icon/Magnifying Glass` `Shades/40` |
| `Filled` | Bottom stroke `Shades/30` | `Shades/80` | Magnifier `Shades/80` · `Icon/Close Big` `Shades/40` |

Height 40px · padding 8px / 12px · `Body/16`.

---

### 16.7 Usage

1. **Max height** — from the 6th row on, the rows scroll inside the flyout; the flyout stops growing. With Search on, search stays fixed on top and only the rows scroll.
2. **Searching** — rows filter as you type (label contains the text, not case-sensitive). Clear (×) shows once there is text.
3. **No results** — one line, "No results for "…"", `Body/16`, `Shades/50`. Not a component.
4. **Long labels** — one line, then "…", in the field and in the rows.
5. **Title, helper text, caption or error** — put the Drop Down in `Field _ Block` (see 19.4).
6. Placeholder text: "Select a service".

---

## 17. Input _ Phone

Phone number input with a country code selector. Mirrors `Input _ Text` states and tokens.

---

### 17.1 Components

| Component | Node | Description |
|-----------|------|-------------|
| `Input _ Phone` | `7833:3853` | The field |
| `Flag` | `7832:3603` | Country flag, 18×12 (3:2). `Country`: `GR` · `CY` · `IE` · `EN` |
| `Input _ Phone _ Country Item` | `7834:3760` | Row of the country list |

---

### 17.2 Properties

| Property | Type | Values / Default |
|----------|------|------------------|
| `State` | Variant | `Default` · `Hover` · `Focused+Typing` · `Filled` · `Disabled` · `Success` · `Open` |
| `Error` | Variant | `Off` · `On` (`Open` only with `Error=Off`) |
| `Flag` | Instance swap | `Flag` |
| `Country code` | Text | `+30` |
| `Phone number` | Text | `Phone number` |
| `Icon Right` · `Icon Cancel` | Boolean | `true` |

Total variants: **12**

---

### 17.3 Anatomy & Specs

```
[ Flag  +30  ⌄ ] │ [ Phone number            (icon) ]
```

| Spec | Value |
|------|-------|
| Height | 40px |
| Min width | 256px (same as Input _ Text) |
| Padding / gap | 8px / 12px · 8px |
| Corner radius | 2px |
| Country segment | Flag 18×12 + code (`Body/16`, `Shades/80`) + 12px chevron, gap 6px |
| Divider | 1px `Shades/20` |

---

### 17.4 States

| State | Border | Number text | Chevron / icon |
|-------|--------|-------------|----------------|
| `Default` | `Shades/40` | `Shades/40` (placeholder) | `Shades/40` |
| `Hover` | `Blue/50 (Logo)` | — | `Shades/50` |
| `Focused+Typing` | `Blue/50 (Logo)` | `Shades/80` | `Blue/50 (Logo)` |
| `Filled` | `Shades/40` | `Shades/80` | `Shades/80` |
| `Open` | `Blue/50 (Logo)` | — | `Icon/Chevron Up`, `Blue/50 (Logo)` |
| `Success` | `Green/30` | `Shades/80` | `Green/30`, `Icon/Check Big` |
| `Disabled` | `Shades/40`, background `Shades/5` | `Shades/40` | `Shades/40` |
| `Error=On` | `Coral/50` | as state | as state |

---

### 17.5 Country list

`Input _ Phone _ Country Item` mirrors `Drop Down _ Item`: height 48px, padding 12 / 16px, gap 10px, `Body/16`.

| State | Background | Text |
|-------|-----------|------|
| `Default` | `Shades/0 (White)` | `Shades/80` |
| `Hover` | `Blue/50 (Logo)` @5% | `Blue/60` |
| `Selected` | `Shades/0 (White)` | `Blue/50 (Logo)` |

Place rows inside a white container, radius 4px, `Elevation 2`. List width = field width.

---

### 17.6 Usage

1. The country segment (flag + code + chevron) is one tap target and opens the country list.
2. Tapping the number area opens the numeric keypad.
3. Default country follows the market: Douleutaras GR +30 · Cyprus +357 · YourPro IE +353.
4. Number length (national number, no leading 0): GR 10 · CY 8 · IE 9 · UK 10.
5. If the user pastes "+30…" or "0030…", strip the code and switch the flag.
6. Country list: markets first, selected row in `Blue/50 (Logo)`.
7. Label, caption and error: use `Field _ Block`.

**Dev handoff**

- Number field: `<input type="tel" inputmode="tel" autocomplete="tel-national">`
- Country selector: `autocomplete="tel-country-code"`
- Store and send as E.164, e.g. `+306941234567`. Validate and format per country (e.g. libphonenumber-js).
- Flags: Untitled UI rectangle SVGs, 18×12 — https://www.untitledui.com/resources/flag-icons

---

## 18. Input _ Price

Small numeric field with a € prefix, used for prices.

---

### 18.1 Properties

| Property | Type | Values / Default |
|----------|------|------------------|
| `State` | Variant | `Placeholder` · `Hover` · `Focused+Typing` · `Filled` · `Error / Placeholder` · `Error / Filled` |
| `Number` | Text | `50` |

Total variants: **6**

---

### 18.2 States

| State | Border | Number | € |
|-------|--------|--------|---|
| `Placeholder` | `Shades/40` | `Shades/40` | `Shades/40` |
| `Hover` | `Blue/50 (Logo)` | `Shades/50` | `Shades/40` |
| `Focused+Typing` | `Blue/50 (Logo)` | `Shades/80` | `Shades/40` |
| `Filled` | `Shades/40` | `Shades/80` | `Shades/40` |
| `Error / Placeholder` | `Coral/50` | `Shades/40` | `Shades/40` |
| `Error / Filled` | `Coral/50` | `Shades/80` | `Shades/40` |

Height 40px · padding 12 / 16px · gap 8px · radius 2px · `Body/16` · doc width 90px.

---

### 18.3 Usage

1. Width stays the same up to 4-digit numbers.
2. The field expands up to 6-digit numbers, then truncates.

> No Disabled or Focused (keyboard) state.

---

### 18.4 Figma

| Resource | Node |
|----------|------|
| Component set | `Input _ Price` — node `7567:39713` |

---

## 19. Input _ Text

Single-line text field (shown as "Input Field" in the Minibook), plus a tall multi-line version and a shared block for labels and messages.

---

### 19.1 Components

| Component | Node | Description |
|-----------|------|-------------|
| `Input _ Text` | `3237:59498` | Single-line field |
| `Text Input _ Tall` | `7202:38569` | Multi-line field |
| `Field _ Block` | `6457:41678` | Title, text, field, caption, error and success messages around one field (was "Text Input _ Block"). Shared with Drop Down. |

---

### 19.2 Input _ Text — Properties

| Property | Type | Values / Default |
|----------|------|------------------|
| `State` | Variant | `Default` · `Hover` · `Focused` · `Focused+Typing` · `Filled` · `Success` · `Disabled` |
| `Error` | Variant | `Off` · `On` |
| `Text field` | Text | `Text field` |
| `Icon Left` · `Icon Right` · `Icon Cancel` | Boolean | `true` |

Total variants: **13** (`Success` has no `Error=On` version)

| Spec | Value |
|------|-------|
| Height | 40px |
| Min width | 256px |
| Padding / gap | 8px / 12px · 8px |
| Corner radius | 2px |
| Text style | `Body/16` |
| Icons | 16px |

No Pill shape for Input _ Text.

---

### 19.3 Input _ Text — States

| State | Border | Text | Icons |
|-------|--------|------|-------|
| `Default` | `Shades/40` | `Shades/40` (placeholder) | `Shades/40` |
| `Hover` | `Blue/50 (Logo)` | `Shades/40` | `Shades/40` |
| `Focused` (keyboard) | `Blue/50 (Logo)` + focus ring | `Shades/40` | `Shades/40` |
| `Focused+Typing` | `Blue/50 (Logo)` | `Shades/80` | `Blue/50 (Logo)` |
| `Filled` | `Shades/40` | `Shades/80` | `Shades/80` |
| `Success` | `Green/30` | `Shades/80` | `Green/30`, right icon `Icon/Check Big` |
| `Disabled` | `Shades/40`, background `Shades/5` | `Shades/40` | `Shades/40` |
| `Error=On` | `Coral/50` (focus ring stays `Blue/50`) | as state | Cancel icon `Coral/50` |

Hover border is kept while typing and goes back to `Shades/40` on click outside. No Error glow.

---

### 19.4 Field _ Block

| Property | Type | Default |
|----------|------|---------|
| `Field` | Instance swap | `Input _ Text` (default), `Text Input _ Tall` or `Drop Down` |
| `Title` / `Title label` | Boolean / Text | `true` / `Title` |
| `Text` / `Text label` | Boolean / Text | `true` / `Explanatory text / Question` |
| `Caption` / `Caption label` | Boolean / Text | `true` / `Caption with extra information` |
| `Error caption` / `Error caption label` | Boolean / Text | `true` / `This field is required` |
| `Success caption` / `Success caption label` | Boolean / Text | `true` / Greek sample |

| Element | Style |
|---------|-------|
| Title | `Body/16 Semibold`, `Shades/95 (Black)` |
| Explanatory text | 16px, `Shades/80` |
| Caption | `Body/14`, `Shades/50` |
| Error message | `Body/14`, `Coral/50` |
| Success message | `Body/14`, `Green/40` |
| Gap header ↔ field | 8px · field ↔ messages 4px |

> ⚠️ The explanatory text has no text style applied (raw 16px).

---

### 19.5 Text Input _ Tall

Same colours and icons as `Input _ Text`, 112px high (doc size), padding 8 / 20 / 8 / 12px.

| Property | Type | Values / Default |
|----------|------|------------------|
| `Variation` | Variant | `Default` · `Hover` · `Focused` · `Focused & Typing` · `Filled` · `Disabled` · `Success` · `Error / Default` · `Error / Hover` · `Error / Focused` · `Error / Focused & Typing` · `Error / Filled` · `Error / Disabled` |
| `Scroll bar` | Boolean | `false` |
| `Text Field` | Text | `Text field` |
| `Icon Left` · `Icon Right` · `Icon Cancel` | Boolean | `true` |

- Max height 136px; text truncates after 5 lines.
- Scroll bar on: 4px wide, `Shades/70`, 8px from top, right and bottom. Icons sit 8px left of it. Same scrollbar as the CCF modal.

> ⚠️ Uses one `Variation` property for states and errors, instead of `State` + `Error` like Input _ Text.

---

## 20. Input _ Text _ Chat

Message field with a Send icon, used in chat.

---

### 20.1 Properties

| Property | Type | Values / Default |
|----------|------|------------------|
| `State` | Variant | `Default` · `Hover` · `Focused+Typing` · `Filled` |
| `Message` | Text | `Το μήνυμά σου` |

Total variants: **4**

---

### 20.2 States

| State | Border | Text | Send icon |
|-------|--------|------|-----------|
| `Default` | `Shades/40` | `Shades/40` | `Shades/40` |
| `Hover` | `Blue/50 (Logo)` | `Shades/50` | `Shades/50` |
| `Focused+Typing` | `Blue/50 (Logo)` | `Shades/80` | `Blue/50 (Logo)` |
| `Filled` | `Shades/40` | `Shades/80` | `Shades/80` |

Height 56px · padding 16px · gap 8px · radius 2px · `Body/16` · Send icon 16px.

---

### 20.3 Figma

| Resource | Node |
|----------|------|
| Component set | `Input _ Text _ Chat` — node `7569:47751` |

---

## 21. Pagination

A navigation control that allows users to move through a multi-page dataset. Composed of three sub-components assembled into a parent `Pagination` component.

---

### 21.1 Sub-components

| Component | Node | Description |
|-----------|------|-------------|
| `Pagination _ Page Number` | `6488:27789` | Individual page number button |
| `Pagination _ PrevNext` | `6492:27895` | Previous and Next arrow buttons |
| `Pagination _ Ellipsis` | `6494:27929` | Separator between non-adjacent page numbers |

---

### 21.2 Pagination _ Page Number

| State | Background | Text |
|-------|-----------|------|
| `Default` | White | `Shades/80` |
| `Active` | `Blue/50 (Logo)` | `Shades/0 (White)` |
| `Hover` | `Blue/5` | `Blue/60` |

Dimensions: **40×40px**

---

### 21.3 Pagination _ PrevNext

| Property | Values |
|----------|--------|
| `PrevNext` | `Previous` · `Next` |
| `State` | `Default` · `Hover` · `Inactive` |

| State | Background | Icon |
|-------|-----------|------|
| `Default` | White | `Blue/50 (Logo)` |
| `Hover` | `Blue/5` | `Blue/50 (Logo)` |
| `Inactive` | White | `Shades/40` |

Dimensions: **40×40px**

---

### 21.4 Pagination _ Ellipsis

Non-interactive. White background, `Shades/50` text. **40×40px**

---

### 21.5 Parent: `Pagination`

| Variant | Description |
|---------|-------------|
| `2 Pages` | Previous · 1 · 2 · Next |
| `3 Pages` | Previous · 1 · 2 · 3 · Next |
| `First Page Open` | Previous (inactive) · 1 · 2 · 3 · … · Next |
| `In-between Page Open` | Previous · … · n · n+1 · n+2 · … · Next |
| `Last Page Open` | Previous · … · n-2 · n-1 · n · Next (inactive) |

The variant property is called `Variation`.

---

### 21.6 Figma

| Resource | Node |
|----------|------|
| Component set | `Pagination` — node `6494:27987` |
| `Pagination _ Page Number` | node `6488:27789` |
| `Pagination _ PrevNext` | node `6492:27895` |
| `Pagination _ Ellipsis` | node `6494:27929` |

---

## 22. Progress Bar

Thin bar showing progress through a flow (e.g. the CCF modal). One component for mobile and desktop, one colour (Material-style).

---

### 22.1 Properties

| Property | Type | Values |
|----------|------|--------|
| `Progress` | Variant | `25%` · `50%` · `75%` · `[Legacy]` |

| Spec | Value |
|------|-------|
| Height | 6px |
| Track | `Shades/20` |
| Active | `Blue/50 (Logo)` |
| Corner radius | Full |

`[Legacy]` (white track, `Blue/40` bar) is kept for existing layouts only.

---

### 22.2 Figma

| Resource | Node |
|----------|------|
| Component set | `Progress Bar` — node `7978:41705` |

---

## 23. Purple Background Curve

Decorative purple curve under headers.

| Property | Values |
|----------|--------|
| `Height` | `16` · `80` |

- Colour: `Purple/40`.
- Stretches in width; the height stays fixed (16px or 80px).

**Figma:** `Purple Background Curve` — node `5690:34876`

---

## 24. Quick Action Button

Full-width answer button used in quick-action question flows, with an optional image (avatars) and a chevron.

---

### 24.1 Properties

| Property | Type | Values / Default |
|----------|------|------------------|
| `State` | Variant | `Default` · `Hover` · `Pressed` · `Selected` · `Disabled` |
| `Image` | Variant | `Off` · `On` |
| `Text` | Text | `Text` |

Total variants: **10**

---

### 24.2 States

| State | Background | Border | Text / chevron |
|-------|-----------|--------|----------------|
| `Default` | `Shades/0 (White)` | 1px `Shades/40` | `Shades/80` / `Blue/50 (Logo)` |
| `Hover` | White + `Blue/50 (Logo)` @5% | 1px `Blue/60` | `Blue/60` |
| `Pressed` | White + `Blue/50 (Logo)` @10% | 1px `Blue/70` | `Blue/70` |
| `Selected` | `Blue/20` | 1px `Blue/40` | `Blue/60` |
| `Disabled` | `Shades/10` | — | `Shades/60` |

Height 40px (one line) · padding 8 / 12 / 8 / 24px · radius 48px · `Body/16`.

---

### 24.3 Usage

1. Text runs up to three lines, then truncates.
2. With an image: one line only, then truncation.

---

### 24.4 Figma

| Resource | Node |
|----------|------|
| Component set | `Quick Action Button` — node `3553:32950` |

---

## 25. Radio Button

A form control that allows users to select a single option from a set of mutually exclusive choices.

---

### 25.1 Properties

| Property | Type | Values / Default |
|----------|------|------------------|
| `State` | Variant | `Default` · `Hover` · `Pressed` · `Focused Unselected` · `Selected` · `Focused Selected` · `Error` · `Disabled` |
| `Text` | Text | Label |
| `Label` | Boolean | Shows / hides the label |

Total variants: **8**

---

### 25.2 States

| State | Control background | Border | Label | Inner dot |
|-------|-------------------|--------|-------|-----------|
| `Default` | White | `Shades/50` | `Shades/80` | — |
| `Hover` | White + `Blue/50 (Logo)` @5% | `Blue/60` | `Blue/60` | — |
| `Pressed` | White + `Blue/50 (Logo)` @10% | `Blue/70` | `Blue/70` | — |
| `Focused Unselected` | White + `Blue/50 (Logo)` @5% | `Blue/60` | `Blue/60` | + focus ring |
| `Selected` | `Blue/50 (Logo)` | `Blue/50 (Logo)` | `Blue/60` | White |
| `Focused Selected` | `Blue/50 (Logo)` | `Blue/50 (Logo)` | `Blue/60` | White + focus ring |
| `Error` | White | `#E65651` (`Coral/50`, not bound) | `#E65651` | — |
| `Disabled` | White | `#B2BBC7` (`Shades/40`, not bound) | `#939CA8` (no token) | — |

> ⚠️ Error and Disabled use unbound hex values.

---

### 25.3 Specs

| Spec | Value |
|------|-------|
| Control | 24px |
| Gap (control ↔ label) | 12px |
| Text style | `Body/16` |
| Gap between radio buttons | `Sizes/06` (16px) |
| Gap between group title and first radio button | `Sizes/07` (24px) |

---

### 25.4 Figma

| Resource | Node |
|----------|------|
| Component set | `Radio button` — node `3073:32039` |

---

## 26. Search Bar

App search bar (expandable search, Material-style) and its result rows.

---

### 26.1 App _ Search Bar

| Property | Type | Values |
|----------|------|--------|
| `Variation` | Variant | `White` · `Dark` · `White Rounded` |
| `State` | Variant | `Default` · `Active` |

| Variation | Background | Icons | Placeholder / typed text |
|-----------|-----------|-------|--------------------------|
| `Dark` | `Purple/40` | `Shades/0 (White)` | `Shades/40` / `Shades/0 (White)` |
| `White` · `White Rounded` | `Shades/0 (White)`, bottom stroke `Shades/30` | `Blue/50 (Logo)` | `Shades/40` / `Shades/80` |

360 × 56px · padding 16px · gap 12px · `Body/16`. Left: `Icon/Chevron Left` (back). Right: `Icon/Close Big` (clear).

---

### 26.2 Search Bar _ Result

| Variation | Content |
|-----------|---------|
| `Recent` | `Icon/History` (`Shades/50`) + recent search (`Body/16`, `Shades/95`), divider `Shades/30` |
| `Result` | `Icon/Magnifying Glass` + job title (`Body/18 Semibold`), name and phone (`Body/16`), job ID (`Body/14`, `Shades/80`), divider |

---

### 26.3 Usage

1. "Back" returns the user to the job list.
2. "×" deletes whatever the user typed.

---

### 26.4 Figma

| Resource | Node |
|----------|------|
| `App _ Search Bar` | node `1882:11496` |
| `Search Bar _ Result` | node `1882:11505` |

---

## 27. Snackbar

A brief, non-blocking notification that confirms an action or surfaces a status.

---

### 27.1 Properties

| Property | Type | Values / Default |
|----------|------|-----------------|
| `Kind` | Variant | `Info` · `Success` · `Warning` · `Alert` |
| `Lines` | Variant | `One` · `Multiple` |
| `CTA` | Boolean | `true` · `false` |
| `CTA Label` | Text | `Action` |
| `Text` | Text | Message copy |

Total variants: **8** (4 kinds × 2 line variants)

---

### 27.2 Anatomy

- **Container** — tinted background per kind, drop shadow always applied
- **Icon Container** — kind-specific icon at 24px
- **Content** — optional title (`Body/14 Semibold`) and message (`Body/14`)
- **Action** — text link, `Body/14`
- **Close Container** — `Icon/Close Big` for manual dismissal

---

### 27.3 Kind → Tokens

| Kind | Icon | Icon colour | Background |
|------|------|------------|------------|
| `Info` | `Icon/Info Circle` | `Blue/40` | `Blue/10` |
| `Success` | `Icon/Circle Check Solid` | `Green/30` | `Green/10` |
| `Warning` | `Icon/Exclamation Triangle` | `Orange/50` | `Yellow/10` |
| `Alert` | `Icon/Circle Close Solid` | `Coral/50` | `Coral/10` |

**Shared across all kinds**

| Element | Token |
|---------|-------|
| Title | `Body/14 Semibold`, `Shades/90` |
| Message | `Body/14`, `Shades/80` |
| Action | `Body/14`, `Shades/80` |
| Close icon | `Shades/80` |
| Border-radius | `Sizes/04` (8px) |
| Shadow | `Elevation 2` — `0 2px 8px rgba(0,0,0,0.15)` — always on |

---

### 27.4 Lines Variant

| Variant | Height | Icon placement |
|---------|--------|----------------|
| `One` | 53px | Vertically centred |
| `Multiple` | 128px | Top-aligned |

---

### 27.5 Dimensions & Spacing

| Property | Value |
|----------|-------|
| Min width | 160px |
| Max width | 360px |
| Doc width | 328px |
| Padding | `Sizes/06` (16px) all sides |
| Gap (icon ↔ content) | `Sizes/04` (8px) |

---

### 27.6 Usage

1. **Position** — mobile: bottom of screen, centred. Desktop: bottom-right, `padding-right: 16px`.
2. **Layer order** — above all other UI elements.
3. **Non-blocking** — doesn't prevent interaction with the page beneath.
4. **Auto-dismiss** — snackbars without actions auto-dismiss after 7 seconds.
5. **One at a time** — a new snackbar replaces the current one immediately.
6. **One vs Multiple lines** — `Lines=One` for short confirmations (e.g. "Booking confirmed"); `Lines=Multiple` when the message needs a title + supporting text.
7. **Not a substitute for Alert** — for persistent, inline or page-level messages, use Alert or Banner.

---

### 27.7 Figma

| Resource | Node |
|----------|------|
| Component set | `Snackbar` — node `6668:36088` (was `6660:35833`) |

---

## 28. Tabs

Switches between content sections within the same view. Built like Button Group: a `Tabs _ Item` and a `Tabs` container.

---

### 28.1 Components & Properties

**Tabs** — node `8155:5303` — 2 variants

| Property | Type | Values |
|----------|------|--------|
| `Width` | Variant | `Hug` · `Fill` |
| `Tabs` | Slot | `Tabs _ Item` instances |

**Tabs _ Item** — node `6268:9148` — 6 variants

| Property | Type | Values / Default |
|----------|------|------------------|
| `State` | Variant | `Default` · `Hover` · `Pressed` · `Focused` · `Selected` · `Focused Selected` |
| `Label` | Text | `Label` |

---

### 28.2 States

| State | Background | Bottom border | Label |
|-------|-----------|---------------|-------|
| `Default` | — | 1px `Shades/40` | `Shades/80` |
| `Hover` | `Blue/50 (Logo) 5%`, top corners 8px | 1px `Blue/60` | `Blue/60` |
| `Pressed` | — | 1px `Blue/70` | `Blue/70` |
| `Selected` | — | 2px `Blue/50 (Logo)` | `Blue/50 (Logo)` |
| `Focused` | — | 2px `Blue/50 (Logo)` focus ring | `Blue/60` |
| `Focused Selected` | — | 2px `Blue/50 (Logo)` focus ring | `Blue/50 (Logo)` |

---

### 28.3 Specs

| Property | Value |
|----------|-------|
| Height | 40px |
| Padding | 8px V · 16px H |
| Gap between tabs | 0 — flush |
| Text style | `Body/16` |

---

### 28.4 Usage

1. **Width=Hug** — tabs hug their labels and start from the left. The bottom line runs to the end of the container. On small screens the row scrolls sideways and labels never truncate.
2. **Width=Fill** — tabs share the width equally; a label that doesn't fit ends with "…".

---

## 29. Toggle

Turns a setting on or off straight away. Rebuilt in Nov 2026.

---

### 29.1 Properties

| Property | Type | Values / Default |
|----------|------|------------------|
| `Selected` | Variant | `Off` · `On` |
| `State` | Variant | `Default` · `Hover` · `Pressed` · `Focused` · `Disabled` |
| `Icon` | Variant | `Off` · `On` — icon inside the knob |
| `Label Position` | Variant | `Right` · `Left` |
| `Label` | Boolean | `true` |
| `Text` | Text | `Label` |

Total variants: **40**

---

### 29.2 Anatomy

- **Track** — 39 × 24px, radius Full
- **Knob** — 20px circle. With `Icon=On`: `Icon/Circle Close Solid` when off, `Icon/Circle Check Solid` when on
- **Label** — `Body/16`, 12px from the track

---

### 29.3 States — Off

| State | Track | Track border | Knob | Label |
|-------|-------|--------------|------|-------|
| `Default` | `Shades/0 (White)` | 1px `Shades/50` | `Shades/60` | `Shades/80` |
| `Hover` | White + `Blue/50 (Logo) 5%` | 1px `Blue/60` | `Blue/60` | `Blue/60` |
| `Pressed` | White + `Blue/50 (Logo) 10%` | 1px `Blue/70` | `Blue/70` | `Blue/70` |
| `Focused` | as Hover + focus ring | 1px `Blue/60` | `Blue/60` | `Blue/60` |
| `Disabled` | `Shades/0 (White)` | 1px `Shades/40` | `Shades/40` | `Shades/50` |

### 29.4 States — On

| State | Track (fill + border) | Knob | Label |
|-------|----------------------|------|-------|
| `Default` | `Blue/50 (Logo)` | White | `Blue/60` |
| `Hover` | `Blue/60` | White | `Blue/60` |
| `Pressed` | `Blue/70` | White | `Blue/70` |
| `Focused` | `Blue/50 (Logo)` + focus ring | White | `Blue/60` |
| `Disabled` | `Shades/40` | White | `Shades/50` |

---

### 29.5 Usage

1. Labels are usually short. When a label wraps, the text box keeps its full width, so the gap to the toggle looks bigger than 12px (most visible with `Label Position=Left`).
2. In code, `fitToggleLabels` (see the Minibook Toggle page) narrows a wrapped label to its longest line so the gap stays 12px.
3. In Figma, break the line by hand (Shift+Enter) to get the same result.

---

### 29.6 Figma

| Resource | Node |
|----------|------|
| Component set | `Toggle` — node `3684:83220` |

---

## 30. Toggle Button

Full-width selectable button used in question flows; selected answers show a check.

---

### 30.1 Properties

| Property | Type | Values / Default |
|----------|------|------------------|
| `Selected` | Variant | `False` · `True` |
| `State` | Variant | `Default` · `Hover` · `Pressed` · `Inactive` |
| `Text` | Text | `Toggle button` |

Total variants: **8**

---

### 30.2 States

| Selected | State | Background | Border | Text | Check icon |
|----------|-------|-----------|--------|------|------------|
| False | `Default` | `Shades/0 (White)` | 1px `Shades/40` | `Shades/80` | — |
| False | `Hover` | White + `#006BFF` @5% | 1px `Blue/60` | `Blue/60` | — |
| False | `Pressed` | White + `#006BFF` @10% | 1px `Blue/70` | `Blue/70` | — |
| False | `Inactive` | `Shades/10` | — | `Shades/60` | — |
| True | `Default` | `Blue/20` | — | `Blue/60` | `Blue/60` |
| True | `Hover` | `Blue/30` | — | `Blue/60` | `Blue/60` |
| True | `Pressed` | `Blue/40` | — | `Blue/60` | `Shades/0 (White)` |
| True | `Inactive` | `Shades/10` | — | `Shades/60` | — |

Height 40px · padding 8 / 24px · radius 48px · `Body/16`.

> ⚠️ Unselected Hover / Pressed use an unbound `#006BFF` tint instead of the `Blue/50 (Logo) 5%` / `10%` variables.

---

### 30.3 Usage

1. When users go a step back to an answered quick action, or leave and come back, the answer they clicked shows as selected.
2. Text runs up to three lines, then truncates.

---

### 30.4 Figma

| Resource | Node |
|----------|------|
| Component set | `Toggle Button` — node `3703:41933` |

---

## 31. Tooltip

Short supporting text on a dark background.

| Property | Type | Values / Default |
|----------|------|------------------|
| `Type` | Variant | `Single Line` · `Multi Line` |
| `Text Field` | Text | `Supporting text` |

| Spec | Value |
|------|-------|
| Background | `Shades/95 (Black)` |
| Text | `Body/14`, `Shades/0 (White)` |
| Padding (V / H) | 4px / 8px |
| Corner radius | 2px |
| Multi Line width | 328px |

**Figma:** `Tooltip` — node `4718:32023`
