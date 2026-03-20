# Shop Overview — B.A.D. Condition-Led Shop

> **Developer notes (global):**
> - The shop is implemented as GHL funnel pages — **Option B**: each category page routes visitors to individual product/order forms within GHL.
> - No third-party e-commerce platform is required; all transactions happen inside GHL (Stripe integration).
> - The shop is **condition-led**, not product-led. Navigation is organised by health outcome/condition, not by product type.
> - All copy must comply with the compliant language rules in the **Global Compliance Language** section below.

---

## Shop Philosophy

The B.A.D. shop is not a product catalogue. It is a guided resource organised around how people actually experience their health — by what they are dealing with, not by what we happen to sell.

Visitors do not arrive thinking "I want a supplement." They arrive thinking "I cannot sleep, my joints ache, and I feel like my body has abandoned me." The shop meets them there.

Every category page is built around a **condition or outcome** and presents curated, evidence-informed support options alongside pathways into deeper, personalised support.

**Core commitments:**
- No diet culture, no transformation theatre, no before/after framing.
- No medical claims. Language is always "support", "help reduce discomfort", "evidence-informed."
- Every page surfaces the full B.A.D. support ecosystem — not just a product checkout.
- "Start here" and "Not sure?" pathways are visible on every category page.

---

## Shop Architecture

### Navigation Structure (Condition-Led IA)

```
Shop Homepage
├── Menopause & Hormone Balance          → docs/16-shop-category-menopause.md
├── Endometriosis & Pelvic Pain          → docs/17-shop-category-stubs.md
├── Arthritis & Joint Pain               → docs/17-shop-category-stubs.md
├── Gut Health & Inflammation            → docs/17-shop-category-stubs.md
└── Energy, Stress & Burnout             → docs/17-shop-category-stubs.md
```

### GHL Implementation (Option B)

| Page Type | GHL Build Method |
|---|---|
| Shop Homepage | GHL funnel page with category navigation blocks |
| Category Page | GHL funnel page (one per condition) — see `docs/15-shop-category-page-template.md` |
| Product/Order Form | Standard GHL order form, linked from each category page CTA |
| Checkout | GHL native checkout (Stripe) |
| Post-Purchase | GHL thank-you page + automation workflow |

> **Developer note:** Build each category page as a separate step in a GHL funnel (or as individual funnels sharing the same domain subdirectory). Suggested URL structure: `/shop`, `/shop/menopause`, `/shop/endometriosis`, etc.

---

## Shop Homepage — Wireframe Blocks

> **Developer note:** Build as a single GHL funnel page. Sections map to GHL "rows" or "sections". Mobile-first layout throughout.

---

### Block 1 — Hero

**Headline:**
> Support that starts where you are.

**Subheadline:**
> Everything here is organised around how you feel — not around what we sell. Find your area, explore what might help, and take the next step that feels right for you.

**Brand name + tagline:**
> **B.A.D. Shop**
> Balanced. Authentic. Deserving.

> **Developer note:** No generic "Welcome to our shop" language. Hero is warm and orienting, not promotional.

---

### Block 2 — Condition Navigation Grid

**Section headline:**
> What are you dealing with right now?

Display as a **responsive card grid** (2 columns on mobile, 3 on tablet, 5 on desktop). Each card links to the corresponding category page.

| Card | Condition | Short descriptor | Target URL |
|---|---|---|---|
| 1 | Menopause & Hormone Balance | Perimenopause, hot flushes, hormone shifts | `/shop/menopause` |
| 2 | Endometriosis & Pelvic Pain | Chronic pelvic pain, endo, cycle pain | `/shop/endometriosis` |
| 3 | Arthritis & Joint Pain | Joint stiffness, inflammation, mobility | `/shop/arthritis` |
| 4 | Gut Health & Inflammation | Bloating, IBS, gut-immune connection | `/shop/gut-health` |
| 5 | Energy, Stress & Burnout | Fatigue, nervous system, adrenal depletion | `/shop/energy-stress` |

> **Developer note:** Each card displays: condition title, one-line descriptor, brand-consistent icon or illustration, and a "Explore →" CTA. Cards should be visually equal in weight — no condition should appear to be "featured" above others.

---

### Block 3 — "Not Sure Where to Start?"

**Headline:**
> Not sure where to start?

**Body copy:**
> Sometimes the hardest part is knowing which door to open. If you're dealing with several things at once — or you just want to talk it through before choosing anything — you have two options:

**Two CTA options:**

| Option | Label | Action |
|---|---|---|
| A | Take the free quiz → | Link to GHL quiz funnel (placeholder — see developer note below) |
| B | Message Monika on WhatsApp → | Opens WhatsApp with pre-filled message |

> **Developer note (quiz):** A condition-routing quiz is a future build. Placeholder: create a GHL funnel page at `/shop/quiz` with a "Coming soon" block and a WhatsApp fallback CTA. Tag: `Shop — Quiz Attempted`. When the quiz is built, it should apply one of the condition tags (`Shop — Menopause`, `Shop — Endo`, etc.) based on responses and redirect to the relevant category page.

> **WhatsApp pre-filled message (copy):**
> "Hi Monika — I found the B.A.D. shop and I'm not sure which area is right for me. Could you help?"

---

### Block 4 — Ecosystem Pathways

**Section headline:**
> How B.A.D. support works

Display as a **3-step horizontal row** (stacked on mobile):

