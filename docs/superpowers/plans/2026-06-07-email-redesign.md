# Email Template Redesign Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Redesign `code.html` into a Bold Editorial email template with a deep green gradient hero, left-border accent cards, two image placeholders, and a refined dark footer.

**Architecture:** Single `code.html` file — the existing Tailwind CDN + Material Symbols setup is replaced with embedded `<style>` CSS and Inter from Google Fonts. Each section of the email is a self-contained `<div>` inside a 600px-wide wrapper. No JavaScript is required.

**Tech Stack:** HTML5, embedded CSS (no framework), Inter (Google Fonts)

---

## File Map

| Action | File | Responsibility |
|---|---|---|
| Overwrite | `code.html` | The entire email template |

The plan rewrites `code.html` top-to-bottom across 5 tasks. Each task appends one or more sections. Start from a blank file in Task 1 and grow it to completion.

---

### Task 1: Base structure, CSS foundation, and Header

**Files:**
- Overwrite: `code.html`

- [ ] **Step 1: Replace `code.html` with the new skeleton + header**

Overwrite `code.html` entirely with the following. This establishes the `<head>`, all embedded CSS, and the header section. The `<!-- CONTENT -->` comment is a placeholder for subsequent tasks.

```html
<!DOCTYPE html>
<html lang="bg">
<head>
<meta charset="utf-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>VNN Engineering - Периодична Профилактика</title>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800;900&display=swap" rel="stylesheet"/>
<style>
  * { box-sizing: border-box; margin: 0; padding: 0; }

  body {
    background: #e8edf0;
    font-family: 'Inter', sans-serif;
    padding: 24px 8px;
  }

  .email-wrap {
    width: 100%;
    max-width: 600px;
    margin: 0 auto;
    background: #fff;
    border-radius: 8px;
    overflow: hidden;
    box-shadow: 0 4px 24px rgba(0,0,0,0.12), 0 1px 4px rgba(0,0,0,0.08);
  }

  /* ── HEADER ── */
  .email-header {
    background: #fff;
    padding: 14px 24px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    border-bottom: 1px solid #e5e7eb;
  }
  .header-brand {
    font-size: 18px;
    font-weight: 900;
    color: #075227;
    letter-spacing: -0.02em;
  }
  .header-sub {
    font-size: 9px;
    font-weight: 600;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    color: #9ca3af;
    margin-top: 3px;
  }
  .header-badge {
    display: flex;
    align-items: center;
    gap: 6px;
    background: #f0faf4;
    border: 1px solid #a3e9af;
    border-radius: 6px;
    padding: 6px 12px;
  }
  .badge-icon { font-size: 16px; }
  .badge-text {
    font-size: 13px;
    font-weight: 800;
    color: #075227;
    letter-spacing: 0.05em;
  }
  .badge-sup {
    font-size: 8px;
    color: #ba1a1a;
    font-weight: 700;
    vertical-align: super;
  }

  /* ── HERO ── */
  .email-hero {
    background: linear-gradient(135deg, #063d1e 0%, #075227 40%, #286b3d 75%, #3a8a55 100%);
    padding: 32px 24px 28px;
    position: relative;
    overflow: hidden;
  }
  .hero-circle-1 {
    position: absolute;
    right: -60px; top: -60px;
    width: 240px; height: 240px;
    border-radius: 50%;
    background: rgba(255,255,255,0.04);
    pointer-events: none;
  }
  .hero-circle-2 {
    position: absolute;
    left: -40px; bottom: -80px;
    width: 200px; height: 200px;
    border-radius: 50%;
    background: rgba(145,214,158,0.06);
    pointer-events: none;
  }
  .hero-eyebrow {
    font-size: 10px;
    font-weight: 600;
    letter-spacing: 0.18em;
    text-transform: uppercase;
    color: #91d69e;
    margin-bottom: 14px;
    position: relative;
    z-index: 1;
  }
  .hero-content {
    display: flex;
    gap: 20px;
    align-items: center;
    position: relative;
    z-index: 1;
  }
  .hero-text { flex: 1.1; }
  .hero-headline {
    font-size: 38px;
    font-weight: 900;
    line-height: 0.95;
    letter-spacing: -0.03em;
    text-transform: uppercase;
    color: #fff;
    margin-bottom: 14px;
  }
  .hero-headline-accent { color: #91d69e; }
  .hero-tagline {
    font-size: 13px;
    color: rgba(255,255,255,0.75);
    line-height: 1.55;
  }
  .hero-image-col {
    flex: 0.9;
    display: flex;
    justify-content: center;
  }
  .img-placeholder-hero {
    width: 100%;
    max-width: 190px;
    aspect-ratio: 3 / 4;
    background: rgba(255,255,255,0.07);
    border: 2px dashed rgba(145,214,158,0.4);
    border-radius: 12px;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    gap: 10px;
    color: rgba(145,214,158,0.7);
    font-size: 10px;
    font-weight: 600;
    letter-spacing: 0.05em;
    text-align: center;
    line-height: 1.5;
  }
  .placeholder-icon {
    font-size: 28px;
    opacity: 0.6;
  }

  /* ── STATS BAR ── */
  .stats-bar {
    background: #063d1e;
    padding: 18px 24px;
    display: flex;
    align-items: center;
    justify-content: center;
  }
  .stat-block {
    flex: 1;
    text-align: center;
    padding: 0 16px;
  }
  .stat-number {
    font-size: 36px;
    font-weight: 900;
    color: #91d69e;
    line-height: 1;
    letter-spacing: -0.03em;
  }
  .stat-unit {
    font-size: 9px;
    font-weight: 700;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    color: rgba(255,255,255,0.5);
    margin-top: 5px;
  }
  .stat-or {
    font-size: 11px;
    font-style: italic;
    color: rgba(255,255,255,0.35);
    padding: 0 8px;
  }

  /* ── INTRO TEXT ── */
  .section-white { background: #fff; padding: 24px; }
  .section-tinted { background: #f8faf9; padding: 24px; }
  .section-label {
    font-size: 10px;
    font-weight: 700;
    letter-spacing: 0.18em;
    text-transform: uppercase;
    color: #286b3d;
    margin-bottom: 14px;
  }
  .intro-text {
    font-size: 15px;
    color: #1f2937;
    line-height: 1.65;
  }
  .intro-text strong { color: #075227; }

  /* ── TECH DESCRIPTION ── */
  .tech-card {
    background: #fff;
    border-left: 4px solid #286b3d;
    border-radius: 0 8px 8px 0;
    padding: 16px 18px;
    display: flex;
    gap: 14px;
    align-items: flex-start;
  }
  .tech-icon-wrap {
    width: 36px;
    height: 36px;
    min-width: 36px;
    background: #075227;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 16px;
  }
  .tech-text {
    font-size: 13px;
    color: #374151;
    line-height: 1.6;
  }

  /* ── BENEFITS + DETAIL IMAGE ── */
  .benefits-layout {
    display: flex;
    gap: 16px;
    align-items: flex-start;
  }
  .benefits-grid {
    flex: 1.2;
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 8px;
  }
  .benefit-card {
    background: #fff;
    border-left: 3px solid #286b3d;
    border-top: 1px solid #e5e7eb;
    border-right: 1px solid #e5e7eb;
    border-bottom: 1px solid #e5e7eb;
    border-radius: 0 6px 6px 0;
    padding: 12px 14px;
  }
  .benefit-icon {
    font-size: 18px;
    margin-bottom: 6px;
    display: block;
  }
  .benefit-title {
    font-size: 11px;
    font-weight: 700;
    color: #075227;
    line-height: 1.3;
  }
  .benefit-sub {
    font-size: 10px;
    color: #6b7280;
    margin-top: 3px;
    line-height: 1.4;
  }
  .detail-image-col { flex: 0.8; }
  .img-placeholder-detail {
    width: 100%;
    aspect-ratio: 2 / 3;
    background: #f3f4f6;
    border: 2px dashed #d1d5db;
    border-radius: 10px;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    gap: 10px;
    color: #9ca3af;
    font-size: 9px;
    font-weight: 600;
    letter-spacing: 0.04em;
    text-align: center;
    line-height: 1.5;
  }

  /* ── CTA ── */
  .cta-section {
    background: #fff;
    padding: 24px;
    text-align: center;
    border-top: 1px solid #e5e7eb;
  }
  .cta-button {
    display: block;
    width: 100%;
    background: #075227;
    color: #fff;
    font-size: 16px;
    font-weight: 800;
    letter-spacing: 0.01em;
    padding: 16px 24px;
    border-radius: 8px;
    text-decoration: none;
    margin-bottom: 14px;
  }
  .cta-note {
    font-size: 12px;
    color: #6b7280;
    line-height: 1.55;
  }

  /* ── FOOTER ── */
  .email-footer {
    background: #063d1e;
    padding: 24px;
    color: #fff;
  }
  .footer-top {
    display: flex;
    justify-content: space-between;
    align-items: flex-start;
    margin-bottom: 16px;
    padding-bottom: 16px;
    border-bottom: 1px solid rgba(255,255,255,0.1);
  }
  .footer-brand {
    font-size: 16px;
    font-weight: 900;
    color: #fff;
    letter-spacing: -0.01em;
  }
  .footer-partner {
    font-size: 9px;
    font-weight: 600;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    color: #91d69e;
    margin-top: 4px;
  }
  .footer-badge {
    font-size: 10px;
    font-weight: 700;
    color: #91d69e;
    letter-spacing: 0.05em;
    border: 1px solid rgba(145,214,158,0.3);
    padding: 5px 12px;
    border-radius: 4px;
    align-self: center;
  }
  .footer-contacts {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 10px;
    margin-bottom: 16px;
  }
  .footer-link {
    display: flex;
    align-items: center;
    gap: 7px;
    font-size: 12px;
    color: rgba(255,255,255,0.75);
    text-decoration: none;
  }
  .footer-address {
    display: flex;
    align-items: flex-start;
    gap: 7px;
    font-size: 12px;
    color: rgba(255,255,255,0.75);
    line-height: 1.5;
  }
  .footer-copy {
    font-size: 10px;
    color: rgba(255,255,255,0.35);
    text-align: center;
    letter-spacing: 0.04em;
    padding-top: 14px;
    border-top: 1px solid rgba(255,255,255,0.08);
  }
</style>
</head>
<body>
<div class="email-wrap">

  <!-- HEADER -->
  <div class="email-header">
    <div>
      <div class="header-brand">VNN Engineering</div>
      <div class="header-sub">Official Service Partner</div>
    </div>
    <div class="header-badge">
      <span class="badge-icon">⚕</span>
      <span class="badge-text">EMS<span class="badge-sup">+</span></span>
    </div>
  </div>

  <!-- CONTENT -->

</div>
</body>
</html>
```

