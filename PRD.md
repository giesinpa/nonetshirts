# Product Requirements Document: nøne.

**Version:** 1.0
**Date:** February 15, 2026
**Status:** In Development

---

## 1. Overview

**nøne.** is a minimalist t-shirt brand built on the philosophy of *"Designed for nothing. Made for everything."* The brand strips away branding noise, trend-chasing, and unnecessary design — delivering premium cotton essentials defined by intentional construction and a perfect fit.

This document covers the digital platform that supports the brand: a research-driven fit validation tool, a brand storefront, and the checkout experience.

---

## 2. Problem Statement

The t-shirt market is saturated with brands that prioritize logos, graphics, and trend cycles over fit, fabric, and construction. Consumers who want high-quality, minimalist essentials struggle to find brands that:

- Prioritize fit validation through real body data
- Offer transparent construction details (fabric weight, stitch type, sleeve cut)
- Maintain a consistent, distraction-free brand identity
- Provide a frictionless path from discovery to purchase

---

## 3. Target Audience

| Segment | Description |
|---------|-------------|
| **Primary** | Design-conscious consumers aged 20–40 who value minimalism, quality materials, and intentional wardrobe choices |
| **Secondary** | Fashion industry professionals and enthusiasts interested in garment construction and fit research |
| **Tertiary** | Sustainability-minded buyers who prefer fewer, better-made pieces over fast fashion |

---

## 4. Product Components

### 4.1 Fit Validation Protocol (`index.html`)

An interactive, multi-step research form that collects body measurement data and fit preferences to inform garment design.

**Current State:** Built and deployed

**Steps:**

| Step | Section | Inputs |
|------|---------|--------|
| 0 | Welcome | — |
| 1 | Identity | Full name, email, date of birth, gender identity |
| 2 | Body Measurements | Chest/bust (cm), shoulder width (cm), collar/neckline (cm), body length (cm) |
| 3 | Fit Preference | Fit style (checkbox: loose/boxy, relaxed, regular, slim, tight), preferred size (S–3XL) |
| 4 | Fabric & Texture | Cotton thickness (radio: light, mid-weight, heavy), additional notes (textarea) |
| 5 | Construction Specs | Collar style, hem/bottom, seams/stitch detail, sleeve style/cut (textareas), arm/sleeve length (cm) |
| 6 | Fit Check | Photo upload (optional), fit score (1–10 range slider) |
| 7 | Final Words | Experience feedback, improvement suggestions (textareas) |
| 8 | Thank You | Confirmation |

**Features:**
- Step-by-step single-question-at-a-time navigation
- Progress bar with step indicator
- SVG body measurement diagrams
- Keyboard navigation (Enter to advance)
- Form data collected as JSON (logged to console)
- Smooth fade transitions between steps

### 4.2 Brand Store (`store.html`)

A storefront mockup showcasing the product collection with direct-to-checkout purchasing.

**Current State:** Built with placeholder product images (SVG t-shirt illustrations)

**Sections:**

| Section | Purpose |
|---------|---------|
| Navigation | Fixed top bar with logo, Shop/About/Research links, cart icon |
| Hero | Full-viewport brand statement with CTA |
| Marquee Ticker | Scrolling brand values (100% Cotton, Ethically Made, No Logos, etc.) |
| Product Grid | 6-product grid with hover-to-reveal "Buy Now" buttons |
| Lookbook | 3-panel editorial layout |
| Brand Philosophy | Mission statement with link to fit research |
| Newsletter | Email signup |
| Footer | Navigation, social links, copyright |

**Product Catalog (Mockup):**

| Product | Variant | Price |
|---------|---------|-------|
| Essential Tee | Black | €45 |
| Essential Tee | White | €45 |
| Oversized Tee | Black | €55 |
| Heavyweight Tee | Charcoal | €60 |
| Drop Shoulder Tee | Off-White | €50 |
| Long Sleeve Tee | Black | €55 |

### 4.3 Checkout

**Current State:** Stripe Payment Link integration

- All product cards link to a single Stripe checkout URL
- Opens in new tab (`target="_blank"`)
- URL: `https://buy.stripe.com/6oU4gy7X33iK2MsfYt5sA04`

---

## 5. Design System

### 5.1 Brand Identity

- **Name:** nøne. (lowercase, slashed ø, trailing period)
- **Tone:** Quiet confidence. No excess. Every word and pixel earns its place.
- **Tagline:** *"Nothing unnecessary. Everything intentional."*
- **Philosophy:** *"Designed for nothing. Made for everything."*

### 5.2 Color Palette

| Token | Value | Usage |
|-------|-------|-------|
| `--black` | `#0a0a0a` | Primary background |
| `--white` | `#f5f5f5` | Primary text, buttons |
| `--gray-100` | `#e5e5e5` | — |
| `--gray-200` | `#d4d4d4` | Hover states |
| `--gray-300` | `#a3a3a3` | Body text |
| `--gray-400` | `#737373` | Secondary text, labels |
| `--gray-500` | `#525252` | Hints, muted text |
| `--gray-600` | `#404040` | Borders, dividers |
| `--gray-700` | `#262626` | Card backgrounds |
| `--gray-800` | `#171717` | Subtle backgrounds |

