---
name: Heritage Performance
colors:
  surface: '#f8fafb'
  surface-dim: '#d8dadb'
  surface-bright: '#f8fafb'
  surface-container-lowest: '#ffffff'
  surface-container-low: '#f2f4f5'
  surface-container: '#eceeef'
  surface-container-high: '#e6e8e9'
  surface-container-highest: '#e1e3e4'
  on-surface: '#191c1d'
  on-surface-variant: '#564337'
  inverse-surface: '#2e3132'
  inverse-on-surface: '#eff1f2'
  outline: '#897365'
  outline-variant: '#dcc1b1'
  surface-tint: '#944a00'
  primary: '#944a00'
  on-primary: '#ffffff'
  primary-container: '#e67e22'
  on-primary-container: '#502600'
  inverse-primary: '#ffb783'
  secondary: '#545f6c'
  on-secondary: '#ffffff'
  secondary-container: '#d8e4f3'
  on-secondary-container: '#5a6572'
  tertiary: '#006b58'
  on-tertiary: '#ffffff'
  tertiary-container: '#2cac90'
  on-tertiary-container: '#00392e'
  error: '#ba1a1a'
  on-error: '#ffffff'
  error-container: '#ffdad6'
  on-error-container: '#93000a'
  primary-fixed: '#ffdcc5'
  primary-fixed-dim: '#ffb783'
  on-primary-fixed: '#301400'
  on-primary-fixed-variant: '#713700'
  secondary-fixed: '#d8e4f3'
  secondary-fixed-dim: '#bcc8d6'
  on-secondary-fixed: '#111d27'
  on-secondary-fixed-variant: '#3d4854'
  tertiary-fixed: '#82f7d8'
  tertiary-fixed-dim: '#65dabc'
  on-tertiary-fixed: '#002019'
  on-tertiary-fixed-variant: '#005142'
  background: '#f8fafb'
  on-background: '#191c1d'
  surface-variant: '#e1e3e4'
  heritage-red: '#C0392B'
  industrial-grey: '#555555'
  deep-charcoal: '#222222'
  white: '#FFFFFF'
typography:
  headline-xl:
    fontFamily: Montserrat
    fontSize: 48px
    fontWeight: '700'
    lineHeight: 56px
    letterSpacing: -0.02em
  headline-lg:
    fontFamily: Montserrat
    fontSize: 32px
    fontWeight: '700'
    lineHeight: 40px
    letterSpacing: -0.01em
  headline-md:
    fontFamily: Montserrat
    fontSize: 24px
    fontWeight: '600'
    lineHeight: 32px
  headline-sm:
    fontFamily: Montserrat
    fontSize: 20px
    fontWeight: '600'
    lineHeight: 28px
  body-lg:
    fontFamily: Inter
    fontSize: 18px
    fontWeight: '400'
    lineHeight: 28px
  body-md:
    fontFamily: Inter
    fontSize: 16px
    fontWeight: '400'
    lineHeight: 24px
  body-sm:
    fontFamily: Inter
    fontSize: 14px
    fontWeight: '400'
    lineHeight: 20px
  label-md:
    fontFamily: Inter
    fontSize: 14px
    fontWeight: '600'
    lineHeight: 16px
    letterSpacing: 0.05em
  label-sm:
    fontFamily: Inter
    fontSize: 12px
    fontWeight: '500'
    lineHeight: 16px
  headline-xl-mobile:
    fontFamily: Montserrat
    fontSize: 32px
    fontWeight: '700'
    lineHeight: 40px
  headline-lg-mobile:
    fontFamily: Montserrat
    fontSize: 28px
    fontWeight: '700'
    lineHeight: 36px
rounded:
  sm: 0.25rem
  DEFAULT: 0.5rem
  md: 0.75rem
  lg: 1rem
  xl: 1.5rem
  full: 9999px
spacing:
  base: 8px
  container-max: 1280px
  gutter: 24px
  margin-mobile: 16px
  margin-desktop: 48px
---

## Brand & Style

This design system balances 60 years of automotive heritage with a forward-thinking, high-tech distribution model. The personality is authoritative, industrial, and hyper-efficient, designed to instill confidence in B2B partners and retail customers alike.

The visual direction follows a **Modern Corporate** aesthetic with **Industrial Minimalism**. It utilizes clean lines, structured grids, and high-performance imagery to evoke the precision of automotive engineering. The interface should feel robust and reliable, avoiding unnecessary decorative flourishes in favor of utility and clarity. 

