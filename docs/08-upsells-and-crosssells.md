# Upsells & Cross-Sells — B.A.D. Premium Health Coaching (1:1)

## Ethics Rule

> **No upsells are sent before Month 1 is complete.**

All upsell and cross-sell offers are positioned as additions that support the member's existing work — never as replacements, and never with pressure.

---

## Upsells (Post-Join)

These are offers made to existing 1:1 members to deepen or expand their programme.

### 1. Blood Test Upgrade

| Attribute | Detail |
|---|---|
| **Price** | £184–£220 |
| **Best timing** | Month 1 / Onboarding (if not purchased at checkout) |
| **Trigger** | Not purchased at checkout, or re-offered based on ongoing symptoms |
| **What's included** | Hormone balance, thyroid, metabolic markers, nutrient status, inflammation, gut & liver health, cardiovascular risk |
| **Positioning** | "Get a biological snapshot so we can build your plan around real data, not guesswork." |

---

### 2. Bloods + Minutia.ai Deep Insight Package

| Attribute | Detail |
|---|---|
| **Price** | £349–£499 |
| **Best timing** | High-commitment members, chronic gut clients, or those who didn't accept the post-checkout upsell |
| **Trigger** | Persistent gut concerns, high engagement, or direct interest in deeper analysis |
| **What's included** | Full blood test panel + Minutia.ai gut simulation and microbiome analysis + personalised insights report interpreted by Monika |
| **Positioning** | "The deepest possible picture of your body — for those who want to leave nothing to guesswork." |

---

### 3. Personal Supplement Bundle

| Attribute | Detail |
|---|---|
| **Price** | £69–£149/month (recurring) |
| **Best timing** | Any 1:1 client from Month 1 onwards |
| **Trigger** | Stress or energy concerns flagged in surveys or check-ins |
| **What's included** | Tailored supplement stack designed around the member's specific symptom picture and what has been observed in coaching |
| **Positioning** | "A targeted stack — not a generic one. Built specifically around where you are right now." |

---

### 4. Deep-Dive Month

| Attribute | Detail |
|---|---|
| **Price** | +£70–£100 on top of current plan |
| **Best timing** | When a member hits a plateau or wants to accelerate progress |
| **Trigger** | Member flags feeling stuck, or Monika identifies a specific focus area |
| **What's included** | Elevated support for one month — additional 1:1 session, daily voice note check-ins, intensive protocol review |
| **Positioning** | "Sometimes you need to go deeper for one month to break through. This is that." |

---

### 5. Specialised Programme Upgrades

| Programme | Normal Price | Member Add-On Price |
|---|---|---|
| MenoBlast | £197 | £97 |
| Endo Reset | £197 | £97 |
| PCOS Programme | £197 | £97 |
| Hormone School | £197 | £97 |
| GLP-1 Course | £197 | £97 |

**Best timing:** Month 2+ when a specific condition or concern becomes a clear focus

**Trigger:** Survey responses, condition-specific keywords, member's own question or interest

**Positioning:** "Specialist education and protocol layered on top of your 1:1 work — half price as an existing member."

---

## Cross-Sells (Anytime)

These can be offered to any member at any point during their membership.

### 1. Minutia.ai Standalone Gut Simulation

| Attribute | Detail |
|---|---|
| **Price** | £199–£349 |
| **Trigger** | Persistent or complex gut symptoms |
| **Positioning** | "A deep map of your gut microbiome — without the full blood test package." |

---

### 2. Repeat Blood Testing Every 12 Weeks

| Attribute | Detail |
|---|---|
| **Price** | £150–£184 |
| **Trigger** | Member has completed initial blood test, 12 weeks of work done |
| **Positioning** | "Let's see what's actually moved inside. Your 12-week retest." |

---

### 3. Partner / Friend Add-On

| Attribute | Detail |
|---|---|
| **Price** | £79–£99/month |
| **Trigger** | Member mentions partner or friend wanting support |
| **Positioning** | "Add your partner or a friend to your membership for a fraction of the full price." |

---

### 4. Supplement Restocking Subscription

| Attribute | Detail |
|---|---|
| **Price** | £49–£129/month (auto-order) |
| **Trigger** | Member has been on a supplement protocol for 4+ weeks |
| **Positioning** | "Never run out — your supplements delivered automatically, adjusted as your protocol evolves." |

---

## Retention Offer

### Month 3 Loyalty Upgrade

| Attribute | Detail |
|---|---|
| **For** | Monthly plan members approaching or at Month 3 |
| **Offer** | Continue at £150/month for another 3 months (saves £30/month) |
| **Trigger** | 90 days after `1:1 Active` tag applied |
| **Workflow** | `1:1 Loyalty Retention — Month 3` |
| **Positioning** | "You've done the hard work of starting. Here's a thank-you for continuing — locked-in rate for the next 3 months." |

---

## Automation Triggers

| Trigger | Suggested Offer |
|---|---|
| Survey response: symptoms still present at Month 2 | Blood Test Upgrade |
| Survey response: gut concerns flagged | Microbiome Testing / Bloods + Minutia.ai |
| Survey response: low energy or stress ongoing | Supplement Bundle |
| Check-in: "I feel stuck" phrasing | Deep-Dive Month |
| Check-in: low energy score (e.g. 3/10 or below) | Supplement Bundle or Deep-Dive Month |
| Month 3 reached on monthly plan | Loyalty Retention Offer |
| 12 weeks since initial blood test | Repeat Blood Testing |
| Specific condition flagged (PCOS, endo, perimenopause etc.) | Relevant Specialised Programme |

> **Developer note:** These triggers can be set up in GHL using conditional logic on survey/form field responses, workflow conditions based on tags, and time-based delays. Work with Monika to define exact threshold values (e.g. energy score ≤ 3) before activating.

---

## GHL Workflow Reference

| Offer | Workflow Name | Trigger Type |
|---|---|---|
| Blood Test Upgrade | `1:1 Upsell — Blood Testing` | Survey condition |
| Bloods + Minutia.ai | `1:1 Upsell — Bloods Minutia` | Survey / engagement condition |
| Supplement Bundle | `1:1 Upsell — Supplements` | Survey condition |
| Deep-Dive Month | `1:1 Upsell — Deep Dive` | Survey / manual trigger |
| Specialised Programmes | `1:1 Upsell — Programmes` | Survey / condition / tag |
| Loyalty Retention | `1:1 Loyalty Retention — Month 3` | Time-based (Day 90) |
| Repeat Blood Testing | `1:1 Cross-Sell — Repeat Bloods` | Time-based (Day 84 post first test) |
