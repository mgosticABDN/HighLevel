# Checkout & Payment — B.A.D. Premium Health Coaching (1:1)

## Checkout Page

### Plan Selector

Display as radio buttons. **Quarterly pre-selected by default.**

| Option | Price | Badge | Detail |
|---|---|---|---|
| Monthly | £180/month | — | Rolling, cancel with 30 days' notice |
| Quarterly | £480/every 3 months | **MOST POPULAR** | Equivalent to £160/month — saves £60 |
| Annual | £1,680/year | **BEST VALUE** | Equivalent to £140/month — saves £480 (4 months free) |

> **Developer note:** Pre-select Quarterly on page load. Savings messaging should update dynamically based on selected plan.

---

### Cart Bump (Checkbox — shown after plan selection)

**Checkbox label:**
> ☐ Complete your protocol — add your personalised Blood Test Panel to get results 3x faster

**Price:** +£184

**What's included (display in expandable/tooltip):**
- Hormone balance markers
- Thyroid function
- Metabolic markers
- Nutrient status
- Inflammation markers
- Gut & liver health
- Cardiovascular risk

> **Key decision:** Cart bump is positioned as "completing the protocol" — not a generic upsell. This framing increases take-rate by making it feel like a natural part of the programme.

---

### Order Summary Sidebar

Display a live order summary panel on the right (desktop) or above payment fields (mobile):

- Plan name + price
- Cart bump (if selected) + £184
- **Total today**
- Payment terms note (e.g. "Renews every 3 months. Cancel anytime with 30 days' notice.")

---

### Payment Fields

Standard GHL payment fields:
- Full name
- Email address
- Card number / payment method (Stripe integration)
- Billing address (if required)

---

### Trust Elements (below payment button)

- 🔒 Secure payment via Stripe
- Money-back / satisfaction note (if applicable — confirm with Monika)
- "Monika reviews every fit check personally" reassurance line

---

## Post-Checkout One-Click Upsell Page

Displayed immediately after successful payment — before the Thank You page.

### Headline
> One last thing before you begin…

### Offer: Bloods + Minutia.ai Deep Insight Package

**Price:** £349–£499

**Body copy:**

> You've made a great decision. Before we dive in, I want to offer you the most complete starting point possible.
>
> The Bloods + Minutia.ai Deep Insight Package combines your personalised blood test panel with Minutia.ai's advanced gut simulation technology — giving us a full biological picture of your body before we begin.
>
> This means your nutrition protocol, supplement recommendations, and coaching plan can all be built around real data from day one — not guesswork.

**What's included:**
- Full blood test panel (hormone balance, thyroid, metabolic markers, nutrients, inflammation, gut & liver, cardiovascular risk)
- Minutia.ai gut simulation and microbiome analysis
- Personalised deep insights report
- Monika's interpretation layered into your coaching plan

**Two action buttons:**

| Button | Action |
|---|---|
| "Yes, add this to my order" | Charges additional amount and redirects to Thank You page |
| "No thanks, I'll start with my current plan" | Redirects to Thank You page without adding upsell |

> **Developer note:** One-click upsell must charge without requiring the customer to re-enter payment details (GHL order bump / upsell functionality). Both buttons must redirect to the Thank You page.

---

## Thank You / Payment Success Page

### Headline
> Welcome, B.A.D.dy — your transformation starts now.

### Video Placeholder

> **Developer note:** Add a video embed placeholder above the body copy. This is for a 60–90 second personal welcome video from Monika. The video reduces buyer's remorse and increases onboarding completion rates. Label the placeholder clearly: `[VIDEO: Monika's personal welcome — 60–90 seconds]`

---

### Body Copy

> You've just said yes to support, clarity, and a different way of caring for your health.
>
> Inside this membership, I won't rush you or overwhelm you. And I definitely won't ask you to ignore your life to "do it properly".
>
> Instead, I'll work with your real routines, your real stress load, and your real body.
>
> Your welcome email is on its way. In the meantime, here's what to do next:

---

### Action Buttons (4)

Display as clear, prominent buttons:

| # | Button Label | Action |
|---|---|---|
| 1 | 📅 Book your onboarding call | Links to Monika's calendar booking page |
| 2 | 📝 Complete your pre-programme survey | Links to GHL pre-programme survey form |
| 3 | 💬 Message Monika on WhatsApp | Opens WhatsApp with pre-filled message or link to WhatsApp |
| 4 | 🌱 Join the Mini Membership | Links to Mini Membership access/area |

---

### Closing Note

> This is your B.A.D. season.
> Balanced. Authentic. Deserving.
>
> — Monika 💜

---

## GHL Developer Notes — Checkout Flow

| Step | GHL Action |
|---|---|
| Checkout page loaded | Apply tag `Started Checkout` |
| Plan selected | Update contact field `membership_plan` |
| Cart bump selected | Update contact field `blood_test_added = true` |
| Payment completed | Apply tag `1:1 Active`, trigger workflow `1:1 Purchase — Welcome` |
| Upsell accepted | Update contact field `upsell_bloods_minutia = true` |
| Upsell declined | No action required |
| Thank You page loaded | Confirm `1:1 Active` tag is applied |
| Checkout started but not completed (X hours) | Apply tag `Abandoned Checkout`, trigger win-back workflow |