Key attributes:
- **Trustworthy:** Established through strong typography and a weighted color palette.
- **Efficient:** Minimalist layouts that prioritize part discovery and technical specifications.
- **Precision:** Perfect alignment and consistent spacing mirroring mechanical accuracy.

## Colors

The palette is anchored by a high-visibility **Orange** (Primary), signaling energy and the "AutHaus" brand identity. This is grounded by **Deep Charcoal** (Secondary/Midnight Blue variant) to provide corporate authority and a premium industrial feel.

- **Primary (Orange):** Used for primary actions, branding, and highlighting critical path elements.
- **Secondary (Midnight Blue):** Used for headers, footers, and structural components to provide a stable, weighted foundation.
- **Tertiary (Teal):** Applied sparingly for technical highlights, "Total Automotive Concept" callouts, and success states.
- **Neutrals:** A range of cool greys ensure the interface remains clean. Light Grey (#F4F6F7) is the standard page background to reduce eye strain compared to pure white, while Deep Charcoal (#222222) ensures maximum legibility for body text.

## Typography

The typography system uses a pairing of **Montserrat** and **Inter**. 

- **Montserrat** is chosen for headlines to provide a bold, geometric, and modern industrial feel. Its wide stance conveys stability and strength.
- **Inter** is the workhorse for all body copy and UI labels. It offers exceptional legibility at small sizes, which is critical for dense automotive parts catalogs and technical specifications.

For Thai language support, **Kanit** should be mapped as the primary fallback, matching Montserrat's geometric qualities and weight distribution. Use tight letter-spacing on large headlines to maintain a "high-performance" look, while keeping body copy tracking at zero for maximum readability.

## Layout & Spacing

This design system utilizes a **Fixed Grid** model for desktop to maintain a controlled, professional presentation of technical data. 

- **Grid:** A 12-column grid system is used for desktop (1280px max-width).
- **Rhythm:** An 8px base unit governs all spacing. Vertical margins between sections should typically be 64px or 80px to create "Generous Whitespace," preventing the industrial content from feeling cluttered.
- **Mobile Adaptation:** On mobile, the layout collapses to a single column with 16px side margins. Cards and data tables should allow for horizontal swiping where necessary to preserve data integrity.

## Elevation & Depth

To maintain a "High-Tech" feel, depth is achieved through **Tonal Layers** and **Ambient Shadows**. 

- **Surface Levels:** The primary background is Light Grey. Elevated elements like product cards or search containers use Pure White surfaces.
- **Shadows:** Use very soft, diffused shadows (Blur: 16px, Spread: -4px, Opacity: 8%) with a slight Midnight Blue tint to keep them from looking muddy.
- **Interactive States:** Hovering over interactive elements should slightly increase shadow depth and elevate the element (Y-offset: -2px), signaling responsiveness and precision.

## Shapes

The shape language is "Modern-Industrial." While the grid is sharp and rigid, UI components utilize a **Rounded** (0.5rem / 8px) corner radius. This strikes a balance between the "hard" nature of automotive parts and the "soft" approachable nature of a premium service brand. Large containers (like Hero sections) may use a larger 16px radius to feel more contemporary.

## Components

### Buttons
- **Primary:** Solid Orange background with white text. High-contrast, bold, and clear.
- **Secondary:** Deep Charcoal borders with Charcoal text (Ghost style) for less urgent actions.
- **Tertiary:** Teal text with no background, used for "View Details" or "Technical Specs."

### Cards
- Pure White background, 8px corner radius, and subtle ambient shadow. 
- Use a 1px Light Grey border (#D1D5DB) to define boundaries on white backgrounds if shadows are insufficient.

### Input Fields
- Structured with a 1px border. On focus, the border shifts to Primary Orange with a soft 2px glow.
- Labels must always be visible (Inter, 14px, Semi-bold) to ensure users never lose context in complex forms.

### Chips & Tags
- Used for part categories or stock status (e.g., "In Stock" in Teal, "Out of Stock" in Heritage Red). 
- Semi-transparent backgrounds with high-contrast text for a refined, modern look.

### Data Tables
- Critical for an automotive distributor. Use zebra-striping with the Neutral background color.
- Headers should be Deep Charcoal with white Montserrat labels for clear hierarchy.