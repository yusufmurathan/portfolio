---
name: Achromatic Precision
colors:
  surface: '#131313'
  surface-dim: '#131313'
  surface-bright: '#393939'
  surface-container-lowest: '#0e0e0e'
  surface-container-low: '#1b1b1b'
  surface-container: '#1f1f1f'
  surface-container-high: '#2a2a2a'
  surface-container-highest: '#353535'
  on-surface: '#e2e2e2'
  on-surface-variant: '#c4c7c8'
  inverse-surface: '#e2e2e2'
  inverse-on-surface: '#303030'
  outline: '#8e9192'
  outline-variant: '#444748'
  surface-tint: '#c6c6c7'
  primary: '#ffffff'
  on-primary: '#2f3131'
  primary-container: '#e2e2e2'
  on-primary-container: '#636565'
  inverse-primary: '#5d5f5f'
  secondary: '#c8c6c5'
  on-secondary: '#313030'
  secondary-container: '#474746'
  on-secondary-container: '#b7b5b4'
  tertiary: '#ffffff'
  on-tertiary: '#002e6a'
  tertiary-container: '#d8e2ff'
  on-tertiary-container: '#0060ce'
  error: '#ffb4ab'
  on-error: '#690005'
  error-container: '#93000a'
  on-error-container: '#ffdad6'
  primary-fixed: '#e2e2e2'
  primary-fixed-dim: '#c6c6c7'
  on-primary-fixed: '#1a1c1c'
  on-primary-fixed-variant: '#454747'
  secondary-fixed: '#e5e2e1'
  secondary-fixed-dim: '#c8c6c5'
  on-secondary-fixed: '#1c1b1b'
  on-secondary-fixed-variant: '#474746'
  tertiary-fixed: '#d8e2ff'
  tertiary-fixed-dim: '#adc6ff'
  on-tertiary-fixed: '#001a42'
  on-tertiary-fixed-variant: '#004395'
  background: '#131313'
  on-background: '#e2e2e2'
  surface-variant: '#353535'
typography:
  display-lg:
    fontFamily: Inter
    fontSize: 48px
    fontWeight: '600'
    lineHeight: 56px
    letterSpacing: -0.02em
  headline-lg:
    fontFamily: Inter
    fontSize: 32px
    fontWeight: '600'
    lineHeight: 40px
    letterSpacing: -0.01em
  headline-lg-mobile:
    fontFamily: Inter
    fontSize: 28px
    fontWeight: '600'
    lineHeight: 36px
    letterSpacing: -0.01em
  headline-md:
    fontFamily: Inter
    fontSize: 24px
    fontWeight: '500'
    lineHeight: 32px
    letterSpacing: -0.01em
  body-lg:
    fontFamily: Inter
    fontSize: 18px
    fontWeight: '400'
    lineHeight: 28px
    letterSpacing: '0'
  body-md:
    fontFamily: Inter
    fontSize: 16px
    fontWeight: '400'
    lineHeight: 24px
    letterSpacing: '0'
  label-sm:
    fontFamily: Inter
    fontSize: 12px
    fontWeight: '600'
    lineHeight: 16px
    letterSpacing: 0.05em
spacing:
  unit: 4px
  gutter: 24px
  margin-mobile: 16px
  margin-desktop: 64px
  container-max: 1280px
---

## Brand & Style
This design system embodies a premium, high-end corporate aesthetic characterized by absolute precision and structural clarity. The visual language is inspired by the intersection of high-fidelity engineering and minimalist luxury, evoking a sense of "digital craftsmanship."

The brand personality is authoritative yet understated. It targets a professional audience that values efficiency, clarity, and sophistication. By utilizing an AMOLED black foundation with zero-radius geometry, the UI achieves a "monolithic" feel—as if the interface is etched directly into the glass of the device. The emotional response is one of calm focus, reliability, and modern elegance.

