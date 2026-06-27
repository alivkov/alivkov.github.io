---
name: Clinical Engineering System
colors:
  surface: '#f8f9ff'
  surface-dim: '#cbdbf5'
  surface-bright: '#f8f9ff'
  surface-container-lowest: '#ffffff'
  surface-container-low: '#eff4ff'
  surface-container: '#e5eeff'
  surface-container-high: '#dce9ff'
  surface-container-highest: '#d3e4fe'
  on-surface: '#0b1c30'
  on-surface-variant: '#404940'
  inverse-surface: '#213145'
  inverse-on-surface: '#eaf1ff'
  outline: '#707a70'
  outline-variant: '#c0c9be'
  surface-tint: '#286b3d'
  primary: '#075227'
  on-primary: '#ffffff'
  primary-container: '#286b3d'
  on-primary-container: '#a3e9af'
  inverse-primary: '#91d69e'
  secondary: '#5b5f5e'
  on-secondary: '#ffffff'
  secondary-container: '#dde0de'
  on-secondary-container: '#5f6362'
  tertiary: '#474646'
  on-tertiary: '#ffffff'
  tertiary-container: '#5f5e5e'
  on-tertiary-container: '#dbd8d7'
  error: '#ba1a1a'
  on-error: '#ffffff'
  error-container: '#ffdad6'
  on-error-container: '#93000a'
  primary-fixed: '#acf3b8'
  primary-fixed-dim: '#91d69e'
  on-primary-fixed: '#00210b'
  on-primary-fixed-variant: '#065227'
  secondary-fixed: '#e0e3e1'
  secondary-fixed-dim: '#c4c7c5'
  on-secondary-fixed: '#181c1b'
  on-secondary-fixed-variant: '#434846'
  tertiary-fixed: '#e5e2e1'
  tertiary-fixed-dim: '#c8c6c5'
  on-tertiary-fixed: '#1c1b1b'
  on-tertiary-fixed-variant: '#474746'
  background: '#f8f9ff'
  on-background: '#0b1c30'
  surface-variant: '#d3e4fe'
typography:
  headline-xl:
    fontFamily: Inter
    fontSize: 48px
    fontWeight: '700'
    lineHeight: '1.1'
    letterSpacing: -0.02em
  headline-lg:
    fontFamily: Inter
    fontSize: 32px
    fontWeight: '700'
    lineHeight: '1.2'
    letterSpacing: -0.01em
  headline-lg-mobile:
    fontFamily: Inter
    fontSize: 24px
    fontWeight: '700'
    lineHeight: '1.2'
  title-md:
    fontFamily: Inter
    fontSize: 20px
    fontWeight: '600'
    lineHeight: '1.4'
  body-base:
    fontFamily: Inter
    fontSize: 16px
    fontWeight: '400'
    lineHeight: '1.6'
  body-sm:
    fontFamily: Inter
    fontSize: 14px
    fontWeight: '400'
    lineHeight: '1.5'
  label-caps:
    fontFamily: Inter
    fontSize: 12px
    fontWeight: '600'
    lineHeight: '1'
    letterSpacing: 0.05em
rounded:
  sm: 0.125rem
  DEFAULT: 0.25rem
  md: 0.375rem
  lg: 0.5rem
  xl: 0.75rem
  full: 9999px
spacing:
  base: 8px
  xs: 4px
  sm: 12px
  md: 24px
  lg: 48px
  xl: 80px
  gutter: 24px
  margin: 32px
---

## Brand & Style

This design system is built on the pillars of **precision, reliability, and clinical excellence**. It is tailored for B2B medical engineering communications where clarity of information is paramount. The visual language balances high-tech engineering with the sterile, trustworthy environment of modern healthcare.

The design style follows a **Modern Corporate** aesthetic with a strong emphasis on **Minimalism**. It utilizes generous white space to reduce cognitive load and compartmentalized data modules to convey complex technical information efficiently. The mood is professional and authoritative, ensuring that technicians and medical buyers feel a sense of security and systematic order.

## Colors

The palette is anchored by a deep **Forest Green**, symbolizing growth, health, and operational safety. This is paired with a vast amount of **Clinical White** to maintain a sterile and professional atmosphere. 

- **Primary Green:** Used for headers, primary actions, and success-state iconography.
- **Secondary Mint Tint:** A very light desaturated green used for background sections and subtle grouping containers.
- **Surface Neutrals:** High-contrast blacks are reserved for typography to ensure maximum legibility, while mid-tone slates are used for secondary technical data and labels.

## Typography

The design system utilizes **Inter** exclusively to leverage its systematic, neutral, and utilitarian characteristics. Its tall x-height and excellent legibility at small sizes make it ideal for technical specifications and medical documentation.

Headlines should be bold and tightly spaced to create a sense of structural strength. Body copy maintains a generous line height (1.6) to facilitate easy reading of long-form service descriptions or technical manuals. Labels and technical meta-data use an uppercase style with increased tracking to differentiate "data" from "narrative" text.

## Layout & Spacing

The layout philosophy relies on a **Fluid Grid** model with a strictly enforced 8px baseline rhythm. This ensures that all components, icons, and text blocks align to a predictable vertical and horizontal cadence.

- **Desktop:** A 12-column grid with 24px gutters. Elements should span 3, 4, 6, or 12 columns to maintain a balanced, symmetrical appearance.
- **Mobile:** A 4-column grid with 16px margins. Content reflows vertically, with complex data tables transitioning into card-based layouts.
- **Padding:** Internal component padding should prioritize the `md` (24px) unit to ensure interfaces feel breathable and professional, rather than cramped.

## Elevation & Depth

To maintain a "medical-grade" aesthetic, this design system avoids heavy shadows and skeuomorphism. Instead, it uses **Tonal Layers** and **Low-Contrast Outlines** to define hierarchy.

Depth is achieved through:
1. **Z-axis Layering:** Using subtle 1px borders in a light grey-green hex (#E2E8F0) to separate content modules.
2. **Surface Hierarchy:** Backgrounds use the Secondary color (#F4F7F5) to sit "behind" white content cards, creating a natural sense of stacking without the need for blurs or shadows.
3. **Interactive Lift:** For buttons or interactive cards, a very subtle, tight ambient shadow (0px 2px 4px, 5% opacity) may be applied on hover to signal interactivity.

## Shapes

The shape language is **Soft (Level 1)**. This choice reflects engineering precision—sharp enough to feel technical and industrial, but slightly softened (4px to 8px) to feel approachable and modern.

- **Standard Components:** Use a 4px radius (e.g., input fields, small buttons).
- **Cards & Containers:** Use an 8px radius (rounded-lg) for main content blocks to provide a distinct, organized frame.
- **Icon Enclosures:** Circular containers are used specifically for iconography to soften the "technical" feel of the line-art.

## Components

### Buttons
Primary buttons are solid Green (#286B3D) with bold white Inter text. Secondary buttons use a Green outline with a transparent background. All buttons have a 4px corner radius.

### Cards
Cards are the primary layout tool. They feature a white background, an 8px corner radius, and a 1px border. They should include a distinct header area, often highlighted with a subtle top-border or a light grey background.

### Technical Icons
Icons must be thin-stroke, linear, and geometric. They are frequently housed in circular containers to act as visual anchors for service features or technical benefits.

### Input Fields
Inputs are minimalist, using a 1px border. When focused, the border transitions to the primary green. Labels are always positioned above the field using the `label-caps` style for maximum clarity.

### Data Lists
Service intervals and technical specs are presented in clean, striped lists or 2-column key-value pairs, separated by light 1px horizontal dividers to ensure readability of data points.