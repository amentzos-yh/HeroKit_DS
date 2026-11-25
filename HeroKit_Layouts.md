# HeroKit — Layouts

> **Version:** 1.2
> **Last updated:** 25 November 2026
> **Source:** `🌈 DS . HeroKit` → page `3. Layouts`. Figma is the source of truth when this doc and Figma disagree.
> **Naming:** colours and text styles use their Figma names. Single components are documented in `HeroKit_Components.md`.

---

## Table of Contents

1. [Bottom Nav Bars (Apps)](#1-bottom-nav-bars-apps)
2. [Footer](#2-footer)
3. [Header & Menu — Customer (Web)](#3-header--menu--customer-web)
4. [Header & Menu — Pro (Web)](#4-header--menu--pro-web)
5. [Loaders](#5-loaders)
6. [Modal, Dialog & Drawer](#6-modal-dialog--drawer)
7. [Modal _ CCF](#7-modal-_-ccf)
8. [Pro App _ Side Menu](#8-pro-app-_-side-menu)

---

## 1. Bottom Nav Bars (Apps)

### 1.1 Customer App _ Bottom Nav Bar

White bar with four tabs: Home, Chat, Jobs, Profile. Built like the Pro App bar.

| Component | Node | Properties |
|-----------|------|------------|
| `Customer App _ Bottom Nav Bar` | `8402:7992` | `Variation`: `Default` · 360 × 72px |
| `Customer App _ Bottom Nav Bar _ Tab` | `8402:7933` | `Link`: `Home` · `Chat` · `Jobs` · `Profile` · `State`: `Default` · `Active` · `Notification` (boolean) · 70 × 60px |

| Tab | EN label | GR label |
|-----|----------|----------|
| Home | Explore | — |
| Chat | Douleutaras chat | Douleutaras Συνομιλία |
| Jobs | My jobs | — |
| Profile | Profile | — |

- `Notification` shows the number indicator on Chat and Jobs only. It reuses `Pro App _ Bottom Nav Bar _ Number Indicator`.
- There is no Ideas tab anymore.

### 1.2 Pro App _ Bottom Nav Bar

| Component | Node | Properties |
|-----------|------|------------|
| `Pro App _ Bottom Nav Bar` | `4528:50846` | `Variation`: `Default` · 360 × 72px |
| `Pro App _ Bottom Nav Bar _ Tab` | `4528:50591` | `Link`: `Jobs` · `Chat` · `Notifications` · `Stat Center` · `Wallet` · `Reviews` · `State`: `Default` · `Active` · `Notification` (boolean) |
| `Pro App _ Bottom Nav Bar _ Number Indicator` | `1698:39390` | `Digits`: `1 digit` · `2 digits` · `99+ digits` · 18px high |

Tab label: 10px, Regular, `Shades/70`.

### 1.3 Behaviour

Bottom navigation behaves differently per platform (Material Design guidance):

1. **Android** — selecting a new item opens that destination's top-level screen. Scroll position, tab selection and in-line search are reset.
2. **iOS** — the destination shows the user's prior state. If they visited that section before, they return to the last screen viewed; otherwise the top-level screen.

---

## 2. Footer

Web footer, one set per breakpoint.

| Component | Node | Properties |
|-----------|------|------------|
| `Footer` | `2884:93124` | `Breakpoint`: `Mobile` · `768` · `1024` · `1280` · `1440` · `1920` · `State`: `Default` · `Open Category` · `Open Dropdown` (Mobile) |
| `Footer _ Logos` | `2884:93125` | `Logo`: `Anytime` · `Elpedison (Archived)` · `IKEA` · `Skroutz` · `Psifiakos 1` · `Leroy merlin` · `Enerwave` |

| Breakpoint | Size |
|------------|------|
| Mobile | 360 × 783px (894px with a category open) |
| 768 | 768 × 864px |
| 1024 | 1024 × 620px |
| 1280 / 1440 | 1280 / 1440 × 522px |
| 1920 | 1920 × 498px |

> ⚠️ The footer background is an unbound `#FFFFFF`, not `Shades/0 (White)`.

---

## 3. Header & Menu — Customer (Web)

| Component | Node | Properties |
|-----------|------|------------|
| `Header _ Customer _ Mobile` | `1090:15915` | `State`: `Burger` · `BurgerNotification` · `Close` · `BSDIR on scroll` · `Home on scroll` · `Language`: `Greek` · `English` · `Brand`: `Douleutaras` · `YourPro` · 360 × 64px |
| `Header _ Customer _ Desktop` | `1090:15691` | `State`: `LoggedIn` · `ProReg` · `Notification` · `BSDIR on Scroll` · `Language` · `Breakpoint`: `768+` · `768-` · `Brand` · 1280 / 768 × 80px |
| `Header _ Customer _ Desktop _ Links` | `1367:30612` | `Kind`: `BecomePartner` · `LogIn` · `AllCategories` · `Chat` · `MyJobs` · `MyAccount` · `Close` · `Language` · `Hover/Active` · `Notification` |
| `Header _ Customer _ Mobile _ Links` | `1376:34887` | `Kind`: `Chat` · `MyJobs` · `SignOut` · `AllCategories` · `BurgerClose` · `Burger` · `LogIn` · `BecomePartner` · `Settings` · `SwitchToPro` · `Language` · `Hover` · `Notification` · `Language` |
| `Header _ Jobs Drop Down` | `1091:76494` | Jobs list under My Jobs |
| `Header _ Jobs Drop Down _ Item` | `3041:48439` | `Variation`: `Default` · `Hover` · 329 × 96px |
| `Menu Drop Down` | `6417:38644` | `Variation`: `Default` · `Slot` · `3rd item` / `4th item` / `Slot Placeholder` (booleans) · 240px wide |
| `Menu Drop Down _ Item` | `6417:38733` | `Label` · `Variation`: `Default` · `Hover` · `Selected` · 40px high |
| `Megamenu _ Icon` | `3150:10323` | `Kind`: `Appliances` · `Cleaning` · `Construction` · `Doors` · `Events` · `MoreServices` · `Removals` · `Renovations` · `Urgent` · 24px |
| `Icon/Web Nav/Typo Avatar` | `7255:38238` | `State`: `Default` · `Hover` · 32px initials avatar |
| `Icon/Web Nav/…` | various | 24px header icons with number badges: Briefcase, User Outline, User Pro Outline, Notifications Outline Num 1–3, Jobs, Jobs Num 1–3, Header Burger, Header Burger Num 1, Header Burger Close, Chat Bubble Stroke, Chat Bubble Stroke Num 1–3 |

**Search header examples** (single components): `Header _ Desktop _ Search` (`1090:16009`), `… _ Search 1 Tag`, `… _ Search Active`, `… _ Search 3 Tags`, and the same three for `Header _ Mobile`.

**Notes**

1. Minimum distance between menu content and the viewport edge is 40px. If less, the scroll bar appears.

> ⚠️ A second component also called `Header / 1280 / Search` (`1090:15860`) is still on the page, to be deleted.

---

## 4. Header & Menu — Pro (Web)

| Component | Node | Properties |
|-----------|------|------------|
| `Pro Menu _ Desktop _ Header` | `6836:37455` | `Breakpoint`: `1440` · `1024` · `Credit Balance` (boolean) · 80px high |
| `Pro Menu _ Desktop _ Primary Links` | `2836:34747` | `Kind`: `Jobs` · `Stat Center` · `Notifications` · `Chat` · `State`: `Default` · `Hover` · `Pressed` |
| `Pro Menu _ Desktop _ Secondary Links` | `6836:37790` | `Dropdown`: `Submenu` · `My Jobs` |
| `Pro Menu _ Desktop _ Avatar` | `6836:37385` | `Hover`: `Off` · `On` |
| `Pro Menu _ Credit Balance` | `6836:37449` | `Hover` · `Language`: `GR` · `En` · 188 × 52px |
| `Pro Menu _ Icon Links` | `6832:33232` | `Kind`: `Chat` · `Notifications` · `Bubble`: `No` · `1 digit` · `2 digit` · `3 digit` |
| `Pro Menu _ Secondary Links` | `6833:35930` | `Kind`: `Invoices` · `Bonus` · `Referral Club` · `Settings` · `Help` · `Change to Pro` · `Logout` · `Language` · `State`: `Off` · `On` |
| `Pro Menu _ Mobile _ Header` | `6825:47366` | `Kind`: `My Jobs` · `Active` · `Completed` · `Cancelled` · `Available` · 360 × 64px |
| `Pro Menu _ Mobile _ Primary Links` | `6833:36059` | `Kind`: `My Jobs` · `Stats` · `Chat` · `Notifications` · `Hover` |
| `Pro Menu _ Mobile _ Job Links` | `2843:36178` | `Link`: `My Jobs` · `Active Jobs` · `Completed Jobs` · `Cancelled Jobs` · `Available Jobs` · `Hover` |

**Notes**

1. The Pro homepage is the Active Jobs page.
2. The main CTA says "My jobs" instead of "Active jobs".

---

## 5. Loaders

| Component | Node | Properties |
|-----------|------|------------|
| `Loader` | `6784:14533` | `Breakpoint`: `Default` (360 × 555) · `Variant2` (1440 × 555) · `Title` · `Text` · `Show Title` |
| `Loader _ USP` | `6800:42` | `State`: `Loaded` · `Loading` · `USP`: `Customer satisfaction` · `Quality of the job` · `Competitive pricing` · `Punctuality` · `Choice percentage` · `Speed` · `Communication` |
| `Loader _ Icon` | `6784:8838` | `USP`: 8 options · 88 × 88px |
| `Loader _ Skeleton Card` | `6784:14401` | `Colour`: `White` · `Grey` · 153 × 185px |
| `Loader _ AI` | `7977:9291` | `Variation`: `Beginning` · `Start` · `Default` · `Text` · 360 × 668px |

**Loader _ USP** — 37px high, padding 8 / 12px, gap 8px, radius 4px, white with 1px `Shades/30` border, `Body/14` `Shades/80`, 16px check icon.

**Loader _ Skeleton Card** — radius 4px, 1px `Shades/30` border, placeholder shapes in `Shades/10`.

### 5.1 Animation

1. Each USP is on screen for 1.3 seconds, from the moment it appears until it disappears.
2. Fade expands over 250ms and collapses over 250ms, `easeOutCubic`.
3. Skeleton cards get a gradient (shimmer) animation.
4. `Loader _ AI` loops the full animation until it fades out.

> ⚠️ Naming to clean up: `Breakpoint=Variant2` on `Loader`.

---

## 6. Modal, Dialog & Drawer

### 6.1 Components

| Component | Node | Properties |
|-----------|------|------------|
| `Modal _ Web` | `7062:29751` | `Type`: `Modal` · `Dialog` · `Drawer` · `Modal (LEGACY)` · `Breakpoint`: `Mobile` · `Small` · `Medium` · `Large` · `Mobile (Scrollbar)` · `Margins`: `On` · `Off` · `CTA` (boolean) · `Place content here` (slot) |
| `Modal _ Web _ Header` | `7220:36149` | `Kind`: `Default` · `Back Button` · `Back & Title` · `Title` · `Back` (booleans) · `Text label` · 56px high |
| `Modal _ CTA` | `6875:28582` | `Kind`: `Full width` · `Left` · `Right` · `Center` · `CTAs`: `1` · `2` · `Stroke`: `On` · `Off` |
| `Modal _ App` | `6876:30927` | `Variation`: `Default (Hug)` · `Fill` · `CTA` (boolean) · `Container Slot` |
| `Modal _ App _ Header` | `2359:71730` | `Kind`: `Close` · `Back` · `Search` · `Search Active` · `Button` (boolean, Close / Back only) · 59px high (Search: 56px) |
| `Drawer _ Item` | `4493:16471` | `State`: `Default` · `Hover` · `Pressed` · `Stroke`: `On` · `Off` · `Icon` (boolean) · `Label` · 360 × 66px |

### 6.2 Sizes (Modal _ Web)

| Breakpoint | Width |
|------------|-------|
| Mobile | 360px (full screen) |
| Small | 400px |
| Medium | 560px |
| Large | 720px |

- Fixed widths with a narrow-viewport safety rule: minimum 32px margin per side. `width: min(<fixed>, calc(100vw - 64px));` The rule only kicks in on narrow viewports (e.g. Large at a 768px viewport → 704px).
- No fixed height — the modal hugs its content. `max-height: 85vh`. When content is taller, the content area scrolls; header and footer stay fixed. The modal is vertically centred.
- Mobile: corner radius 16px on the top corners. Content padding 24px (top, sides).

### 6.3 Parts

| Part | Spec |
|------|------|
| Header (`Modal _ Web _ Header`) | 56px, padding 16px, white, bottom stroke `Shades/30`, `Icon/Close Big` 24px |
| CTA section (`Modal _ CTA`) | Padding 16px, white, top stroke `Shades/30` (`Stroke=On`). 80px with one Large button. |
| App header (`Modal _ App _ Header`) | Padding 16px, white, top corners 16px, bottom stroke `Shades/30`. See 6.3.1. |
| Scrim | `#000000` at 50% |

#### 6.3.1 Modal _ App _ Header — Kinds

| Kind | Height | Left | Middle | Right |
|------|--------|------|--------|-------|
| `Close` | 59px | `Icon/Close Big` 24px, `Blue/50 (Logo)` | — | Optional Button (Pill, Primary, Small) |
| `Back` | 59px | Button (Link, Primary, Large) with `Icon/Circle Arrow Left Outline` + label | — | Optional Button (Pill, Primary, Small) |
| `Search` | 56px | Button (Link, Primary, Large), icon only (`Icon/Circle Arrow Left Outline`) | Placeholder, `Body/16`, `Shades/50`, fills the width | `Icon/Close Big` 24px, `Blue/50 (Logo)` |
| `Search Active` | 56px | as `Search` | Typed text, `Body/16`, `Shades/80` | as `Search` |

- `Close` / `Back`: left and right items are pushed to the edges (space between). The `Button` boolean shows / hides the right button.
- `Search` / `Search Active`: gap 24px, no right button.

### 6.4 Behaviour

| Type | Scrim click | Other |
|------|-------------|-------|
| `Modal` | Dismisses | Mobile: can be dragged down; dragged all the way, it closes. |
| `Dialog` | Does **not** dismiss | Decision dialogs need an explicit action. |
| `Drawer` | Dismisses | — |

1. If the content area scrolls, the CTA section gets a stroke on top. Keep 24px between the end of the content and the CTA section.
2. **Mobile:** the modal opens full screen. On scroll, the top part stays fixed and the CTA stays visible at the bottom.
3. **App:** the user can drag the modal by its top part. Dragged all the way down, it closes. Tapping the dark area behind it closes it.

> ⚠️ Open: desktop CTA layout rules per button count (alignment and width for 1, 2 or 3 CTAs). `Modal _ CTA` currently covers 1–2 CTAs.

---

## 7. Modal _ CCF

Job request modal (customer contact form). Separate components for mobile and desktop; legacy variants are kept so existing instances don't break.

### 7.1 Components

| Component | Node | Properties |
|-----------|------|------------|
| `Modal _ CCF _ Mobile` | `7165:35006` | `Variation`: `Default` · `Scroll Bar` · `Avatar` · `Avatar Scroll Bar` · `[Legacy] Default` · `[Legacy] No margins` · `CTA` · `Slot` · 360px wide |
| `Modal _ CCF _ Mobile _ Header` | `7978:41712` | `Data Points`: `Both` · `Pros` · `Price Range` · `None` · `Category` (boolean) · `Category Label` |
| `Modal _ CCF _ Data Points` | `7978:41674` | `Breakpoint`: `Mobile` · `Desktop` · `Variation`: `Pros` · `Price` · `Pros Only` · `Price Only` · `Pros Num` · `Price Range` |
| `Modal _ CCF _ Nav` | `7986:33420` | `State`: `Default` · `No back` · `Progress Bar` (boolean) · 48px high |
| `Modal _ CCF _ Desktop` | `7171:36769` | `Variation`: `Default` · `Scroll` · `[Legacy] Default` · `[Legacy] CTA` · `[Legacy] Scroll` · `Progress Bar` · `CTA` · `Slot` |
| `Modal _ CCF _ Desktop _ Sidebar` | `7987:38928` | `Back` · `Category` · `Pros` · `Prices` (booleans) · `Category Name` · 265 × 570px |
| `Modal _ CCF _ Desktop _ Curve` | `7987:38575` | 45 × 570px, `Purple/40` |

### 7.2 Specs

| Spec | Value |
|------|-------|
| Header / sidebar background | `Purple/40` |
| Nav | Back (`Icon/Circle Arrow Left Outline`) · Progress Bar · Close (`Icon/Close Big`), padding 12 / 16px, gap 24px |
| Data point label | `Body/14`, `Shades/30` |
| Mobile sheet | White, top corners 16px |
| Desktop width | Min 760px (fits a tablet), max 850px. Only the main column changes; the sidebar keeps its width. |
| Desktop height | 570px |
| Desktop radius | 16px |
| Scrollbar | The standard custom scrollbar for HeroKit (all custom scrollbars match this one) |

### 7.3 Data points

1. Grid with 2 columns, 1 : 0.8, gap 4px. Fits the Greek labels ("Διαθέσιμοι επαγγελματίες:") without changes.
2. Values never wrap: a long value (e.g. 20.000-60.000 €) ends with "…". When a value is cut, show a tooltip with the full value on hover.
3. `Variation=Avatar` / `Avatar Scroll Bar` (mobile): the header is set to `Data Points=None`, so the category name and the avatar show together. Avatar + data points isn't a designed combination — don't switch them on together.

### 7.4 What changed (vs. the legacy modal)

1. Back and close buttons are updated.
2. Data points: new layout, same logic.
3. Progress bar sits outside the content, aligned with the buttons.
4. Curve is more compact, so the modal fits the tablet breakpoint.
5. The category is now visible inside the modal too.

> ⚠️ Open: desktop CCF modal to be aligned with the mobile one.

---

## 8. Pro App _ Side Menu

| Component | Node | Properties |
|-----------|------|------------|
| `Pro App _ Side Menu` | `1882:11981` | `Variation`: `Default` · `[Archived]` · `Name` · `Rating` · `Missing Prices` · `Idea` (booleans) · 304 × 618px |
| `Pro App _ Side Menu _ Links` | `2323:103901` | `Link`: `Invoices` · `Bonus` · `Referral Club` · `Settings` · `Help` · `Logout` · `Language` · `Profile` · `Idea` · `Hover` |

1. Opens from the left (slides left to right) and sits on the left of the screen.
2. Dismissed by tapping the scrim or the Close button.
3. Tapping the pro's profile area opens the profile in the in-app browser.
4. Some items are available only for Top Pros.