- [ ] **Step 2: Open `code.html` in a browser and verify the header**

Expected: White bar with "VNN Engineering" in dark green on the left, "EMS+" green badge on the right, 1px gray bottom border. Body background is `#e8edf0`. The card has rounded corners and a soft shadow.

- [ ] **Step 3: Commit**

```bash
git add code.html
git commit -m "feat: new email template — base CSS and header"
```

---

### Task 2: Hero section and Stats bar

**Files:**
- Modify: `code.html` — replace `<!-- CONTENT -->` with hero + stats, then add new `<!-- CONTENT -->` below

- [ ] **Step 1: Replace `<!-- CONTENT -->` with the hero and stats HTML**

In `code.html`, replace the line `  <!-- CONTENT -->` with:

```html
  <!-- HERO -->
  <div class="email-hero">
    <div class="hero-circle-1"></div>
    <div class="hero-circle-2"></div>
    <div class="hero-eyebrow">VNN Engineering · Официален сервизен партньор</div>
    <div class="hero-content">
      <div class="hero-text">
        <div class="hero-headline">
          ПЕРИОДИЧНА<br/>ПРОФИЛАК<span class="hero-headline-accent">ТИКА</span>
        </div>
        <div class="hero-tagline">За надеждна работа.<br/>Дълъг живот. Спокойствие.</div>
      </div>
      <div class="hero-image-col">
        <div class="img-placeholder-hero">
          <span class="placeholder-icon">🖼</span>
          Device image<br/>Airflow ONE
        </div>
      </div>
    </div>
  </div>

  <!-- STATS BAR -->
  <div class="stats-bar">
    <div class="stat-block">
      <div class="stat-number">12</div>
      <div class="stat-unit">месеца</div>
    </div>
    <span class="stat-or">или</span>
    <div class="stat-block">
      <div class="stat-number">2000</div>
      <div class="stat-unit">работни часа</div>
    </div>
  </div>

  <!-- CONTENT -->
```

