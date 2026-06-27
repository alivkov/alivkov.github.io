# Email Template Redesign — Design Spec
**Date:** 2026-06-06
**Project:** VNN Engineering / EMS Periodic Maintenance Email (Периодична Профилактика)

## Overview

Redesign the existing HTML email template (`code.html`) to be more modern and professional, using a **Bold Editorial** visual direction with device image placeholders.

## Design Direction: Bold Editorial

- Full-width deep green gradient hero banner dominates the first impression
- 900-weight uppercase typography with mint green accent on headline
- Left-border accent cards replace icon-centered benefit cards
- Dark green footer (deeper than current)
- Two image placeholders: full device shot (hero) and close-up detail shot (alongside benefits)
- The existing color palette (forest green `#075227`, dark green `#063d1e`, mint `#91d69e`) is preserved

## Section-by-Section Spec

### 1. Header
- White background, 1px bottom border (`#e5e7eb`)
- Left: "VNN Engineering" in 900-weight green (`#075227`), "Official Service Partner" in 9px uppercase gray below
- Right: EMS+ badge — light green tinted pill (`background: #f0faf4`, `border: 1px solid #a3e9af`) with ⚕ icon and bold green "EMS+" text

### 2. Hero
- Background: `linear-gradient(135deg, #063d1e 0%, #075227 40%, #286b3d 75%, #3a8a55 100%)`
- Two subtle decorative circles (rgba overlays) for depth — not interactive
- Eyebrow text: "VNN Engineering · Официален сервизен партньор" in 10px mint green (`#91d69e`), letter-spacing 0.18em
- Headline: "ПЕРИОДИЧНА ПРОФИЛАК" in white + "ТИКА" in mint `#91d69e`, 38px 900-weight, letter-spacing -0.03em
- Tagline: "За надеждна работа. Дълъг живот. Спокойствие." in white 75% opacity, 13px
- Right column: **Image placeholder** — dashed border (`rgba(145,214,158,0.4)`), dark glass background, labeled "Device image / Airflow ONE". Aspect ratio 3:4.

### 3. Stats Bar
- Background: `#063d1e` (darkest green)
- Layout: stat block "12 / месеца" — italic "или" separator (white 35% opacity) — stat block "2000 / работни часа"
- Numbers: 36px 900-weight mint (`#91d69e`), labels in 9px uppercase white 50% opacity

### 4. Intro Text
- White background, 24px padding
- Section label: "Уважаеми колеги" in 10px uppercase green, letter-spacing 0.18em
- Body: 15px, `#1f2937`, line-height 1.65. The phrase "надеждна работа" bolded in green.

### 5. Technical Description
- Tinted background (`#f8faf9`)
- Left-border card: 4px solid `#286b3d` left border, rounded right corners
- Dark green circle icon enclosure with ⚙ icon
- 13px body text, `#374151`, line-height 1.6

### 6. Benefits + Detail Image
- White background, section label: "Редовната профилактика помага за:"
- **Left:** 2×2 grid of benefit cards. Each card: left 3px border `#286b3d`, 1px border other sides (`#e5e7eb`), rounded right corners. Contains an emoji icon, bold green title (11px), gray subtitle (10px).
  - Card 1: 🛡 По-дълъг експлоатационен живот / на апарата
  - Card 2: ⚡ Намаляване на неочаквани прекъсвания / в работата
  - Card 3: 📈 По-висока ефективност / и производителност
  - Card 4: 💰 Предотвратяване на скъпи ремонти / и изненади
- **Right:** **Image placeholder** — gray dashed border, aspect ratio 2:3, labeled "Close-up detail shot"

### 7. CTA
- White background, 1px top border
- Full-width dark green button (`#075227`), white 800-weight text, "✉ Свържете се с нас", 8px border-radius
- Below: 12px gray note about individual quotes per model/configuration

### 8. Footer
- Background: `#063d1e`
- Top row: "VNN Engineering EOOD" (white 900-weight) + "Official EMS Dental Service Partner" (mint 9px uppercase) on left; "EMS+" badge (mint border, mint text) on right. Separated from contacts by 1px rgba border.
- Contacts grid (2 columns): email, website, phone, address — 12px white 75% opacity
- Copyright: 10px white 35% opacity, centered

## Image Placeholders

Two placeholders to be replaced with real images later:

| Location | Aspect Ratio | Label | Style |
|---|---|---|---|
| Hero (right column) | 3:4 (portrait) | "Device image / Airflow ONE" | Dark glass + dashed mint border |
| Benefits (right column) | 2:3 (portrait) | "Close-up detail shot" | Light gray + dashed gray border |

## Content Fixes

- Benefit 3 placeholder text ("Беддствие действитедеде...") replaced with: "По-висока ефективност / и производителност"

## Technical Notes

- Template is a single `code.html` file using Tailwind CSS CDN + Inter from Google Fonts
- Max-width: 600px (standard email width)
- The redesign uses embedded `<style>` CSS (as seen in the mockup), replacing Tailwind utility classes. This matches the approved mockup and avoids reliance on a CDN at render time.
- Material Symbols icon font can be replaced with emoji for the benefit cards (simpler, more compatible)
- No JavaScript needed for the email itself (the existing micro-interaction script is browser-only and can be kept or removed)