| Step | Name | Description | CTA |
|---|---|---|---|
| 1 | Start Here | Mini plan or workshop — low-ticket entry point to explore your condition and get immediate, actionable guidance | Explore Start Here options → |
| 2 | In-Clinic Support | B.A.D. Reset Session — a focused in-person session combining targeted therapy, CBD balm application, and a personalised mini protocol | Book a Reset Session → |
| 3 | Deep Support | B.A.D. Premium Health Coaching (1:1) — full personalised programme for root-cause, long-term change | Find out more → |

> **Developer note:** This block is replicated on every category page (see template). It is the primary pathway block that prevents the shop from being a dead-end. Link targets:
> - "Start Here options" → `/shop/start-here` (placeholder, or link to relevant category page product if quiz routes there)
> - "Book a Reset Session" → GHL booking calendar for B.A.D. Reset Session
> - "Find out more" → Sales page for B.A.D. Premium Health Coaching (`docs/04-sales-page-copy.md`)

---

### Block 5 — Global Disclaimer

> **Developer note:** Display at the bottom of the shop homepage and every category page. Styled as a small-text, soft-background block (e.g. light grey or brand accent). Not hidden — always visible.

> The products and resources in the B.A.D. shop are designed to support your wellbeing and complement a healthy lifestyle. They are not intended to diagnose, treat, cure, or prevent any medical condition. If you have a health concern, please consult your GP or a qualified healthcare professional. Nothing here replaces medical care.

---

### Block 6 — Footer CTA

**Headline:**
> Ready to take the next step?

**Body copy:**
> Start with what feels right. Come back when you're ready for the next layer. B.A.D. is built to grow with you.

**CTA button:**
> Explore the shop →

*(scrolls to Block 2 — condition navigation grid)*

---

## GHL Automation Tags (Shop)

| Tag | When Applied |
|---|---|
| `Shop — Visited` | Contact views any shop page |
| `Shop — Menopause` | Contact views the Menopause category page |
| `Shop — Endo` | Contact views the Endometriosis category page |
| `Shop — Arthritis` | Contact views the Arthritis category page |
| `Shop — Gut Health` | Contact views the Gut Health category page |
| `Shop — Energy Stress` | Contact views the Energy, Stress & Burnout category page |
| `Shop — Quiz Attempted` | Contact clicks the quiz CTA (quiz placeholder) |
| `Shop — Reset Booked` | Contact books a B.A.D. Reset Session from the shop |
| `Shop — Start Here Purchased` | Contact purchases a Start Here product/workshop |
| `Shop — 1:1 Enquiry` | Contact clicks through to the 1:1 membership sales page from the shop |

> **Developer note:** Apply page-view tags using GHL page tracking or workflow triggers on page load. Use these tags to personalise follow-up automations and route contacts to condition-specific nurture sequences.

---

## GHL Workflows (Shop)

| Workflow Name | Trigger | Description |
|---|---|---|
| `Shop — Browse Nurture` | `Shop — Visited` tag applied | Short 2-email nurture introducing the ecosystem; gentle, not pushy |
| `Shop — Reset Follow-Up` | `Shop — Reset Booked` tag applied | Post-session follow-up and product recommendation email |
| `Shop — Start Here Complete` | `Shop — Start Here Purchased` tag applied | Delivery + next-step email recommending the Reset or 1:1 |
| `Shop — 1:1 Bridge` | `Shop — 1:1 Enquiry` tag applied | Routes contact into the existing `Pre-Purchase Nurture` workflow |

---

## Global Compliance Language

### Always use
- "may help support…"
- "evidence-informed"
- "designed to support recovery and regulation"
- "help reduce discomfort"
- "supports the body's natural processes"
- "as part of a balanced lifestyle"

### Never use
- "treats", "cures", "heals", "fixes", "reverses" (any condition name)
- "clinically proven to treat [condition]"
- "eliminate", "eradicate", "get rid of" (symptoms)
- Before/after framing or dramatic transformation language
- Weight loss language or diet culture framing
- "This will work for you" or guaranteed outcome language

### Disclaimer block (mandatory on all shop pages)

> The products and resources in the B.A.D. shop are designed to support your wellbeing and complement a healthy lifestyle. They are not intended to diagnose, treat, cure, or prevent any medical condition. If you have a health concern, please consult your GP or a qualified healthcare professional. Nothing here replaces medical care.

> **Developer note:** This block must appear at the bottom of every shop page. It should be visible without scrolling on mobile if the page is short, or at minimum always present in the footer area. Do not hide it in a collapsed section.

---

## UX Rules (Global)

1. **No urgency / scarcity language in the shop.** The membership funnel uses limited-spots messaging — the shop does not. Products are available; the shop is a safe, unhurried browsing environment.
2. **No pop-ups on category pages.** Visitors are already on a support-seeking journey; interruptive pop-ups break trust. Capture leads through the "Not sure?" block and footer CTAs instead.
3. **WhatsApp is always available.** Every category page must include at minimum one WhatsApp CTA for human support.
4. **Pricing is always visible.** No "request a quote" or hidden pricing. If a product is out of stock, show "Out of stock — notify me" rather than removing the item.
5. **Mobile-first.** All grids and blocks collapse gracefully to single-column on mobile. CTAs are full-width buttons on mobile.
6. **Accessibility.** All images require alt text. Colour contrast must meet WCAG AA minimum. All CTA buttons have descriptive labels (not just "Click here").