- [ ] **Step 2: Open `code.html` in a browser and verify hero + stats**

Expected:
- Green gradient hero (`#063d1e` → `#3a8a55`) with two faint decorative circles
- "ПЕРИОДИЧНА ПРОФИЛАК" in white + "ТИКА" in mint `#91d69e`, 38px heavy weight
- Dashed mint-bordered portrait placeholder on the right
- Dark `#063d1e` stats bar below with "12 / МЕСЕЦА" and "2000 / РАБОТНИ ЧАСА" in large mint numerals, "или" between them

- [ ] **Step 3: Commit**

```bash
git add code.html
git commit -m "feat: add hero section and stats bar"
```

---

### Task 3: Intro text and Technical description

**Files:**
- Modify: `code.html` — replace `<!-- CONTENT -->` with intro + tech sections, add new `<!-- CONTENT -->` below

- [ ] **Step 1: Replace `<!-- CONTENT -->` with intro and tech description HTML**

```html
  <!-- INTRO TEXT -->
  <div class="section-white">
    <div class="section-label">Уважаеми колеги</div>
    <p class="intro-text">
      С цел гарантиране на <strong>надеждна работа</strong>, оптимална ефективност и минимизиране на риска от технически проблеми с вашата EMS GBT Machine, препоръчваме извършването на периодична профилактика на всеки 12 месеца или 2000 работни часа (което настъпи първо).
    </p>
  </div>

  <!-- TECH DESCRIPTION -->
  <div class="section-tinted">
    <div class="tech-card">
      <div class="tech-icon-wrap">⚙</div>
      <p class="tech-text">
        Профилактиката включва проверка на основните функционални модули и подмяна на определени компоненти от сервизните комплекти за съответния модел апарат. Тези компоненти са определени от EMS като консумативи с повишен риск от износване.
      </p>
    </div>
  </div>

  <!-- CONTENT -->
```

