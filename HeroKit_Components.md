# HeroKit — Components

> **Version:** 1.0
> **Last updated:** 20 April 2026

---

## Table of Contents

1. [Breadcrumb](#1-breadcrumb)
2. [Button](#2-button)
3. [Checkbox](#3-checkbox)

---

## 1. Breadcrumb

A navigation aid that shows the user's current location within the page hierarchy. Helps users understand where they are and navigate back to parent pages.

---

### 1.1 Component Set: `Breadcrumb`

The `Breadcrumb` component composes up to 4 `Breadcrumb Link` instances separated by a `/` divider.

**Properties:**

| Property | Values |
|----------|--------|
| `State` | `Default` |

> The component currently supports a fixed depth of 4 links. Depth is not configurable via a property.

---

### 1.2 Sub-component: `Breadcrumb Link`

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

### 1.3 Anatomy

```
[Link label] / [Link label] / [Link label] / [Link label]
```

- Each segment is a `Breadcrumb Link` instance
- Segments are separated by a plain text `/` divider
- The last segment typically uses the `Active` state to indicate the current page

---

### 1.4 Figma

| Resource | Link |
|----------|------|
| Component set | `Breadcrumb` — node `3276:32813` |
| Sub-component | `Breadcrumb Link` — node `4721:36827` |

---

## 2. Button

The primary interactive element for triggering actions. Available in three types, two hierarchies, three sizes, and two modes (light/dark).

---

### 2.1 Properties

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

### 2.2 Types

**Pill** — the standard button. Rounded, filled or outlined, used for primary actions across the product.

**Text** — a label-only button with no background. Used for inline or low-emphasis actions. Always accompanied by an icon.

**Icon** — a circular icon-only button. Used for compact or toolbar contexts.

---

### 2.3 States — Pill (Light mode)

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

### 2.4 States — Text (Light mode, Primary)

Text buttons have no background or border — colour change only.

| State | Text colour | Notes |
|-------|------------|-------|
| `Default` | `#006BFF` | Blue 50 |
| `Hovered` | `#004BE0` | Blue 60 |
| `Pressed` | `#042CC8` | Blue 70 |
| `Focused` | `#006BFF` + `#006BFF` at 10% bg | Subtle fill behind label |
| `Disabled` | `#929CAB` | Neutral 50 |

---

### 2.5 States — Dark mode (Primary only)

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

### 2.6 Sizes

| Size | Font size | Padding (V / H) | Corner radius |
|------|-----------|-----------------|---------------|
| `Small` | 12px | 4px / 12px | 48px |
| `Medium` | 14px | 12px / 24px | 48px |
| `Large` | 16px | 12px / 24px | 48px |

> Corner radius is set to 48px across all sizes — this produces the pill shape regardless of button height.

**Icon button padding (Medium):** 12px on all sides (square).

---

### 2.7 Typography

All button labels use `IBM Plex Sans, Regular (400)`. Size varies by the `Size` property — see 2.6 above.

---

### 2.8 Figma

| Resource | Node |
|----------|------|
| Component set | `Button` — node `4921:37343` |

---

## 3. Checkbox

A form control that allows users to select one or multiple options from a set.

---

### 3.1 Properties

| Property | Values |
|----------|--------|
| `State` | `Default` · `Hover` · `Pressed` · `Focused Unselected` · `Selected` · `Focused Selected` · `Error` · `Disabled` |
| `Size` | `Medium` · `Large` |

Total variants: **16**

---

### 3.2 Anatomy

Each checkbox variant is composed of:
- A square control box with a border and optional fill
- A checkmark icon (visible in `Selected` and `Focused Selected` states only)
- A focus ring rectangle (visible in `Focused Unselected` and `Focused Selected` states)
- A text label

---

### 3.3 States

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

### 3.4 Sizes

| Size | Control box | Component height |
|------|------------|-----------------|
| `Medium` | 16×16px | 20px |
| `Large` | 24×24px | 24px |

Corner radius on control box: **2px**

---

### 3.5 Typography

Labels use `body/14-regular` at Medium size and `body/16-regular` at Large size — IBM Plex Sans, Regular (400).

---

### 3.6 Figma

| Resource | Node |
|----------|------|
| Component set | `Checkbox` — node `3130:36530` |