### 5.3 Typography

| Role | Font | Weight | Usage |
|------|------|--------|-------|
| Body | Inter | 300–600 | All UI text |
| Brand / Mono | Space Mono | 400, 700 | Logo, labels, step indicators, prices |
| Logo | Inter | 900 | SVG logo rendering |

### 5.4 Components

- **Buttons:** Primary (white bg), Outline (bordered), Ghost (text-only)
- **Option Cards:** Radio and checkbox cards with indicator dots
- **Measurement Cards:** Icon + description + input with unit label
- **Range Slider:** Custom styled with centered large value display
- **File Upload:** Dashed border area with drag-and-drop styling
- **Product Cards:** Image + info row, hover reveals "Buy Now" overlay

### 5.5 Motion

- Easing: `cubic-bezier(0.4, 0, 0.2, 1)`
- Section transitions: 0.5s fade + translateY
- Hover states: 0.2s–0.4s
- Marquee: 20s linear infinite scroll

---

## 6. Technical Architecture

### 6.1 Current Stack

| Layer | Technology |
|-------|-----------|
| Frontend | Vanilla HTML, CSS, JavaScript |
| Fonts | Google Fonts (Inter, Space Mono) |
| Hosting | Cloudflare Pages (static) |
| Payments | Stripe Payment Links |
| Version Control | Git / GitHub |
| Build | None (static files served directly) |

### 6.2 File Structure

```
nonetshirts/
├── index.html          # Fit Validation Protocol (research form)
├── store.html          # Brand store mockup
├── assets/
│   └── logo.svg        # nøne. wordmark (SVG, transparent bg)
├── README.md
└── PRD.md
```

### 6.3 Deployment

- **Platform:** Cloudflare Pages
- **Build command:** *(none)*
- **Build output directory:** `/`
- **Production branch:** `main`

---

## 7. Roadmap

### Phase 1 — Foundation (Current)

- [x] Fit Validation Protocol (interactive multi-step form)
- [x] Brand store mockup with product grid
- [x] nøne. logo (SVG, transparent background)
- [x] Stripe checkout integration (payment link)
- [x] Responsive design (mobile + desktop)
- [x] Cloudflare Pages deployment
- [x] Footer with social links and navigation

### Phase 2 — Data & Product

- [ ] **Backend API** for form submission storage (e.g., Cloudflare Workers + D1/KV, or Supabase)
- [ ] **Admin dashboard** to view and export fit validation responses
- [ ] **Real product photography** to replace SVG placeholders
- [ ] **Individual product pages** with size selector, image gallery, and detailed specs
- [ ] **Per-product Stripe checkout links** (unique link per SKU/size)
- [ ] **Size guide page** powered by aggregated fit research data

### Phase 3 — Commerce

- [ ] **Shopping cart** with multi-item support
- [ ] **Stripe Checkout Sessions** (server-side) for full e-commerce flow
- [ ] **Order confirmation** and email receipts
- [ ] **Inventory management** integration
- [ ] **Shipping calculator** by region
- [ ] **Returns/exchange policy** page

### Phase 4 — Growth

- [ ] **Email marketing** integration (newsletter → Mailchimp/Resend)
- [ ] **SEO optimization** (meta tags, Open Graph, structured data)
- [ ] **Analytics** (Plausible or Cloudflare Web Analytics)
- [ ] **About page** with brand story and manufacturing details
- [ ] **Journal/blog** for editorial content and lookbook entries
- [ ] **Social proof** (customer reviews, fit photos)
- [ ] **Referral program**

---

## 8. Success Metrics

| Metric | Target | Measurement |
|--------|--------|-------------|
| Fit Protocol completions | 100+ responses in first month | Form submission count |
| Store page engagement | >60% scroll to product grid | Scroll depth analytics |
| Checkout click-through | >5% of store visitors | Stripe link clicks / page views |
| Conversion rate | >2% of checkout clicks | Stripe completed payments / clicks |
| Newsletter signups | 200+ in first quarter | Signup form submissions |
| Mobile responsiveness | 0 layout issues on common devices | Manual QA + Lighthouse audit |

---

## 9. Constraints & Assumptions

- **No build tooling required.** The site is pure static HTML/CSS/JS served directly. This keeps deployment simple but limits componentization as the site grows.
- **Single Stripe Payment Link.** All products currently route to the same checkout. Per-product links or Stripe Checkout Sessions are needed before real sales.
- **No backend.** Form data is logged to console only. A storage solution is needed to capture research responses.
- **Placeholder imagery.** Product photos must be shot and integrated before launch.
- **No authentication.** The fit protocol is open to anyone. No login or account system exists.

---

## 10. Open Questions

1. Should the fit validation data feed directly into a custom size recommendation engine?
2. What is the target launch date for real product sales vs. the research-only phase?
3. Will the brand expand beyond t-shirts (e.g., pants, hoodies), and should the store architecture account for that?
4. Should form responses be tied to future customer accounts for personalized sizing?
5. What shipping regions will be supported at launch?
