# WEBSITE-SPEC — AutoHaus by Patanayont

**Version:** 1.0 | **Date:** 2026-06-14 | **Status:** Draft — awaiting owner sign-off

> **Rule:** This document must be updated before any code change. Code follows spec.

---

## 1. Problem Statement

The current patanayont.com site (Bootstrap 3, ©2016, 4 static PHP pages) fails to communicate the brand's 60-year authority and premium genuine-parts positioning to three distinct audience types visiting the same URL. It has no language toggle, no dark-mode support, no accessible color contrast, and no clear differentiation between B2B and B2C customer journeys. The site looks dated relative to competitors and creates a trust gap that costs credibility before a prospect even reads the content.

---

## 2. Goals

| # | Goal | Metric |
|---|------|--------|
| G1 | Establish AutoHaus as a premium, trustworthy brand (not just a parts warehouse) | User perception survey after soft-launch: ≥70% rate "น่าเชื่อถือ/professional" |
| G2 | Route each of the 3 audience segments to relevant content within 10 seconds of landing | Scroll-depth + CTA click per segment tracked via GA4 events |
| G3 | Meet WCAG 2.1 AA on all text/interactive elements | 0 critical contrast failures in automated audit (axe, WAVE) |
| G4 | Fully bilingual TH/EN with single-click toggle | Language switch works on all pages, all components |
| G5 | Mobile-first — primary audience accesses via smartphone | LCP < 2.5s on 4G mobile (Lighthouse ≥ 90) |

---

## 3. Non-Goals (v1.0)

| # | Out of Scope | Rationale |
|---|-------------|-----------|
| NG1 | E-commerce / parts ordering / shopping cart | Owner decision 14 Jun 2026: goal is brand & trust, not transactions |
| NG2 | Parts catalog / search | Requires ERP integration — separate project |
| NG3 | Customer login / account portal | No backend infrastructure planned for v1 |
| NG4 | Live inventory or pricing | Backend dependency, deferred to v2 |
| NG5 | CMS / content management back-end | Static files for v1; CMS can be layered on later |

---

## 4. Target Audiences (3 Segments)

| Segment | Thai Label | Who | Primary Need | CTA |
|---------|-----------|-----|-------------|-----|
| **A1 — ร้านอะไหล่ B2B** | ร้านอะไหล่ / ตัวแทนจำหน่าย | Parts shops, wholesalers, sub-distributors | Reliable supply partner, OES quality guarantee, credit terms | "ติดต่อฝ่ายขาย (B2B)" |
| **A2 — อู่ / ฟลีต** | อู่ซ่อม / บริษัทรถยนต์ | Repair workshops, fleet managers, insurance repairers | Fast sourcing, genuine parts for warranty validity | "สั่งอะไหล่สำหรับอู่" |
| **A3 — เจ้าของรถ B2C** | เจ้าของรถ | Individual car owners, enthusiasts | Find nearest dealer, verify part authenticity, price transparency | "ค้นหาร้านอะไหล่ใกล้คุณ" |

The landing page must present a **segment router** above the fold (3 large cards or tabs) so visitors self-select within the first viewport.

---

## 5. Site Architecture

```
/ (Landing Page — single-page scroll with anchor sections)
├── #hero          Hero banner — brand statement + segment router
├── #about         About AutoHaus — 60 years, 3 commitments, ISO
├── #brands        7 Japanese marque logos — genuine parts wall
├── #segments      Deep-dive per audience (tab or accordion)
├── #offices       3 office locations with maps
├── #contact       Contact form + direct contact info
└── #footer        Legal name, copyright, nav links

/contact           Dedicated contact page (mirrors #contact section)
/careers           Job listings (mirrors old jobs.php)
/team              Team page (mirrors old team.php)
```

---

## 6. Page Sections — Landing Page

### 6.1 Navigation (sticky)

| Element | Detail |
|---------|--------|
| Logo | `assets/logoPTY.svg` inline SVG, white version on dark chrome header |
| Nav links | เกี่ยวกับเรา · สินค้า · ลูกค้าของเรา · สาขา · ติดต่อเรา (TH) / About · Products · Customers · Locations · Contact (EN) |
| Language toggle | TH / EN button — saves preference to `localStorage` |
| Theme toggle | Light / Dark / System — uses `prefers-color-scheme` + CSS class override |
| Font-size control | A- A A+ — adjusts `html { font-size }` via CSS custom property |
| Mobile | Hamburger → slide-down drawer, all controls accessible |

