# Shop Category Page Template — B.A.D. Condition-Led Shop

> **Developer notes (global):**
> - This template is reusable across all five condition category pages.
> - Each category page is built as a GHL funnel page. Product CTAs link to GHL order forms.
> - Sections below map 1:1 to GHL funnel rows/sections. Build in order.
> - Replace all `[CONDITION]`, `[CONDITION_TAG]`, and `[PLACEHOLDER]` tokens for each specific category.
> - For fully written copy, see the individual category files (e.g. `docs/16-shop-category-menopause.md`).

---

## Standard Section Layout

Every category page uses the following section order. Do not reorder sections.

| # | Section Name | Purpose |
|---|---|---|
| 1 | Hero | Orient the visitor; validate their experience |
| 2 | "This is for you if…" | Qualify and resonate — not a filter, a mirror |
| 3 | Curated Support Options | Product/resource grid with compliant descriptions |
| 4 | "Start Here" Entry Point | Low-ticket entry — mini plan or workshop |
| 5 | In-Clinic: B.A.D. Reset Session | In-person session CTA |
| 6 | Deep Support: B.A.D. Premium 1:1 | Membership pathway bridge |
| 7 | "Not Sure?" Block | WhatsApp + quiz routing |
| 8 | Testimonials | Social proof — condition-relevant, compliant |
| 9 | Disclaimer | Mandatory compliance block |

---

## Section 1 — Hero

> **Developer note:** Full-width section. Headline and subheadline are the most important copy on the page. No product imagery in the hero — use a warm, lifestyle-oriented image (no clinical settings, no before/after).

**Headline:**
> [CONDITION headline — warm, validating, written for the person not the product]

**Subheadline:**
> [One to two sentences that acknowledge what the visitor is experiencing, followed by a reassurance that support exists. No claims.]

**Brand anchor:**
> **B.A.D. — Balanced. Authentic. Deserving.**

**CTA button (primary):**
> Explore support options →

*(Scrolls to Section 3 — Curated Support Options)*

---

## Section 2 — "This is for you if…"

> **Developer note:** Display as a bulleted list with brand icon/checkmark. 5–8 bullets. These are lived experiences, not medical symptoms — write them as the visitor would describe them to a friend, not a doctor. This section has no CTA; it exists purely to build recognition and trust.

**Section headline:**
> This is for you if…

**Bullets:**
- [Bullet 1 — lived experience description]
- [Bullet 2]
- [Bullet 3]
- [Bullet 4]
- [Bullet 5]
- [Bullet 6 — optional]
- [Bullet 7 — optional]

---

## Section 3 — Curated Support Options

> **Developer note:**
> - Display as a card grid. 1 column on mobile, 2 on tablet, 3 on desktop.
> - Each card: product/resource name, one-line description, price (if applicable), CTA button linking to GHL order form.
> - Maximum 6 items per category page to avoid overwhelming the visitor.
> - Products are curated per condition — do not display the full product catalogue.
> - All descriptions must follow the Global Compliance Language rules (`docs/14-shop-overview.md`).

**Section headline:**
> Support options for [CONDITION]

**Card layout per item:**

```
[Product/Resource Name]
[One-line compliant description]
[Price]
[CTA button: "Find out more" or "Add to order"]
```

**Cards (populate per category):**

| # | Name | Compliant Description | Price | CTA |
|---|---|---|---|---|
| 1 | [PRODUCT 1] | [Description — must not claim to treat/cure] | £[X] | Find out more → |
| 2 | [PRODUCT 2] | [Description] | £[X] | Find out more → |
| 3 | [PRODUCT 3] | [Description] | £[X] | Find out more → |
| 4 | [PRODUCT 4] | [Description] | £[X] | Find out more → |
| 5 | [PRODUCT 5] | [Description] | £[X] | Find out more → |
| 6 | [RESOURCE — e.g. guide or mini plan] | [Description] | Free / £[X] | Download → |

> **Developer note:** Each "Find out more →" CTA opens the corresponding GHL order form. Build one order form per product, named consistently: `Shop — [Product Name]`. Link from card CTA button.

---

## Section 4 — "Start Here" Entry Point

> **Developer note:** Display as a standalone highlighted block (contrasting background colour — e.g. soft brand accent). This is the low-ticket entry point designed for visitors who are not yet ready to commit to a full programme or higher-ticket product.

**Block label (small caps / eyebrow text):**
> Start here

**Headline:**
> New to B.A.D.? Start with the [CONDITION] Mini Plan.

**Body copy:**
> Not sure where to begin? The [CONDITION] Mini Plan is a short, focused starting point — a structured guide to understanding your [condition area] and three immediate steps you can take this week.
>
> It's practical, evidence-informed, and designed to work alongside whatever else you have going on. No overhaul required.

**Price:**
> £[X] — or free with your first B.A.D. Reset Session

**CTA button:**
> Get the Mini Plan →

*(Links to GHL order form for the mini plan product)*

> **Developer note:** If the mini plan for this condition does not yet exist, replace this block with a "Coming soon — join the list" block with an email capture form (GHL form). Tag: `Shop — [CONDITION_TAG] Mini Plan Waitlist`.

---

## Section 5 — In-Clinic: B.A.D. Reset Session

> **Developer note:** This block is identical across all category pages. Do not modify the copy — only update the condition-specific framing sentence at the top. This is a CTA block, not a product page; keep it concise.

**Block label (eyebrow text):**
> In-clinic support

