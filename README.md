# AutoHaus by Patanayont — Website

ศูนย์อะไหล่รถยนต์แท้แบบ **ONE-STOP** สำหรับรถญี่ปุ่นชั้นนำ · *Total Automotive Concept* · ดำเนินธุรกิจกว่า **60 ปี** (ตั้งแต่ พ.ศ. 2507)

Modern, brand-forward landing page for **หจก. พัฒนายนตร์ (Patanayont)** — trading as **AutoHaus®**.

---

## Stack

- **React 18** (no-build, via CDN UMD + Babel standalone) — single `index.html`, runs by just opening in a browser
- **Tailwind CSS** (Play CDN) with brand tokens mapped from `BRAND.md`
- **Glassmorphism** visual style over an industrial-heritage aesthetic
- **Fonts:** Montserrat (display) · Kanit (Thai+Latin) · Inter (body)

## Features

- 🧭 **Audience router** — 3 segments: parts shops (B2B) · workshops/fleets · car owners (B2C)
- 🌐 **Bilingual TH/EN** toggle (persisted)
- 🌗 **Dark / Light / System** theme
- 🔠 Adjustable **font size** (A− / A / A+)
- 📱 **Mobile-first**, responsive 375 → 1280px
- ♿ **WCAG 2.1 AA** — verified contrast (e.g. CTA 7.7:1 AAA)
- ⚡ **WebP** imagery (~0.6 MB total) · SEO JSON-LD · favicon

## Run locally

No build step required — serve the folder with any static server:

```bash
python3 -m http.server 4521
# then open http://localhost:4521
```

## Structure

```
index.html              # the whole app (React + Tailwind, single file)
BRAND.md                # brand guidelines — source of truth (colors, voice, logo, contact)
DESIGN.md               # design system (type scale, spacing, components)
WEBSITE-SPEC.md         # living PRD — update BEFORE any change
CLAUDE.md               # working rules for the dev/designer persona
assets/
  logoPTY.svg           # master logo (AutoHaus)
  favicon.svg
  img/                  # hero & content imagery (.webp + original)
  brands/               # 7 Japanese marque logos
```

## Working rules

1. **Update `WEBSITE-SPEC.md` first** — code follows spec.
2. **No invented content** — company facts come from `BRAND.md` only.
3. **WCAG 2.1 AA** minimum on every color combo.
4. **Mobile-first**, test at 375 / 768 / 1024 / 1280px.

## Production notes

For production, precompile the JSX (drop Babel standalone) and use the Tailwind CLI/PostCSS instead of the Play CDN.

---

*© หจก. พัฒนายนตร์ (Patanayont) · Genuine Parts · OES Quality · ISO 9001 Certified · 60 Years*