- [ ] **Step 2: Open `code.html` in a browser and verify intro + tech**

Expected:
- White section with "УВАЖАЕМИ КОЛЕГИ" in 10px green uppercase label, body text at 15px with "надеждна работа" bolded in green
- Tinted `#f8faf9` section with a card: 4px green left border, dark green circular icon on the left, 13px gray body text on the right

- [ ] **Step 3: Commit**

```bash
git add code.html
git commit -m "feat: add intro text and tech description sections"
```

---

### Task 4: Benefits grid and detail image placeholder

**Files:**
- Modify: `code.html` — replace `<!-- CONTENT -->` with benefits section, add new `<!-- CONTENT -->` below

- [ ] **Step 1: Replace `<!-- CONTENT -->` with benefits + detail image HTML**

```html
  <!-- BENEFITS + DETAIL IMAGE -->
  <div class="section-white">
    <div class="section-label">Редовната профилактика помага за:</div>
    <div class="benefits-layout">
      <div class="benefits-grid">
        <div class="benefit-card">
          <span class="benefit-icon">🛡</span>
          <div class="benefit-title">По-дълъг експлоатационен живот</div>
          <div class="benefit-sub">на апарата</div>
        </div>
        <div class="benefit-card">
          <span class="benefit-icon">⚡</span>
          <div class="benefit-title">Намаляване на неочаквани прекъсвания</div>
          <div class="benefit-sub">в работата</div>
        </div>
        <div class="benefit-card">
          <span class="benefit-icon">📈</span>
          <div class="benefit-title">По-висока ефективност</div>
          <div class="benefit-sub">и производителност</div>
        </div>
        <div class="benefit-card">
          <span class="benefit-icon">💰</span>
          <div class="benefit-title">Предотвратяване на скъпи ремонти</div>
          <div class="benefit-sub">и изненади</div>
        </div>
      </div>
      <div class="detail-image-col">
        <div class="img-placeholder-detail">
          <span class="placeholder-icon" style="font-size:24px; opacity:0.5;">🖼</span>
          Close-up<br/>detail shot
        </div>
      </div>
    </div>
  </div>

  <!-- CONTENT -->
```