**Headline:**
> The B.A.D. Reset Session

**Body copy:**
> Sometimes you need something that works *now* — not just a plan to work through.
>
> The B.A.D. Reset is a focused 45-minute in-person session designed to support your body's own regulation and recovery. It combines targeted machine therapy, CBD balm application to support local inflammation, and a personalised mini protocol you leave with on the day.
>
> It is not a treatment. It is a reset — something that helps your body feel heard, and gives you a clear, immediate next step.

**Pricing:**
> Intro: £25 · Single session: £45 · 3-session pack: £120

**CTA button:**
> Book a Reset Session →

*(Links to GHL booking calendar for B.A.D. Reset Session)*

**Compliance note (inline, small text below button):**
> The B.A.D. Reset Session is a wellness session, not a medical treatment. It does not diagnose or treat any condition.

---

## Section 6 — Deep Support: B.A.D. Premium 1:1

> **Developer note:** This block bridges shop visitors into the main membership funnel. Keep it short — it is a signpost, not a sales page. The full sales page is at `docs/04-sales-page-copy.md`. Link the CTA to that page.

**Block label (eyebrow text):**
> Deep support

**Headline:**
> When you're ready to go deeper — B.A.D. Premium 1:1

**Body copy:**
> If you're dealing with [CONDITION] alongside other symptoms, or if you've been managing this for a long time without feeling like anything has really shifted, it might be time for something more personalised.
>
> B.A.D. Premium Health Coaching (1:1) is a full coaching membership — monthly strategy sessions, daily WhatsApp support, a personalised protocol, and a real human who understands the complexity of what you're navigating.
>
> You do not have to keep figuring this out alone.

**CTA button:**
> Find out more about B.A.D. Premium 1:1 →

*(Links to sales page — `docs/04-sales-page-copy.md` / `/sales` funnel page)*

---

## Section 7 — "Not Sure?" Block

> **Developer note:** Replicated from the shop homepage. Always present on every category page. Display as a soft-background callout block.

**Headline:**
> Not sure where to start?

**Body copy:**
> If you're dealing with more than one thing, or you just want to talk it through before choosing anything, you have two options:

**CTA options:**

| Option | Label | Action |
|---|---|---|
| A | Take the free quiz → | `/shop/quiz` (placeholder — see `docs/14-shop-overview.md`) |
| B | Message Monika on WhatsApp → | WhatsApp pre-filled: "Hi Monika — I'm looking at the [CONDITION] section and would love some guidance on where to start." |

---

## Section 8 — Testimonials

> **Developer note:** Display as 2–3 card slots. Testimonials must be condition-relevant. Replace placeholder text with real client testimonials when available. Follow compliant language rules — no outcome guarantees. Outcome language should be client-reported and clearly framed as individual experience.

**Section headline:**
> What others have experienced

---

**Testimonial 1 — placeholder**

> "[Condition-relevant testimonial describing lived experience, not a medical outcome. E.g. 'I felt more understood in one session than I had in years of trying to manage this alone.']"
>
> — *[Name], [Age]*

---

**Testimonial 2 — placeholder**

> "[Testimonial focused on the support experience, not a specific physical claim.]"
>
> — *[Name], [Age]*

---

**Testimonial 3 — optional placeholder**

> "[Optional third testimonial.]"
>
> — *[Name], [Age]*

---

## Section 9 — Disclaimer

> **Developer note:** Display as a visible, soft-background block at the bottom of the page. Do not collapse or hide. See `docs/14-shop-overview.md` for full compliance language rules.

> The products and resources in the B.A.D. shop are designed to support your wellbeing and complement a healthy lifestyle. They are not intended to diagnose, treat, cure, or prevent any medical condition. If you have a health concern, please consult your GP or a qualified healthcare professional. Nothing here replaces medical care.

---

## GHL Build Reference (Per Category Page)

| Element | GHL Action |
|---|---|
| Page load | Apply tag `Shop — Visited` and `Shop — [CONDITION_TAG]` |
| "Get the Mini Plan" click | Apply tag `Shop — [CONDITION_TAG] Mini Plan Interest` |
| "Book a Reset Session" click | Apply tag `Shop — Reset Booked` (or on booking confirmation) |
| "Find out more about 1:1" click | Apply tag `Shop — 1:1 Enquiry`; trigger `Shop — 1:1 Bridge` workflow |
| WhatsApp CTA click | Apply tag `Shop — WhatsApp Contact` |
| Quiz CTA click | Apply tag `Shop — Quiz Attempted` |

> **Developer note:** Use GHL page tracking or embedded workflow triggers on button clicks where possible. For click-based tags (WhatsApp, quiz), wrap CTAs in GHL tracked links or use JavaScript custom actions if available in your GHL plan.

---

## Naming Conventions (GHL)

| Resource Type | Naming Pattern | Example |
|---|---|---|
| Funnel page | `Shop — [Condition]` | `Shop — Menopause` |
| Order form | `Shop — [Product Name]` | `Shop — Menopause Mini Plan` |
| Tag (page view) | `Shop — [Condition Tag]` | `Shop — Menopause` |
| Tag (interest) | `Shop — [Condition Tag] [Action]` | `Shop — Menopause Mini Plan Interest` |
| Workflow | `Shop — [Condition] [Trigger]` | `Shop — Menopause Browse Nurture` |
| Custom field | `shop_[condition]_[field]` | `shop_menopause_mini_plan_purchased` |
