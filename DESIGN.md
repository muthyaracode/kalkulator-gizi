---
name: NutriTrack Minimalist Monochrome
colors:
  surface: '#131316'
  surface-dim: '#131316'
  surface-bright: '#39393c'
  surface-container-lowest: '#0e0e11'
  surface-container-low: '#1b1b1e'
  surface-container: '#1f1f22'
  surface-container-high: '#2a2a2d'
  surface-container-highest: '#353438'
  on-surface: '#e4e1e6'
  on-surface-variant: '#c4c7c9'
  inverse-surface: '#e4e1e6'
  inverse-on-surface: '#303033'
  outline: '#8e9193'
  outline-variant: '#444749'
  surface-tint: '#c6c6c7'
  primary: '#ffffff'
  on-primary: '#2f3132'
  primary-container: '#e2e2e3'
  on-primary-container: '#636466'
  inverse-primary: '#5d5e60'
  secondary: '#c6c5cf'
  on-secondary: '#2f3038'
  secondary-container: '#4a4b53'
  on-secondary-container: '#bcbbc5'
  tertiary: '#ffffff'
  on-tertiary: '#2f3037'
  tertiary-container: '#e2e1eb'
  on-tertiary-container: '#63646c'
  error: '#ffb4ab'
  on-error: '#690005'
  error-container: '#93000a'
  on-error-container: '#ffdad6'
  primary-fixed: '#e2e2e3'
  primary-fixed-dim: '#c6c6c7'
  on-primary-fixed: '#1a1c1d'
  on-primary-fixed-variant: '#454748'
  secondary-fixed: '#e3e1ec'
  secondary-fixed-dim: '#c6c5cf'
  on-secondary-fixed: '#1a1b22'
  on-secondary-fixed-variant: '#46464e'
  tertiary-fixed: '#e2e1eb'
  tertiary-fixed-dim: '#c6c6cf'
  on-tertiary-fixed: '#1a1b22'
  on-tertiary-fixed-variant: '#45464e'
  background: '#131316'
  on-background: '#e4e1e6'
  surface-variant: '#353438'
typography:
  display-lg:
    fontFamily: Plus Jakarta Sans
    fontSize: 40px
    fontWeight: '700'
    lineHeight: 48px
    letterSpacing: -0.03em
  display-lg-mobile:
    fontFamily: Plus Jakarta Sans
    fontSize: 32px
    fontWeight: '700'
    lineHeight: 40px
    letterSpacing: -0.025em
  headline-lg:
    fontFamily: Plus Jakarta Sans
    fontSize: 28px
    fontWeight: '600'
    lineHeight: 36px
    letterSpacing: -0.02em
  headline-md:
    fontFamily: Plus Jakarta Sans
    fontSize: 22px
    fontWeight: '600'
    lineHeight: 28px
    letterSpacing: -0.015em
  headline-sm:
    fontFamily: Plus Jakarta Sans
    fontSize: 18px
    fontWeight: '600'
    lineHeight: 24px
    letterSpacing: -0.01em
  body-lg:
    fontFamily: Plus Jakarta Sans
    fontSize: 16px
    fontWeight: '400'
    lineHeight: 24px
    letterSpacing: 0em
  body-md:
    fontFamily: Plus Jakarta Sans
    fontSize: 14px
    fontWeight: '400'
    lineHeight: 20px
    letterSpacing: 0em
  body-sm:
    fontFamily: Plus Jakarta Sans
    fontSize: 12px
    fontWeight: '400'
    lineHeight: 16px
    letterSpacing: 0.01em
  label-lg:
    fontFamily: Plus Jakarta Sans
    fontSize: 14px
    fontWeight: '600'
    lineHeight: 20px
    letterSpacing: 0.01em
  label-md:
    fontFamily: Plus Jakarta Sans
    fontSize: 12px
    fontWeight: '500'
    lineHeight: 16px
    letterSpacing: 0.02em
  label-sm:
    fontFamily: Plus Jakarta Sans
    fontSize: 10px
    fontWeight: '600'
    lineHeight: 14px
    letterSpacing: 0.04em
  metric-numeral:
    fontFamily: Plus Jakarta Sans
    fontSize: 24px
    fontWeight: '700'
    lineHeight: 28px
    letterSpacing: -0.03em
rounded:
  sm: 0.25rem
  DEFAULT: 0.5rem
  md: 0.75rem
  lg: 1rem
  xl: 1.5rem
  full: 9999px
spacing:
  gutter: 1rem
  gutter-tablet: 1.5rem
  margin: 1.25rem
  margin-tablet: 2rem
  margin-desktop: 3rem
  space-xs: 0.25rem
  space-sm: 0.5rem
  space-md: 1rem
  space-lg: 1.5rem
  space-xl: 2.25rem