The design style is **Minimalist-Industrial**:
- **Pure AMOLED Black:** High-contrast foundations for infinite depth.
- **Sharp Geometry:** No rounded corners; every element is defined by 90-degree precision.
- **Architectural Whitespace:** Generous, intentional negative space to define hierarchy.
- **Refined Accents:** Minimal use of color, reserved only for critical interactions.

## Colors
The palette is strictly curated to maintain high contrast and a premium executive feel. 

- **Foundation:** The background is #000000 (Pure Black). This creates a seamless transition with hardware bezels and provides maximum contrast for legibility.
- **Accents:** A subtle slate blue (#3B82F6) is used sparingly for active states, primary actions, or focus indicators.
- **Neutral/Borders:** We use #1A1A1A for structural lines and dividers. These borders should be barely perceptible, serving as a guide rather than a barrier.
- **Typography:** Headings utilize #FFFFFF for maximum punch. Body text uses #A1A1AA to reduce eye strain and establish a clear information hierarchy.

## Typography
The system relies on **Inter**, a typeface designed for screens, providing exceptional legibility and a neutral, professional tone. 

- **Headlines:** Use tight letter-spacing and semi-bold weights to create a "locked-in" editorial look.
- **Body:** Standardized at 16px for optimal readability with a generous 1.5x line height.
- **Labels:** Small caps or uppercase with increased tracking (0.05em) should be used for metadata and eyebrow text to differentiate from body copy.
- **Scaling:** On mobile devices, display and headline sizes should scale down by approximately 15% to maintain visual balance within tighter margins.

## Layout & Spacing
The layout follows a **Fixed Grid** philosophy for desktop and a **Fluid** approach for mobile. 

- **Grid:** Use a 12-column grid for desktop. Columns are separated by 24px gutters. Content should be centered within a maximum container width of 1280px.
- **Rhythm:** All spacing (padding, margins) must be increments of 4px. Use larger gaps (48px, 64px, or 80px) between major sections to emphasize the "Apple-like" use of whitespace.
- **Alignment:** Strict adherence to the baseline grid is required. Every element must feel mathematically placed. Avoid "optical" centering if it breaks the grid's vertical rhythm.

## Elevation & Depth
In an AMOLED environment, traditional shadows are discarded in favor of **Tonal Layering** and **Low-Contrast Outlines**.

- **Surfaces:** Use #000000 for the primary background. Elevated elements (like cards or menus) should not use shadows; instead, they are defined by a 1px border of #1A1A1A or a very slightly lighter fill (#0A0A0A) if necessary.
- **Depth:** Higher hierarchy is represented by brightness rather than physical shadow. A "closer" element might have a slightly brighter border or more vibrant white text.
- **Glassmorphism:** Reserved strictly for overlays (like navigation bars). Use a high-density background blur (30px+) with a 10% white tint to create a sophisticated "frosted obsidian" effect.

## Shapes
The shape language is strictly **Sharp (0px)**. 

Every UI component—from primary buttons to form fields and container cards—must use square corners. This reinforces the architectural and technical nature of the system. The only exception to the "roundness rule" is for elements that are intrinsically circular, such as avatars or radio button indicators, though even these should be evaluated for square alternatives where possible.

## Components
Consistent execution of these components is vital for the "monolithic" aesthetic.

- **Buttons:** Primary buttons are solid #FFFFFF with #000000 text. Secondary buttons are outlined in #1A1A1A with #FFFFFF text. All have 0px radius.
- **Input Fields:** Minimalist design with a bottom border only (#1A1A1A). On focus, the border transitions to #FFFFFF or the accent Blue. Labels should be small and uppercase.
- **Cards:** Defined by a 1px border of #1A1A1A. No fill (keep #000000) to maintain the "black-out" look. 
- **Lists:** Items are separated by thin 1px dividers (#1A1A1A). Hover states should be a subtle shift to #0A0A0A.
- **Selection Controls:** Checkboxes and Radio buttons must be square. Active states use the primary accent blue for clear feedback.
- **Navigation:** Top-level navigation should be persistent, utilizing the frosted obsidian glass effect mentioned in Elevation.