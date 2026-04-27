# HeroKit — Components

> **Version:** 1.2
> **Last updated:** 27 April 2026

---

## Table of Contents

1. [Alert](#1-alert)
2. [Breadcrumb](#2-breadcrumb)
3. [Button](#3-button)
4. [Button Groups](#4-button-groups)
5. [Checkbox](#5-checkbox)
6. [Counter](#6-counter)
7. [Date Picker](#7-date-picker)
8. [Pagination](#8-pagination)
9. [Radio Button](#9-radio-button)
10. [Tabs](#10-tabs)
11. [Toggle](#11-toggle)

---

## 1. Alert

An inline notification that communicates status, feedback, or required attention within the flow of a page. Used for non-blocking messages such as confirmations, warnings, and errors related to the user's current task.

---

### 1.1 Properties

| Property | Values |
|----------|--------|
| `Breakpoint` | `Mobile` · `Desktop` |
| `Kind` | `Info` · `Success` · `Warning` · `Alert` |
| `Elevation` | `On` · `Off` |

Total variants: **16** (4 kinds × 2 breakpoints × 2 elevation states)

---

### 1.2 Anatomy

Each Alert variant is composed of:
- A container with a 1px border and tinted background
- An **Icon Container** — icon (16px), colour matches the kind
- A **Content** area — title (`body/14-semibold`) and message (`body/14-regular`) in neutral colour
- A **Close Container** — `Icon/Close Big` for dismissing the alert
- An **Action** text link — `body/14-regular`, Blue 50 `#006BFF`

---

### 1.3 Kind → Tokens

| Kind | Icon colour | Background | Border |
|------|------------|------------|--------|
| `Info` | `Blue/40` `#4297FF` | `Blue/10` `#E5F2FF` | `Blue/40` `#4297FF` |
| `Success` | `Green/30` `#1FC198` | `Green/10` `#E6F4F1` | `Green/30` `#1FC198` |
| `Warning` | `Orange/50` `#EF9E00` | `Orange/10` `#FEFBF5` | `Orange/50` `#EF9E00` |
| `Alert` | `Coral/50` `#E65651` | `Coral/10` `#FEF8F8` | `Coral/50` `#E65651` |

**Shared across all kinds**

| Element | Token |
|---------|-------|
| Title | `body/14-semibold`, Neutral 90 `#232429` |
| Message | `body/14-regular`, Neutral 80 `#3A3D46` |
| Action | `body/14-regular`, Neutral 80 `#3A3D46` |
| Close icon | Neutral 80 `#3A3D46` |
| Border-radius | `--size-02` (4px) |

---

### 1.4 Elevation

| Value | Effect |
|-------|--------|
| `Off` | No shadow — flat appearance |
| `On` | Drop shadow applied — use when the alert overlaps content |

---

### 1.5 Breakpoint Specs

| Spec | Mobile | Desktop |
|------|--------|---------|
| Padding | `--size-04` / `--size-05` (8px V / 12px H) | `--size-05` / `--size-06` (12px V / 16px H) |
| Layout | Stacked — text and action on separate lines | Inline — text and action on the same row |
| Gap (icon ↔ content) | `--size-04` (8px) | `--size-04` (8px) |
| Icon alignment | Top of first text line | Vertically centred |

---

### 1.6 Usage

1. **Width** — In the design system file, variants are drawn at fixed widths (328px mobile, 690px desktop) for documentation. **In product use, set the Alert to fill its container.**
2. **Elevation** — Use `Elevation=On` when the alert floats above page content. Use `Elevation=Off` for inline alerts within the page flow.
3. **Dismissible** — All variants include a `Close Container`. Show or hide it depending on whether the alert should be dismissible.

---

### 1.7 Figma

| Resource | Node |
|----------|------|
| Component set | `Alert Notice` — node `863:23836` |

---

## 2. Breadcrumb

A navigation aid that shows the user's current location within the page hierarchy. Helps users understand where they are and navigate back to parent pages.

---

### 2.1 Component Set: `Breadcrumb`

The `Breadcrumb` component composes up to 4 `Breadcrumb Link` instances separated by a `/` divider.

**Properties:**

| Property | Values |
|----------|--------|
| `State` | `Default` |

> The component currently supports a fixed depth of 4 links. Depth is not configurable via a property.

---

### 2.2 Sub-component: `Breadcrumb Link`

The interactive element within a breadcrumb trail. Each link has its own state.

**Properties:**

| Property | Values |
|----------|--------|
| `State` | `Default` · `Hover` · `Active` · `Disabled` |

**State definitions:**

| State | Colour | Hex | Underline | Notes |
|-------|--------|-----|-----------|-------|
| `Default` | Blue 50 | `#006BFF` | No | Standard unvisited link |
| `Hover` | Blue 60 | `#004BE0` | Yes | On mouse hover |
| `Active` | Neutral 80 | `#3A3D46` | No | Current page in the trail |
| `Disabled` | Neutral 40 | `#B2BBC7` | No | Non-interactive |

**Typography:** `body/14-regular` — IBM Plex Sans, Regular (400), 14px

---

### 2.3 Anatomy

```
[Link label] / [Link label] / [Link label] / [Link label]
```

- Each segment is a `Breadcrumb Link` instance
- Segments are separated by a plain text `/` divider
- The last segment typically uses the `Active` state to indicate the current page

---

### 2.4 Figma

| Resource | Link |
|----------|------|
| Component set | `Breadcrumb` — node `3276:32813` |
| Sub-component | `Breadcrumb Link` — node `4721:36827` |

---

## 3. Button

The primary interactive element for triggering actions. Available in three types, two hierarchies, three sizes, and two modes (light/dark).

---

### 3.1 Properties

| Property | Values |
|----------|--------|
| `Mode` | `Light` · `Dark` |
| `Type` | `Pill` · `Text` · `Icon` |
| `Icon` | `Yes` · `No` · `N/A` (Icon type only) |
| `Hierarchy` | `Primary` · `Secondary` |
| `Size` | `Small` · `Medium` · `Large` |
| `State` | `Default` · `Hovered` · `Pressed` · `Focused` · `Disabled` |

Total variants: **210**

---

### 3.2 Types

**Pill** — the standard button. Rounded, filled or outlined, used for primary actions across the product.

**Text** — a label-only button with no background. Used for inline or low-emphasis actions. Always accompanied by an icon.

**Icon** — a circular icon-only button. Used for compact or toolbar contexts.

---

### 3.3 States — Pill (Light mode)

#### Primary

| State | Background | Text | Border | Notes |
|-------|-----------|------|--------|-------|
| `Default` | `#006BFF` | `#FFFFFF` | — | Blue 50 |
| `Hovered` | `#004BE0` | `#FFFFFF` | — | Blue 60 |
| `Pressed` | `#042CC8` | `#FFFFFF` | — | Blue 70 |
| `Focused` | `#006BFF` | `#FFFFFF` | `#006BFF` + inner white shadow (3px) | Focus ring via inner shadow |
| `Disabled` | `#F3F5F7` | `#515867` | — | Neutral 10 bg, Neutral 70 text |

#### Secondary

| State | Background | Text | Border | Notes |
|-------|-----------|------|--------|-------|
| `Default` | `#FFFFFF` | `#006BFF` | `#006BFF` | Outlined |
| `Hovered` | `#006BFF` at 5% | `#004BE0` | `#004BE0` | Subtle blue tint |
| `Disabled` | — | `#515867` | `#B2BBC7` | No fill, muted border |

---

### 3.4 States — Text (Light mode, Primary)

Text buttons have no background or border — colour change only.

| State | Text colour | Notes |
|-------|------------|-------|
| `Default` | `#006BFF` | Blue 50 |
| `Hovered` | `#004BE0` | Blue 60 |
| `Pressed` | `#042CC8` | Blue 70 |
| `Focused` | `#006BFF` + `#006BFF` at 10% bg | Subtle fill behind label |
| `Disabled` | `#929CAB` | Neutral 50 |

---

### 3.5 States — Dark mode (Primary only)

Dark mode inverts the colour logic — white/light backgrounds with blue text.

#### Pill Primary (Dark)

| State | Background | Text | Notes |
|-------|-----------|------|-------|
| `Default` | `#FFFFFF` | `#004BE0` | White bg, Blue 60 text |
| `Hovered` | `#E5F2FF` | `#042CC8` | Blue 10 bg, Blue 70 text |
| `Pressed` | `#CFE6FF` | `#042CC8` | Blue 20 bg, Blue 70 text |

#### Icon Primary (Dark)

| State | Background | Notes |
|-------|-----------|-------|
| `Default` | `#FFFFFF` | White |
| `Hovered` | `#E5F2FF` | Blue 10 |
| `Pressed` | `#CFE6FF` | Blue 20 |

> Sizes (Small / Medium / Large) follow the same padding and font size rules as Light mode — only colours differ.

---

### 3.6 Sizes

| Size | Font size | Padding (V / H) | Corner radius |
|------|-----------|-----------------|---------------|
| `Small` | 12px | 4px / 12px | 48px |
| `Medium` | 14px | 12px / 24px | 48px |
| `Large` | 16px | 12px / 24px | 48px |

> Corner radius is set to 48px across all sizes — this produces the pill shape regardless of button height.

**Icon button padding (Medium):** 12px on all sides (square).

---

### 3.7 Typography

All button labels use `IBM Plex Sans, Regular (400)`. Size varies by the `Size` property — see 3.6 above.

---

### 3.8 Figma

| Resource | Node |
|----------|------|
| Component set | `Button` — node `4921:37343` |

---

## 4. Button Groups

A pair of toggle-style button components used to present a set of mutually exclusive options. Available in two orientations — Vertical (pill-shaped, with label and icon) and Horizontal (icon-only with label below).

---

### 4.1 Sub-components

| Component | Node | Description |
|-----------|------|-------------|
| `Button Group _ Vertical` | `5038:41083` | Pill-shaped button with icon + label, 2 sizes |
| `Button Group _ Horizontal` | `6268:9263` | Circular icon button with label below |

---

### 4.2 Button Group _ Vertical

**Properties:**

| Property | Values |
|----------|--------|
| `Size` | `Small` · `Large` |
| `State` | `Default` · `Hover` · `Pressed` · `Selected` |

Total variants: **8**

**States:**

| State | Background | Border | Text / Icon | Notes |
|-------|-----------|--------|------------|-------|
| `Default` | None | `#B2BBC7` | `#232323` | Neutral 40 border |
| `Hover` | Blue 50 @5% | `#004BE0` | `#004BE0` | Blue 60 |
| `Pressed` | Blue 50 @10% | `#042CC8` | `#042CC8` | Blue 70 |
| `Selected` | `#006BFF` | — | `#FFFFFF` | Blue 50 fill, white content |

**Sizes:**

| Size | Height | Padding (H) | Font size | Icon size |
|------|--------|-------------|-----------|-----------|
| `Small` | 34px | 16px | 14px | 16px |
| `Large` | 48px | 24px | 16px | 24px |

Corner radius: **999px** (full pill)

---

### 4.3 Button Group _ Horizontal

**Properties:**

| Property | Values |
|----------|--------|
| `State` | `Default` · `Hover` · `Pressed` · `Selected` |

Total variants: **4**

**States:**

| State | Icon Container bg | Icon Container border | Icon | Label | Notes |
|-------|------------------|----------------------|------|-------|-------|
| `Default` | `#FFFFFF` | `#B2BBC7` | `#006BFF` | `#232323` | Neutral 40 border |
| `Hover` | `#FFFFFF` + Blue 50 @5% | `#004BE0` | `#004BE0` | `#004BE0` | Blue 60 |
| `Pressed` | `#FFFFFF` + Blue 50 @10% | `#042CC8` | `#042CC8` | `#004BE0` | Blue 70 |
| `Selected` | `#006BFF` | — | `#FFFFFF` | `#004BE0` | Blue 50 fill, white icon |

**Dimensions:**

| Element | Size |
|---------|------|
| Icon Container | 48×48px |
| Total height (with label) | 72px |
| Corner radius | 999px |

**Typography:** Label uses `label/12-regular` — IBM Plex Sans, Regular (400), 12px.

---

### 4.4 Layout — Good Practices

**Vertical (Tab bar)**

| Property | Value |
|----------|-------|
| Container padding | `--size-06` (16px) all sides |
| Gap between items | `--size-05` (12px) |

- Labels should be short — one word where possible. Long labels break the layout.

**Horizontal (Button Group Bar)**

| Property | With icons | Without icons |
|----------|-----------|---------------|
| Container padding | `--size-06` (16px) all sides | `--size-06` (16px) all sides |
| Gap between items | `--size-05` (12px) | `--size-06` (16px) |
| Min. button width | 80px | 80px |
| Max. container width | 328px (mobile) | 328px (mobile) |
| Min. container width | 480px (desktop) | 480px (desktop) |

- Buttons use **Fill, no hug** — they stretch equally to fill the container width.
- Keep labels short — truncate or abbreviate rather than wrapping.

---

### 4.5 Figma

| Resource | Node |
|----------|------|
| `Button Group _ Vertical` | node `5038:41083` |
| `Button Group _ Horizontal` | node `6268:9263` |

---

## 5. Checkbox

A form control that allows users to select one or multiple options from a set.

---

### 11.1 Properties

| Property | Values |
|----------|--------|
| `State` | `Default` · `Hover` · `Pressed` · `Focused Unselected` · `Selected` · `Focused Selected` · `Error` · `Disabled` |
| `Size` | `Medium` · `Large` |

Total variants: **16**

---

### 11.2 Anatomy

Each checkbox variant is composed of:
- A square control box with a border and optional fill
- A checkmark icon (visible in `Selected` and `Focused Selected` states only)
- A focus ring rectangle (visible in `Focused Unselected` and `Focused Selected` states)
- A text label

---

### 11.3 States

| State | Box background | Box border | Label colour | Checkmark | Notes |
|-------|---------------|------------|--------------|-----------|-------|
| `Default` | `#FFFFFF` | `#B2BBC7` | `#232323` | — | Neutral 40 border |
| `Hover` | `#FFFFFF` + Blue 50 @5% | `#004BE0` | `#004BE0` | — | Blue 60 |
| `Pressed` | `#FFFFFF` + Blue 50 @10% | `#042CC8` | `#042CC8` | — | Blue 70 |
| `Focused Unselected` | `#FFFFFF` + Blue 50 @5% | `#004BE0` | `#004BE0` | — | + `#006BFF` focus ring |
| `Selected` | `#006BFF` | `#006BFF` | `#004BE0` | `#FFFFFF` | Blue 50 fill, white check |
| `Focused Selected` | `#006BFF` | `#006BFF` | `#004BE0` | `#FFFFFF` | + `#006BFF` focus ring |
| `Error` | `#FFFFFF` | `#E65651` | `#E65651` | — | Coral 50 |
| `Disabled` | `#FFFFFF` | `#B2BBC7` | `#929CAB` | — | Neutral 40 border, Neutral 50 label |

---

### 11.4 Sizes

| Size | Control box | Component height |
|------|------------|-----------------|
| `Medium` | 16×16px | 20px |
| `Large` | 24×24px | 24px |

Corner radius on control box: **2px**

---

### 11.5 Typography

Labels use `body/14-regular` at Medium size and `body/16-regular` at Large size — IBM Plex Sans, Regular (400).

---

### 11.6 Figma

| Resource | Node |
|----------|------|
| Component set | `Checkbox` — node `3130:36530` |

---

## 6. Counter

A stepper input that lets users increment or decrement a numeric value using `+` and `−` buttons. Used when the value is bounded and users are unlikely to need large jumps.

---

### 11.1 Properties

| Property | Values |
|----------|--------|
| `State` | `Default` · `Hover Plus` · `Hover Minus` · `Minimum` · `Maximum` |

Total variants: **5**

---

### 11.2 Anatomy

Each Counter variant is composed of three sections in a horizontal row:
- **Minus** — decrement button with `Icon/Remove Big`
- **Number** — current value display
- **Plus** — increment button with `Icon/Add Big`

---

### 11.3 States

| State | Minus bg | Minus border | Minus icon | Plus bg | Plus border | Plus icon | Number | Notes |
|-------|---------|-------------|-----------|--------|------------|----------|--------|-------|
| `Default` | `#FFFFFF` | `#929CAB` | `#3A3D46` | `#FFFFFF` | `#929CAB` | `#3A3D46` | `#3A3D46` | Both buttons active |
| `Hover Minus` | `#FFFFFF` + Blue 50 @5% | `#004BE0` | `#004BE0` | `#FFFFFF` | `#929CAB` | `#3A3D46` | `#3A3D46` | Minus hovered |
| `Hover Plus` | `#FFFFFF` | `#929CAB` | `#3A3D46` | `#FFFFFF` + Blue 50 @5% | `#004BE0` | `#004BE0` | `#3A3D46` | Plus hovered |
| `Minimum` | `#FFFFFF` | `#B2BBC7` | `#B2BBC7` | `#FFFFFF` | `#929CAB` | `#3A3D46` | `#3A3D46` | Lower bound reached — Minus disabled |
| `Maximum` | `#FFFFFF` | `#929CAB` | `#3A3D46` | `#FFFFFF` | `#B2BBC7` | `#B2BBC7` | `#3A3D46` | Upper bound reached — Plus disabled |

---

### 11.4 Usage Notes

1. Use when the selectable range is up to 10–15 items. For larger numbers use quick-action inputs instead.
2. The user cannot type a number directly — increment/decrement only.
3. The component has a **fixed width** — do not stretch it to fill containers.

---

### 11.5 Typography

Number display uses `body/18-semibold` — IBM Plex Sans, SemiBold (600), 18px.

---

### 11.6 Dimensions

| Property | Value |
|----------|-------|
| Width | 134px |
| Height | 32px |

---

### 11.7 Layout

- **Gap between label and counter:** `--size-07` (24px)
- **Gap between counter rows:** `--size-06` (16px)

---

### 11.8 Figma

| Resource | Node |
|----------|------|
| Component set | `Counter` — node `4396:51463` |

---

## 7. Date Picker

A calendar UI that allows users to select a date. Composed of a `Date Picker _ Day` sub-component assembled into a parent `Date Picker` component.

---

### 11.1 Sub-components

| Component | Node | Description |
|-----------|------|-------------|
| `Date Picker _ Day` | `6505:45807` | Individual day cell in the calendar grid |

---

### 11.2 Date Picker _ Day

**Properties:**

| Property | Values |
|----------|--------|
| `Kind` | `Current Month` · `Another Month` |
| `State` | `Default` · `Hover` · `Pressed` · `Selected` |

Total variants: **8**

**States:**

| Kind | State | Background | Text | Notes |
|------|-------|-----------|------|-------|
| Current Month | `Default` | `#FFFFFF` | `#3A3D46` | Neutral 80 — in-range day |
| Another Month | `Default` | `#FFFFFF` | `#929CAB` | Neutral 50 — out-of-range day |
| Both | `Hover` | `#F5FAFF` | `#004BE0` | Blue 5 bg, Blue 60 text |
| Both | `Pressed` | `#E5F2FF` | `#042CC8` | Blue 10 bg, Blue 70 text |
| Both | `Selected` | `#006BFF` | `#FFFFFF` | Blue 50 fill, white text |

Dimensions: **40×40px** · Typography: `body/16-regular`

---

### 11.3 Parent: `Date Picker`

One variant (`Kind=Default`). Composed of three sections:

| Section | Height | Description |
|---------|--------|-------------|
| `Month` | 48px | Month/year header with prev/next navigation |
| `Days` | 272px | 7-column calendar grid of `Date Picker _ Day` instances |
| `CTA` | 46px | Confirm / cancel actions |

Overall dimensions: **312×366px**

---

### 11.4 Figma

| Resource | Node |
|----------|------|
| Component set | `Date Picker` — node `6537:41204` |
| Sub-component | `Date Picker _ Day` — node `6505:45807` |

---

## 8. Pagination

A navigation control that allows users to move through a multi-page dataset. Composed of three sub-components assembled into a parent `Pagination` component.

---

### 11.1 Sub-components

| Component | Node | Description |
|-----------|------|-------------|
| `Pagination _ Page Number` | `6488:27789` | Individual page number button |
| `Pagination _ PrevNext` | `6492:27895` | Previous and Next arrow buttons |
| `Pagination _ Ellipsis` | `6494:27929` | Separator between non-adjacent page numbers |

---

### 11.2 Pagination _ Page Number

| Property | Values |
|----------|--------|
| `State` | `Default` · `Active` · `Hover` |

| State | Background | Text | Notes |
|-------|-----------|------|-------|
| `Default` | `#FFFFFF` | `#929CAB` | Neutral 50 — unvisited page |
| `Active` | `#006BFF` | `#FFFFFF` | Blue 50 — current page |
| `Hover` | `#F5FAFF` | `#004BE0` | Blue 5 bg, Blue 60 text |

Dimensions: **40×40px**

---

### 11.3 Pagination _ PrevNext

| Property | Values |
|----------|--------|
| `PrevNext` | `Previous` · `Next` |
| `State` | `Default` · `Hover` · `Inactive` |

| State | Background | Icon | Notes |
|-------|-----------|------|-------|
| `Default` | `#FFFFFF` | `#006BFF` | Blue 50 icon |
| `Hover` | `#F5FAFF` | `#006BFF` | Blue 5 bg |
| `Inactive` | `#FFFFFF` | `#B2BBC7` | Neutral 40 — disabled |

Dimensions: **40×40px**

---

### 11.4 Pagination _ Ellipsis

| State | Background | Text | Notes |
|-------|-----------|------|-------|
| `Default` | `#FFFFFF` | `#929CAB` | Neutral 50 — non-interactive |

Dimensions: **40×40px**

---

### 11.5 Parent: `Pagination`

The parent component assembles sub-components into a full pagination strip. Five layout variants are available:

| Variant | Description |
|---------|-------------|
| `2 Pages` | Previous · 1 · 2 · Next |
| `3 Pages` | Previous · 1 · 2 · 3 · Next |
| `First Page Open` | Previous (inactive) · 1 · 2 · 3 · … · Next |
| `In-between Page Open` | Previous · … · n · n+1 · n+2 · … · Next |
| `Last Page Open` | Previous · … · n-2 · n-1 · n · Next (inactive) |

---

### 11.6 Figma

| Resource | Node |
|----------|------|
| Component set | `Pagination` — node `6494:27987` |
| `Pagination _ Page Number` | node `6488:27789` |
| `Pagination _ PrevNext` | node `6492:27895` |
| `Pagination _ Ellipsis` | node `6494:27929` |

---

## 9. Radio Button

A form control that allows users to select a single option from a set of mutually exclusive choices.

---

### 11.1 Properties

| Property | Values |
|----------|--------|
| `State` | `Default` · `Hover` · `Pressed` · `Focused Unselected` · `Selected` · `Focused Selected` · `Error` · `Disabled` |

Total variants: **8**

---

### 11.2 Anatomy

Each Radio Button variant is composed of:
- A circular control with a border and optional fill
- An inner dot (visible in `Selected` and `Focused Selected` states only)
- A focus ring (visible in `Focused Unselected` and `Focused Selected` states)
- A text label

---

### 11.3 States

| State | Control background | Border | Label colour | Inner dot | Notes |
|-------|-------------------|--------|--------------|-----------|-------|
| `Default` | `#FFFFFF` | `#929CAB` | `#232323` | — | Neutral 50 border |
| `Hover` | `#FFFFFF` + Blue 50 @5% | `#004BE0` | `#004BE0` | — | Blue 60 |
| `Pressed` | `#FFFFFF` + Blue 50 @10% | `#042CC8` | `#042CC8` | — | Blue 70 |
| `Focused Unselected` | `#FFFFFF` + Blue 50 @5% | `#004BE0` | `#004BE0` | — | + `#006BFF` focus ring |
| `Selected` | `#006BFF` | `#006BFF` | `#004BE0` | `#FFFFFF` | Blue 50 fill, white dot |
| `Focused Selected` | `#006BFF` | `#006BFF` | `#004BE0` | `#FFFFFF` | + `#006BFF` focus ring |
| `Error` | `#FFFFFF` | `#E65651` | `#E65651` | — | Coral 50 |
| `Disabled` | `#FFFFFF` | `#B2BBC7` | `#929CAB` | — | Neutral 40 border, Neutral 50 label |

---

### 11.4 Typography

Labels use `body/16-regular` — IBM Plex Sans, Regular (400), 16px.

---

### 11.5 Layout

- **Gap between radio buttons:** `--size-06` (16px)
- **Gap between group title and first radio button:** `--size-07` (24px)

---

### 11.6 Figma

| Resource | Node |
|----------|------|
| Component set | `Radio button` — node `3073:32039` |

---

## 11. Toggle

A binary switch control that lets users turn a setting on or off. Used as an immediate-action alternative to a checkbox when the change takes effect without form submission.

---

### 11.1 Properties

| Property | Values |
|----------|--------|
| `State` | `Active` · `Default` · `Hover` · `Pressed` · `Inactive` |
| `Icon` | `On` · `Off` |

Total variants: **10**

---

### 11.2 Anatomy

Each Toggle variant is composed of:
- A **Track** — the pill-shaped container, changes colour per state
- A **Knob** — the circular handle indicating the current position
- An optional **Icon** inside the knob — `Icon/Circle Check Solid` when active, `Icon/Circle Close Solid` when inactive or default

---

### 11.3 States

| State | Track fill | Icon colour | Notes |
|-------|-----------|-------------|-------|
| `Active` | `#006BFF` | `#FFFFFF` | Blue 50 — toggle is on |
| `Default` | `#717C8E` | `#717C8E` | Neutral 60 — toggle is off |
| `Hover` | `#004BE0` | `#004BE0` | Blue 60 |
| `Pressed` | `#042CC8` | `#042CC8` | Blue 70 |
| `Inactive` | `#B2BBC7` | `#B2BBC7` | Neutral 40 — disabled |

---

### 11.4 Icon property

| Value | Icon used | Appears in |
|-------|-----------|------------|
| `On` | `Icon/Circle Check Solid` (Active) · `Icon/Circle Close Solid` (all others) | Knob |
| `Off` | No icon | Knob |

---

### 11.5 Dimensions

| Property | Value |
|----------|-------|
| Width | 39px |
| Height | 24px |
| Corner radius | 999px (full pill) |

---

### 11.6 Figma

| Resource | Node |
|----------|------|
| Component set | `Toggle` — node `3684:83220` |

---

## 10. Tabs

A horizontal navigation control that switches between content sections within the same view. Each tab item is an individual component assembled into a Tab Bar.

---

### 11.1 Properties

| Property | Values |
|----------|--------|
| `State` | `Default` · `Hover` · `Pressed` · `Focused` · `Selected` |

Total variants: **5**

---

### 11.2 Anatomy

Each Tab item is composed of:
- A **Label** — text that changes colour per state
- A **bottom border** — visible only in the `Selected` state, indicating the active tab

Tabs are assembled side by side in a **Tab Bar** with no gap between items — spacing is handled by padding only.

---

### 11.3 States

| State | Label colour | Notes |
|-------|-------------|-------|
| `Default` | `#3A3D46` | Neutral 80 |
| `Hover` | `#004BE0` | Blue 60 |
| `Pressed` | `#004BE0` | Blue 60 |
| `Focused` | `#004BE0` | Blue 60 |
| `Selected` | `#004BE0` | Blue 60 — active tab, bottom border visible |

---

### 11.4 Dimensions & Spacing

| Property | Value |
|----------|-------|
| Height | 40px |
| Padding | 8px (V) · 16px (H) |
| Gap between tabs | 0px — flush, no gap |

---

### 11.5 Typography

Labels use `body/16-regular` — IBM Plex Sans, Regular (400), 16px.

---

### 11.6 Figma

| Resource | Node |
|----------|------|
| Component set | `Tabs` — node `6268:9148` |