---

## Brand & Style

This design system expresses a refined, disciplined, and calm approach to nutrition and metabolic health. It rejects the loud, gamified, saturated neon aesthetic typical of fitness trackers in favor of quiet architectural clarity, clinical precision, and tactile satisfaction. 

### Core Aesthetic Pillars
- **Disciplined Minimalism:** Maximum reduction of visual noise. Focus resides strictly on numeric data, macro proportions, and daily ingestion cadence.
- **Editorial Monochrome:** A deliberate palette anchored in zinc, deep charcoal, and soft neutral silver tones that treats food tracking like a daily journal of intention rather than an alarmist metric board.
- **Physical Ergonomics:** Built mobile-first for fluid single-handed logging. Buttons, tap targets, and inputs prioritize thumb-zone reachability on mobile displays.
- **Indonesian Vernacular:** Designed natively around Indonesian nutritional context and meal routines (*Sarapan*, *Makan Siang*, *Makan Malam*, and *Camilan*).

## Colors

The palette leverages a dark-mode-first aesthetic inspired by tactile matte materials, deep anodized slate, and crisp high-contrast off-white accents. 

### Color Hierarchy
- **Canvas Base (`#09090B` / Deep Obsidian Charcoal):** The root background canvas provides maximum battery efficiency and ambient comfort during morning and late-night logging.
- **Surface Elevation 1 (`#18181B` / Zinc 900):** Primary container tone for cards, meal blocks, and interactive segments.
- **Surface Elevation 2 (`#27272A` / Zinc 800):** Hover states, nested rows, and input backgrounds.
- **Primary Text & High Contrast Accent (`#F4F4F5` / Zinc 100):** Prominent headlines, primary CTA buttons, active states, and crisp caloric summaries.
- **Secondary & Structural Accent (`#71717A` / Zinc 500):** Inactive states, unfilled progress bar tracks, and borders.
- **Tertiary Accent (`#A1A1AA` / Zinc 400):** Unit labels (`kkal`, `g`), timestamps, secondary metrics, and microcopy.

### Macro Progress Indicators (Tonal Monochrome Differentiation)
To maintain the monochrome aesthetic without sacrificing glanceability, macro elements rely on precise value and texture contrast rather than primary colors:
- **Kalori:** Solid Zinc 100 (`#F4F4F5`)
- **Protein:** Bright Cool Silver (`#E4E4E7`)
- **Karbohidrat (Karbo):** Mid Silver (`#A1A1AA`)
- **Lemak:** Muted Zinc (`#52525B`)

## Typography

Typography relies on `Plus Jakarta Sans` across all display, body, and metric roles. Its geometric foundation provides architectural rigor, while subtle humanist quirks ensure warmth and extreme legibility at small sizes on OLED screens.

### Numerical Hierarchy
Nutritional metrics require rapid visual parsing. Macro readouts and caloric quantities utilize the dedicated `metric-numeral` style combined with tabular figures (`font-variant-numeric: tabular-nums`) to prevent layout shifting during dynamic input updates or log alterations.

### Scale Application
- Large metric readouts (e.g., remaining calories) use `display-lg-mobile` on smartphone screens and `display-lg` on tablets.
- Meal categories (*Sarapan*, *Makan Siang*, *Makan Malam*) use `headline-sm`.
- Gram units and energy denominators (`kkal`, `g`, `mg`) are rendered in `label-sm` or `label-md` with `tertiary_color_hex` to maintain crisp visual hierarchy beneath macro numbers.

## Layout & Spacing

The layout is built around a mobile-first single-column stream that expands into a 2-column dashboard layout on tablet, and a restrained 3-column structured canvas on desktop (max content container: 1080px).

### Layout System
- **Mobile (<640px):** Single-column vertical stream. Global margins of `1.25rem` maximize screen real estate while keeping touch targets safely inside edge gutters. Sticky bottom log interaction for thumb reach.
- **Tablet (640px - 1024px):** 6-column fluid grid with `1.5rem` gutters. Left region anchors the daily summary and macro radial/linear bars; right region displays the sequential meal feed.
- **Desktop (>1024px):** 12-column fixed grid with `3rem` margins. Pinned sidebar for navigation and weekly caloric trends, center column for daily logging entries, right rail for micronutrient breakdowns and hydration.

### Spacing Rhythm
All layout items adhere to an 8pt spatial baseline (`0.25rem` / 4px increments for micro-adjustments). Internal card padding standardizes on `space-md` (16px) for compact records and `space-lg` (24px) for master summary cards.

## Elevation & Depth

To sustain a minimalist monochrome style, depth is established through tonal surface layering and razor-thin low-contrast perimeter lines rather than heavy drop shadows.