Background: dark chrome gradient `#787878 → #404040`, orange border top/bottom per BRAND.md.

---

### 6.2 Hero Section

| Element | Detail |
|---------|--------|
| Full-viewport height | Rotating background images (Ken Burns, 35s cycle) — use existing server assets: `senierteam2.jpg`, `DSC_2037.jpg`, `image_banner5new.jpg`, `image_banner12.jpg` |
| Overlay | Semi-dark scrim `rgba(40,40,40,0.65)` for text legibility |
| Headline | "AutoHaus by Patanayont" — Kanit 700, white, large |
| Sub-headline | "Total Automotive Concept — อะไหล่แท้ ครบ 60 ปี" |
| Segment router | 3 cards (ร้านอะไหล่ / อู่ & ฟลีต / เจ้าของรถ) with distinct CTAs |
| Trust badges | ISO badge + "60 ปี" emblem inline below router |

---

### 6.3 About Section

Content source: BRAND.md §เกี่ยวกับบริษัท and §วิสัยทัศน์ & พันธกิจ

| Block | Content |
|-------|---------|
| Headline | "ความซื่อสัตย์ · 60 ปีของความไว้วางใจ" |
| Company story | 3-sentence company origin paragraph (from BRAND.md §ประวัติ) |
| 3 Commitments | Icon cards: สินค้าคุณภาพสูง · บริการที่ยอดเยี่ยม · นวัตกรรมที่ทันสมัย |
| Vision quote | Pull-quote from BRAND.md §วิสัยทัศน์ |

---

### 6.4 Brands / Genuine Parts Wall

7 manufacturer logo tiles in a responsive grid: **Toyota · Mitsubishi · Mazda · Ford · Honda · Isuzu · Nissan**

Source: `images/genuine_parts_logo/` on server. Must be fetched/copied to local `assets/brands/`.

Headline: "อะไหล่แท้สำหรับรถญี่ปุ่นชั้นนำ 7 แบรนด์"

---

### 6.5 Audience Segment Deep-Dive

3-tab or accordion layout. Each tab = content scoped to one audience.

**A1 — ร้านอะไหล่ (B2B Distributor)**
- Pain: sourcing reliability, OES quality guarantee, volume pricing
- Benefits: nationwide distribution network, ISO-certified stock, 60yr track record
- CTA: "ติดต่อฝ่ายขาย" → tel:02-2248827

**A2 — อู่ & ฟลีต (Workshop / Fleet)**
- Pain: genuine parts for warranty validity, fast turnaround
- Benefits: genuine Genuine Parts, 3 branches in Bangkok for quick pickup
- CTA: "สอบถามราคาอะไหล่" → cs.k@patanayont.com

**A3 — เจ้าของรถ (B2C Owner)**
- Pain: unsure where to get verified genuine parts
- Benefits: trusted 60yr brand, authorized to source directly from manufacturer
- CTA: "หาร้านใกล้คุณ" → anchor to #offices

---

### 6.6 Offices / Locations

3 office cards with embedded Google Maps iframes.

| Office | Address |
|--------|---------|
| สวนมะลิ (HQ) | 23-25 ถ.ยุคล 1 แขวงวัดเทพศิรินทร์ เขตป้อมปราบฯ กทม. 10100 |
| สุขุมวิท 109 | 197/41 หมู่ 1 ซ.สันติบุญ ถ.สุขุมวิท 109 ต.สำโรงเหนือ อ.เมือง จ.สมุทรปราการ 10270 *(จากใบรับรอง ISO 9001 — ยืนยันกับเจ้าของ)* |
| กลการ | (address TBD — needs owner input) |

Phone: 02-2248827-30 · Fax: 0-2225-7691, 0-2225-7692 · Email: cs.k@patanayont.com

---

### 6.7 Contact Section

- Short contact form: ชื่อ / อีเมล / โทรศัพท์ / ข้อความ / [เลือกสาขา dropdown]
- Direct contact block (phone, fax, email with Font Awesome icons)
- LINE QR code placeholder (if available)

---

### 6.8 Footer

- Legal entity: "หจก. พัฒนายนตร์ (Patanayont) © 2024"
- Quick links: เกี่ยวกับเรา · ร่วมงานกับเรา · ติดต่อเรา
- Brand mark: AutoHaus logo (white) on dark chrome
- "Genuine Parts · OES Quality · ISO Certified · 60 ปี"

