# Funnel Overview — B.A.D. Premium Health Coaching (1:1)

## Purpose

This document is the master funnel map for the B.A.D. Premium 1:1 Health Coaching membership. It describes every step a prospect takes from first landing on the website through to becoming an active, retained member — and everything in between.

> **Key decision:** The full application form has been **removed** and replaced with a lightweight 2-minute fit check. See `docs/02-fit-check.md` for full spec.

---

## Complete Funnel Flow

### Step 1 — Sales Page

**What happens:** Visitor lands on the sales page (organic, paid, referral, or email traffic).

**Goal:** Build trust, explain the offer, address objections, and move them to the fit check CTA.

**GHL notes:**
- Page built as a funnel page in GHL
- CTA buttons scroll to pricing section OR link directly to fit check page
- Urgency element (limited monthly spots) displayed near CTA

**Tag applied on page view:** `Viewed Pricing` (via GHL page tracking)

---

### Step 2 — 2-Minute Fit Check

**What happens:** Prospect clicks CTA → taken to a short 5-question fit check page.

**Goal:** Pre-qualify the lead, create micro-commitment, personalise the experience. This is NOT a gating mechanism — all completions proceed to checkout.

**GHL notes:**
- Built as a multi-step funnel page (one question per step)
- Responses captured as custom contact fields
- On submission: show personalised bridge message, then redirect to checkout after 3 seconds (or button click)

**Tags applied:**
- `Started Fit Check` — on first question view
- `Completed Fit Check` — on form submission

Full spec: `docs/02-fit-check.md`

---

### Step 3 — Checkout Page

**What happens:** Prospect is taken directly from fit check to the checkout page.

**Goal:** Convert the warm lead into a paying member.

**Plan options:**
- Monthly: £180/month
- Quarterly: £480/every 3 months *(pre-selected)*
- Annual: £1,680/year

**Cart bump:** Blood Test Panel — £184 (optional, checkbox shown after plan selection)

**GHL notes:**
- Quarterly plan pre-selected (highest retention tier)
- Order summary sidebar displayed
- Standard GHL payment fields

**Tags applied:**
- `Started Checkout` — on page load
- `Abandoned Checkout` — triggered if payment not completed within X hours (GHL abandoned cart workflow)

Full spec: `docs/05-checkout-and-payment.md`

---

### Step 4 — Post-Checkout One-Click Upsell

**What happens:** Immediately after successful payment, member sees a one-click upsell offer.

**Offer:** Bloods + Minutia.ai Deep Insight Package — £349–£499

**GHL notes:**
- One-click upsell page within the GHL funnel
- Two buttons: "Yes, add this to my order" / "No thanks, I'll start with my current plan"
- If accepted: charge added automatically (GHL order bump / upsell flow)

Full spec: `docs/05-checkout-and-payment.md`

---

### Step 5 — Thank You / Payment Success Page

**What happens:** Member sees the thank you page after payment is confirmed.

**Goal:** Celebrate the decision, reduce buyer's remorse, kick off onboarding.

**Content:**
- Headline: "Welcome, B.A.D.dy — your transformation starts now."
- Personal welcome video placeholder (60–90 sec video from Monika)
- 4 action buttons: Book onboarding call / Complete pre-programme survey / Message Monika on WhatsApp / Join Mini Membership

**Tags applied:**
- `1:1 Active` — applied on purchase confirmation

Full spec: `docs/05-checkout-and-payment.md`

---

### Step 6 — Welcome Email (Immediate)

**What happens:** Automated welcome email sent immediately on purchase.

**Subject:** "Welcome & next steps"

**GHL notes:**
- Triggered by purchase event
- Workflow: `1:1 Purchase — Welcome`

Full copy: `docs/06-email-sequences.md`

---

### Step 7 — Onboarding Sequence (3 emails, ~5 days)

| Email | Subject | Timing |
|---|---|---|
| Email 1 | "Let's get you set up" | Day 1 (or immediate) |
| Email 2 | "A little extra support (without adding pressure)" | Day 3 |
| Email 3 | "A note on testing (when it's helpful)" | Day 5 |

**GHL notes:**
- Workflow: `1:1 Onboarding Sequence`
- Triggered by `1:1 Active` tag

Full copy: `docs/06-email-sequences.md`

---