### Surface Tiers
- **Layer 0 (Canvas):** `#09090B` - Root application layer.
- **Layer 1 (Card & Module Surface):** `#18181B` - Elevated meal modules and macro dashboard cards.
- **Layer 2 (Interactive Floating Surfaces / Modals):** `#27272A` - Quick-add food bottom sheets, search overlays, and dropdown menus.

### Low-Contrast Structural Outlines
Cards and interactive blocks utilize a 1px border colored with `#27272A` (or `#3F3F46` for interactive active states). This crisp separation ensures cards stand out distinctly against the canvas without creating visual clutter.

### Ambient Illumination
When a surface floats (such as the quick-log bottom drawer or action sheet), use an ultra-diffused shadow:
- `box-shadow: 0 16px 32px -8px rgba(0, 0, 0, 0.6), 0 0 0 1px rgba(255, 255, 255, 0.06);`

## Shapes

The interface embraces a balanced modern curvature (`roundedness: 2`). This rounds standard cards to 16px (`1rem`) and large hero metric panels to 24px (`1.5rem`), softening the starkness of the monochrome palette while maintaining a structured, architectural feel.

### Geometric Rules
- **Summary Cards & Meal Containers:** `rounded-lg` (16px / `1rem`) creates a comfortable containment boundary.
- **Macro Progress Tracks:** Fully rounded pill caps (`9999px`) for both the background bar and the active fill to denote fluid nutritional consumption.
- **Form Inputs & Search Fields:** `rounded-lg` (12px to 16px) matching card curvature.
- **Micro Chips & Badges:** Subtle soft corners (8px / `0.5rem`).
- **Primary Floating Buttons:** Pill format (`9999px`) to distinguish actionable logging controls from structural data cards.

## Components

### 1. Macro Progress Bars (Sleek Linear & Segmented)
- **Container:** Full width, height of 8px (small) or 12px (featured hero). Background is `#27272A`.
- **Fills:** Solid monotone fills: Protein (`#E4E4E7`), Karbo (`#A1A1AA`), Lemak (`#52525B`). Kalori primary bar is high-contrast Zinc 100 (`#F4F4F5`).
- **Labels:** Two-row vertical layout above the bar: Label (*Protein*) in `label-sm` (`#A1A1AA`), followed by current vs target ratio (*120g / 150g*) in `label-md` tabular text.

### 2. Meal Cards (*Sarapan, Makan Siang, Makan Malam, Camilan*)
- **Default State:** Background `#18181B`, border 1px solid `#27272A`, padding `1.25rem`.
- **Header:** Displays meal title in `headline-sm`, cumulative calories in `metric-numeral` (`#F4F4F5`), and an icon button (`+`) to trigger quick entry.
- **Logged Items List:** Borderless horizontal rows separated by 8px. Left side shows item name (*Contoh: Dada Ayam Panggang 150g*) in `body-md`; right side lists calories (*248 kkal*) and macro micro-chips (*P: 46g | K: 0g | L: 5g*) in `body-sm` muted text.
- **Empty State:** Subtle dashed border `#27272A`, placeholder text *"Belum ada makanan dicatat"* in `body-md` (`#71717A`), and a low-profile text button *"Tambah Sarapan"*.

### 3. Food Logging Input Fields & Search
- **Search Bar:** Background `#18181B`, 1px border `#27272A`, icon search prefix in `#71717A`, text in `#F4F4F5`. Focused state transitions border to `#71717A` with zero outer ring glow.
- **Portion / Gramature Counter:** Stepper input with tactile `+` and `-` buttons housed in a unified pill container with an editable numeric center (`body-lg` bold, center aligned).

### 4. Buttons & Interactive Controls
- **Primary Button (CTA - Simpan / Catat):** High-contrast off-white `#F4F4F5` background, `#09090B` bold typography. Active state scales subtly down (`scale(0.98)`).
- **Secondary Button:** Solid `#27272A` background, `#F4F4F5` text, border 1px solid `#3F3F46`.
- **Ghost / Icon Button:** Transparent background, `#A1A1AA` icon color, subtle hover state to `#27272A`.

### 5. Chips & Filters
- **Filter Tags (*Semua, Favorit, Riwayat, Resep*):** 32px height, padding 6px 14px.
- **Inactive:** Background `#18181B`, text `#A1A1AA`, border 1px solid `#27272A`.
- **Active:** Background `#F4F4F5`, text `#09090B`, font weight 600.

### 6. Quick Daily Summary Banner (Hero Component)
- Positioned at the top of the mobile viewport.
- Central ring or prominent horizontal bar for **"Sisa Kalori"** with formula displayed: *Target (2,200) - Makanan (1,450) = 750 kkal*.
- 3 mini columns below for daily targets of Protein, Karbo, and Lemak with visual progress percentage indicators.