---

## 7. Requirements

### P0 — Must-Have (MVP cannot ship without these)

| ID | Requirement | Acceptance Criteria |
|----|-------------|---------------------|
| P0-01 | Segment router on hero | 3 distinct CTAs visible on load; each scrolls/navigates to relevant section |
| P0-02 | TH/EN language toggle | All visible text switches language; preference persists across reload via localStorage |
| P0-03 | Dark / Light / System theme | `prefers-color-scheme` respected by default; manual override via toggle; all text meets WCAG AA in both modes |
| P0-04 | Mobile responsive (375px+) | No horizontal scroll; all text readable; CTAs tappable (min 44×44px) |
| P0-05 | WCAG 2.1 AA | 0 critical failures on axe scan; no orange body text on white backgrounds |
| P0-06 | AutoHaus logo (SVG) | `assets/logoPTY.svg` displayed in header; correct version per background (standard on white/dark, knockout on orange) |
| P0-07 | 3 office locations + maps | Each branch has address + Google Maps embed or static map link |
| P0-08 | Contact information | Phone, fax, email visible on contact section and footer |

### P1 — Nice-to-Have (high priority fast follow)

| ID | Requirement |
|----|-------------|
| P1-01 | Font-size A- / A / A+ control (accessibility) |
| P1-02 | Ken Burns hero image carousel (CSS-only, no JS library) |
| P1-03 | Sticky header with scroll-triggered background opacity |
| P1-04 | Smooth scroll + active nav highlight on scroll (scrollspy) |
| P1-05 | Contact form with basic validation (HTML5) |
| P1-06 | 7-brand genuine-parts logo wall (needs brand assets from server) |
| P1-07 | Careers page (porting old jobs.php content) |
| P1-08 | Team page (porting old team.php) |

### P2 — Future Considerations

| ID | Requirement |
|----|-------------|
| P2-01 | Parts inquiry form with vehicle model selector |
| P2-02 | CMS integration (Contentful / Sanity) |
| P2-03 | LINE Official Account integration |
| P2-04 | Google Analytics 4 event tracking per segment CTA |
| P2-05 | Mono-white knockout logo SVG asset (for orange-background use) |
| P2-06 | Meta OG tags + structured data (LocalBusiness JSON-LD) |

---

## 8. Design & Technical Constraints

| Constraint | Detail |
|------------|--------|
| Framework | **React 18 (no-build, via CDN UMD + Babel standalone)** — single `index.html`, runs by opening in browser, no toolchain. Matches owner's preferred no-build workflow. |
| CSS framework | **Tailwind CSS (Play CDN)** with inline config mapping BRAND.md tokens to Tailwind theme (`pty-orange`, `pty-charcoal`, etc.). |
| Visual style | **Glassmorphism over Industrial Heritage** — frosted glass cards (`backdrop-blur`) floating over charcoal gradients & real automotive photography. Brand orange `#f39200` is the single accent that "cuts through" the glass. See §8.1. |
| Fonts | **Montserrat** (display/headings, Latin) + **Kanit** (Thai + Latin headings/body) + **Inter** (Latin body) per DESIGN.md. Kanit is the Thai workhorse. |
| Images | Real server assets fetched to `assets/img/` (hero × 4, partsoto, ISO, 60yr) and `assets/brands/` (7 marque logos). |
| No IE support | Modern browsers only (Chrome 90+, Safari 14+, Firefox 88+) |
| Colors | Must follow BRAND.md palette exactly. No new colors without spec update. |
| Logo | `assets/logoPTY.svg` is canonical. Inline `<img>`, never raster. |

### 8.1 Glassmorphism Style Rules (WCAG-safe)

Glass is decorative chrome, never a substitute for contrast. Enforce:

| Rule | Detail |
|------|--------|
| **Dark glass** (on hero/charcoal) | `bg-white/10` + `backdrop-blur-xl` + `border-white/15`. Text = white/`#f0f0f0` → passes AA on the dark scrim beneath. |
| **Light glass** (on `#f8f8f8` sections) | `bg-white/70` + `backdrop-blur-md` + `border-white/60`. Text = `#333333` → 12.6:1 AAA. |
| **Scrim required** | Any glass over a photo must sit on a `rgba(40,40,40,0.55–0.70)` scrim so text never drops below 4.5:1. |
| **Orange discipline** | `#f39200` only on: CTA fills (with `#1a1a1a` text), large bold headings (24px+), borders, icons. NEVER orange body text on white/glass. |
| **Fallback** | `backdrop-blur` unsupported → glass degrades to solid `--surface` at 92% opacity. Test contrast in fallback too. |
| **Reduced transparency** | Respect `prefers-reduced-transparency` — increase glass opacity to near-solid. |