- [ ] **Step 2: Open `code.html` in a browser and verify benefits section**

Expected:
- White section with "РЕДОВНАТА ПРОФИЛАКТИКА ПОМАГА ЗА:" label in green
- 2×2 grid of cards on the left: each has a 3px green left border, emoji icon, bold green title, small gray subtitle
- Portrait dashed-border placeholder on the right labeled "Close-up detail shot"

- [ ] **Step 3: Commit**

```bash
git add code.html
git commit -m "feat: add benefits grid and detail image placeholder"
```

---

### Task 5: CTA section, Footer, and final cleanup

**Files:**
- Modify: `code.html` — replace final `<!-- CONTENT -->` with CTA + footer (no more `<!-- CONTENT -->` after this)

- [ ] **Step 1: Replace the final `<!-- CONTENT -->` with CTA and footer HTML**

```html
  <!-- CTA -->
  <div class="cta-section">
    <a class="cta-button" href="mailto:info@vnndental.com">✉ Свържете се с нас</a>
    <p class="cta-note">Нашите инженери ще изготвят индивидуална оферта за всеки клиент в зависимост от модела и конфигурацията на апаратите.</p>
  </div>

  <!-- FOOTER -->
  <div class="email-footer">
    <div class="footer-top">
      <div>
        <div class="footer-brand">VNN Engineering EOOD</div>
        <div class="footer-partner">Official EMS Dental Service Partner</div>
      </div>
      <div class="footer-badge">EMS+</div>
    </div>
    <div class="footer-contacts">
      <a class="footer-link" href="mailto:info@vnndental.com">@ info@vnndental.com</a>
      <div class="footer-address">📍 <span>гр. Пазарджик,<br/>ул. Найчо Цанов 16</span></div>
      <a class="footer-link" href="https://vnndental.com">🌐 vnndental.com</a>
      <a class="footer-link" href="tel:0883484101">📞 0883484101</a>
    </div>
    <div class="footer-copy">© 2024 VNN Engineering EOOD — Official EMS Dental Service Partner</div>
  </div>
```

- [ ] **Step 2: Open `code.html` in a browser and do a full top-to-bottom visual check**

Go through each section and confirm:
- Header: white bar, green brand name, EMS+ badge
- Hero: green gradient, large headline with mint accent, eyebrow text, device image placeholder
- Stats bar: dark green, "12 / МЕСЕЦА" and "2000 / РАБОТНИ ЧАСА" in large mint numerals
- Intro: green label, body text with bolded phrase
- Tech description: tinted background, left-bordered card with icon
- Benefits: 2×2 left-border cards with emoji icons, detail image placeholder on the right
- CTA: full-width green button linking to `mailto:info@vnndental.com`, gray note below
- Footer: darkest green background, brand + partner label, EMS+ badge, 2-column contact grid, copyright

- [ ] **Step 3: Commit**

```bash
git add code.html
git commit -m "feat: add CTA and footer — email redesign complete"
```