### Step 8 — Daily / Weekly Support

**What happens:** Ongoing coaching touchpoints throughout the membership.

- **Daily:** WhatsApp food diary check-ins and feedback from Monika
- **Weekly:** Automated check-in email with link to weekly feedback form

**GHL notes:**
- Weekly check-in email on recurring 7-day trigger
- Workflow: `1:1 Weekly Check-In`

---

### Step 9 — Monthly Review (Day 25 Each Month)

**What happens:** On Day 25 of each month, a monthly review is triggered.

- Monthly review email sent
- Member receives check-in form
- Prompt to book monthly 1:1 call

**GHL notes:**
- Workflow: `1:1 Monthly Review`
- Trigger: Date-based, Day 25 of active subscription month

Full copy: `docs/06-email-sequences.md`

---

### Step 10 — Upsell Triggers (Month 2+)

**What happens:** Based on survey responses and symptoms flagged, targeted upsell emails are sent from Month 2 onwards.

| Trigger | Upsell Offer |
|---|---|
| Symptoms still present | Blood Testing — £184–£220 |
| Gut concerns flagged | Microbiome Testing |
| Stress/energy issues | Supplement Bundle — £69–£149/month |

> **Ethics rule:** No upsells sent before Month 1 is complete.

**GHL notes:**
- Workflow: `1:1 Upsell — Month 2+`
- Triggered by survey response conditions

Full details: `docs/08-upsells-and-crosssells.md`

---

### Step 11 — Retention / Loyalty Offer (Month 3)

**What happens:** At Month 3, a loyalty offer is sent to encourage continued membership.

**Offer:** Continue at £150/month for another 3 months (save £30/month)

**GHL notes:**
- Workflow: `1:1 Loyalty Retention — Month 3`
- Trigger: 90 days after `1:1 Active` tag applied

---

### Step 12 — Cancellation → Win-Back Sequence

**What happens:** If a member cancels, a 3-email win-back sequence begins.

| Email | Subject | Timing |
|---|---|---|
| Email 1 | "Just checking in" | Day 1 post-cancellation |
| Email 2 | "What would feel supportive right now?" | Day 7 |
| Email 3 | "When you're ready" | Day 14 |

**Tags applied:**
- `Reactivation` — applied if member re-joins from win-back sequence

**GHL notes:**
- Workflow: `1:1 Cancellation Win-Back`
- Trigger: Subscription cancelled / `1:1 Active` tag removed

Full copy: `docs/06-email-sequences.md`

---

## GHL Automation Tags

### Contact Tags

| Tag | When Applied |
|---|---|
| `1:1 Prospect` | Contact added to pre-purchase nurture sequence |
| `Viewed Pricing` | Contact views the sales page / pricing section |
| `Started Fit Check` | Contact begins the 2-minute fit check |
| `Completed Fit Check` | Contact submits the fit check form |
| `Started Checkout` | Contact lands on the checkout page |
| `Abandoned Checkout` | Contact started checkout but did not complete payment |
| `1:1 Active` | Contact completes purchase — membership is active |
| `Reactivation` | Contact re-joins after cancellation |

---

## GHL Workflows Summary

| Workflow Name | Trigger | Description |
|---|---|---|
| `1:1 Purchase — Welcome` | Purchase confirmed / `1:1 Active` tag | Sends immediate welcome email |
| `1:1 Onboarding Sequence` | `1:1 Active` tag applied | 3-email onboarding sequence over ~5 days |
| `1:1 Weekly Check-In` | Recurring (every 7 days) while `1:1 Active` | Weekly check-in email with form link |
| `1:1 Monthly Review` | Day 25 of each active subscription month | Monthly review email + form + call prompt |
| `1:1 Upsell — Month 2+` | Survey response conditions after Month 1 | Targeted upsell emails based on symptoms |
| `1:1 Loyalty Retention — Month 3` | 90 days after `1:1 Active` | Loyalty price offer for continued membership |
| `1:1 Cancellation Win-Back` | Subscription cancelled / `1:1 Active` removed | 3-email win-back sequence over 14 days |
| `1:1 Abandoned Checkout` | Started checkout, no payment within X hours | Re-engagement email or SMS |
| `Pre-Purchase Nurture` | `1:1 Prospect` tag applied | 5-email nurture sequence |
