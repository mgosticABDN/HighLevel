# B.A.D. — Developer Repository

## What This Repo Is

This repository contains the complete build specifications for **B.A.D. (Balanced. Authentic. Deserving.)** — a lifestyle medicine brand led by Monika. It covers two build areas:

1. **B.A.D. Premium Health Coaching (1:1)** — the flagship membership funnel (docs 01–08)
2. **B.A.D. Condition-Led Shop** — a GHL-native shop funnel organised by health condition/outcome (docs 14–17)

It is the single source of truth for every developer, copywriter, and automation specialist working on this project.

All content is written in developer-ready Markdown. Each file maps directly to a build task.

---

## Brand

**B.A.D. — Balanced. Authentic. Deserving.**

A premium 1:1 lifestyle medicine health coaching membership for midlife women. The coaching is led by **Monika**.

| Attribute | Detail |
|---|---|
| **Audience** | Midlife women, ages 35–60 |
| **Concerns** | Fatigue, hormonal imbalance, inflammation, weight, gut issues, perimenopause |
| **Tone** | Warm, clinical-meets-compassionate, never pushy, never salesy |
| **Avoid** | Transformation theatre, before/after language, diet culture |
| **Always** | Meet them where they are, science-backed, personally supportive |

---

## The Funnel at a Glance

| Step | Description |
|---|---|
| 1 | Visitor lands on **Sales Page** |
| 2 | Clicks CTA → taken to **2-Minute Fit Check** (3–5 questions, not a full application) |
| 3 | Fit check submitted → taken directly to **Checkout Page** |
| 4 | Selects plan (Monthly £180 / Quarterly £480 / Annual £1,680) + optional cart bump (Blood Test £184) |
| 5 | One-click post-checkout upsell: Bloods + Minutia.ai Deep Insight Package £349–£499 |
| 6 | Payment success → **Thank You Page** |
| 7 | Automated **Welcome Email** triggered immediately |
| 8 | **Onboarding sequence** (3 emails over ~5 days) |
| 9 | **Daily/weekly support** (WhatsApp food diary, weekly check-in form) |
| 10 | **Monthly review automation** (Day 25 each month) |
| 11 | **Upsell triggers** (Month 2+, based on survey responses/symptoms) |
| 12 | **Retention/loyalty offer** (Month 3) |
| 13 | **Cancellation → Win-back sequence** (14 days, 3 emails) |

---

## File Index

### B.A.D. Premium Health Coaching (1:1) — Membership Funnel

| File | Description |
|---|---|
| `docs/01-funnel-overview.md` | Complete step-by-step funnel map, GHL automation tags and workflows |
| `docs/02-fit-check.md` | 2-minute fit check that replaces the full application form; sits between sales page CTA and checkout |
| `docs/03-offer-and-pricing.md` | Pricing tiers, value stack, optional add-ons, special conditions |
| `docs/04-sales-page-copy.md` | Full sales page copy: hero, sections, FAQ, urgency element, testimonials, CTAs |
| `docs/05-checkout-and-payment.md` | Checkout page spec, cart bump, post-checkout upsell, thank you page |
| `docs/06-email-sequences.md` | All email sequences fully written out with GHL triggers, timing and reference table |
| `docs/07-member-experience.md` | What members receive day-to-day, week-to-week, month-to-month |
| `docs/08-upsells-and-crosssells.md` | Full upsell and cross-sell system with automation triggers and ethics rules |

### B.A.D. Condition-Led Shop — GHL Shop Funnel

| File | Description |
|---|---|
| `docs/14-shop-overview.md` | Shop philosophy, overall architecture, homepage wireframe blocks/sections, global compliance language and UX rules |
| `docs/15-shop-category-page-template.md` | Reusable category page template with standardised section layout, CTAs, and GHL build reference |
| `docs/16-shop-category-menopause.md` | Fully written Menopause & Hormone Balance category page: copy, block structure, product cards, CTAs, and GHL build reference |
| `docs/17-shop-category-stubs.md` | Stubs (headings + TODOs) for Endometriosis & Pelvic Pain, Arthritis & Joint Pain, Gut Health & Inflammation, and Energy, Stress & Burnout category pages |

---

## Key Decisions

1. **No full application form** — replaced with a lightweight 2-minute fit check (`docs/02-fit-check.md`). Everyone who completes it proceeds directly to checkout. This increases micro-commitment and conversion without creating a barrier.
2. **Blood test FAQ corrected** — blood testing is optional, not required.
3. **Social proof email added** as Email 3 in the pre-purchase nurture sequence.
4. **Cart bump reframed** — positioned as "Complete your protocol" rather than a simple add-on.
5. **Urgency/scarcity added** to the sales page — limited monthly spots messaging.
6. **Thank you page video placeholder** added for Monika's personal welcome video (reduces buyer's remorse, increases onboarding completion).
7. **Quarterly plan pre-selected** at checkout — highest retention tier.

---

## Tech Stack

**GoHighLevel (GHL)** — all pages, funnels, automations, email sequences, contact tags, and workflows are built inside GHL unless otherwise noted.

---

## How to Use This Repo

### Membership Funnel (docs 01–08)

1. Read `docs/01-funnel-overview.md` first — it gives you the full picture.
2. Build each page/component using the corresponding spec file.
3. Set up GHL automations using the tags and workflow names listed in each doc.
4. Refer to `docs/06-email-sequences.md` for the GHL Developer Reference Table mapping every email to its trigger, workflow, and timing.

### Condition-Led Shop (docs 14–17)

1. Read `docs/14-shop-overview.md` first — shop philosophy, architecture, homepage wireframe, compliance language rules, and GHL tag/workflow overview.
2. Use `docs/15-shop-category-page-template.md` as the reusable build template for every category page.
3. `docs/16-shop-category-menopause.md` is the completed reference implementation — use it as the benchmark for all other category pages.
4. `docs/17-shop-category-stubs.md` contains the four remaining category page stubs. Complete each stub before building the corresponding GHL funnel page.
5. All shop pages must include the disclaimer block and comply with the language rules in `docs/14-shop-overview.md`.