---

## 9. i18n (Bilingual) Specification

All user-visible strings exist in two versions. Implementation options (pick one before dev starts):

**Option A — `data-i18n` attributes + tiny JS dictionary (recommended for v1)**
```html
<h1 data-i18n="hero.headline">AutoHaus by Patanayont</h1>
```
```js
const i18n = {
  th: { 'hero.headline': 'AutoHaus by Patanayont' },
  en: { 'hero.headline': 'AutoHaus by Patanayont' }
}
```

**Option B — Duplicate HTML blocks** with `lang="th"` / `lang="en"` hidden via CSS class toggle. Simpler but heavier markup.

Default language: **Thai (TH)**. Detect via `navigator.language` as secondary signal, but always honour `localStorage.getItem('lang')` first.

---

## 10. Theming Specification

```css
/* Light theme (default) */
:root {
  --bg: #f8f8f8;
  --surface: #ffffff;
  --text: #333333;
  --text-muted: #5f5f5f;
  --orange: #f39200;
  --dark-1: #787878;
  --dark-2: #404040;
}

/* Dark theme */
[data-theme="dark"] {
  --bg: #1a1a1a;
  --surface: #2a2a2a;
  --text: #f0f0f0;
  --text-muted: #aaaaaa;
  --orange: #f39200;   /* keep brand orange unchanged */
  --dark-1: #555555;
  --dark-2: #1a1a1a;
}
```

System default: `@media (prefers-color-scheme: dark)` applied when user hasn't overridden.
Manual override stored in `localStorage.getItem('theme')` → `'light'` | `'dark'` | `'system'`.

---

## 11. Open Questions

| # | Question | Owner | Blocking? |
|---|----------|-------|-----------|
| OQ-01 | ~~Full address for สุขุมวิท109~~ **(resolved: found on ISO 9001 cert — 197/41 Moo 1, Soi Santiboon, Sukhumvit 109 Rd, Samrong Nua, Mueang, Samut Prakan 10270; confirm still current)**. Still need **กลการ** branch address + confirm both | Owner | Partial — กลการ pending |
| OQ-02 | Available server assets to copy (brand logos, hero photos) — can we wget from old server? | Dev | Yes — for P0-06, P1-06 |
| OQ-03 | LINE Official Account ID / QR code to include? | Owner | No (P2) |
| OQ-04 | Contact form: where should submissions go? (email relay, Google Forms, Formspree?) | Owner | No (P1) |
| OQ-05 | Are careers listings dynamic, or static content that rarely changes? | Owner | No (P1-07) |

---

## 12. Success Metrics

| Metric | Target | Measure at |
|--------|--------|-----------|
| Lighthouse Performance (mobile) | ≥ 90 | Launch day |
| WCAG axe scan — critical issues | 0 | Launch day |
| Page load LCP | < 2.5s on 4G | Launch day |
| Language toggle works | 100% of text switches | QA pass |
| Mobile usability (no horizontal scroll at 375px) | Pass | QA pass |

---

## 13. Changelog

| Date | Version | Change |
|------|---------|--------|
| 2026-06-14 | 1.0 | Initial spec created from owner decisions (14 Jun 2026), BRAND.md, and DESIGN.md |
| 2026-06-14 | 1.1 | Tech stack set to React (no-build CDN) + Tailwind + Glassmorphism (§8, §8.1). Real assets fetched to `assets/img/` & `assets/brands/`. Prototype `index.html` built implementing P0-01→08 + P1-01,02,03,04,06. |
| 2026-06-14 | 1.2 | **Perf:** all images → WebP (~3.9MB → ~0.6MB, 17/17 load OK). **SEO/P2-06:** favicon (`assets/favicon.svg` wheel mark), JSON-LD `AutoPartsStore`, OG image, theme-color. **Trust:** ISO 9001 (Intertek) certificate added as badge in About. **OQ-01 partial:** สุขุมวิท 109 address recovered from ISO cert → added to offices + per-office Google Maps links; กลการ still pending. Verified via preview MCP: 0 console errors, dark/light/mobile/TH-EN all pass. |
