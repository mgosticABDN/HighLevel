# 2-Minute Fit Check — B.A.D. Premium Health Coaching (1:1)

## Overview

The 2-minute fit check replaces the full application form. It sits **between** the sales page CTA and the checkout page.

> **Key decision:** This is NOT a gating mechanism. Everyone who completes the fit check proceeds to checkout. Its purpose is to pre-qualify the lead, make them feel seen and chosen, and increase checkout conversion through micro-commitment.

**Funnel position:** Sales Page CTA → Fit Check → Bridge Message → Checkout Page

---

## Purpose

| Goal | Detail |
|---|---|
| **Pre-qualify** | Capture lead data about symptoms, goals and history |
| **Micro-commitment** | Small investment of time creates psychological ownership |
| **Personalisation** | Responses feed into onboarding and messaging personalisation |
| **Conversion** | Bridge message makes checkout feel like a natural, earned next step |
| **Trust** | Positions Monika as attentive — "she reviews every response personally" |

---

## Questions (5 max, all required except Q5)

---

### Question 1 — Main Health Goal

**Label:** What's your main health goal right now?

**Type:** Multiple choice (single select)

**Options:**
- More energy & less fatigue
- Hormone balance / perimenopause support
- Weight loss that actually sticks
- Gut health & digestion
- Reducing inflammation
- Stress & nervous system support
- Something else

**GHL field name:** `fit_check_health_goal`

---

### Question 2 — Duration

**Label:** How long have you been dealing with this?

**Type:** Multiple choice (single select)

**Options:**
- Less than 6 months
- 6–12 months
- 1–2 years
- 2+ years

**GHL field name:** `fit_check_duration`

---

### Question 3 — Previous Experience

**Label:** Have you tried other programmes or plans before?

**Type:** Multiple choice (single select)

**Options:**
- Yes, and nothing has worked long-term
- Yes, and I had some success but it didn't last
- No, this would be my first structured support

**GHL field name:** `fit_check_previous_experience`

---

### Question 4 — What Matters Most

**Label:** What feels most important to you in a coaching programme?

**Type:** Multiple choice (single select)

**Options:**
- Personalised to MY body, not a generic plan
- Someone in my corner daily
- Understanding the WHY behind my symptoms
- Flexibility around my real life

**GHL field name:** `fit_check_priority`

---

### Question 5 — Open Message (Optional)

**Label:** Is there anything you'd like Monika to know before you join?

**Type:** Short text field (optional)

**Placeholder text:** "Anything at all — no detail is too small."

**GHL field name:** `fit_check_message`

---

## Bridge Message (Shown After Submission)

Display this message on-screen immediately after the form is submitted, before redirecting to checkout:

> "Based on what you've shared, B.A.D. Premium sounds like a strong fit for where you are right now. Monika reviews every response personally. Here's how to secure your place 👇"

**Redirect:** After 3 seconds (or on button click) → Checkout Page

**Button label (optional):** "Secure your place →"

---

## GHL Build Notes

### Page Structure
- Build as a **multi-step funnel page** inside GHL — one question per step
- Mobile-first layout: large tap targets, minimal text, clear progress indicator
- Show a progress bar (e.g. "Step 2 of 5") on each question step

### Data Capture
- Capture each response as a **custom contact field** in GHL (field names listed above)
- Name and email must be collected either before Q1 or as part of the form (standard GHL opt-in step)
- All responses stored against the contact record for use in onboarding personalisation

### Tags
- Apply tag `Started Fit Check` when contact views the first question
- Apply tag `Completed Fit Check` on form submission

### Redirect Logic
- After submission, show bridge message for 3 seconds
- Auto-redirect to checkout page OR provide a button the contact can click to proceed immediately
- Do NOT redirect before bridge message is shown

### Personalisation Feed
- Responses to `fit_check_health_goal`, `fit_check_priority`, and `fit_check_message` should be visible to Monika inside the GHL contact record
- The onboarding survey and first 1:1 call agenda can be pre-populated using these responses

### Abandoned Fit Check
- If a contact starts but does not complete the fit check, apply tag `Started Fit Check` (not `Completed`)
- Optional: trigger a short re-engagement email/SMS after 24 hours ("Did something come up? You can pick up where you left off here.")
