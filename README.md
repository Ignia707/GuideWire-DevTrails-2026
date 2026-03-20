# GuideWire-DevTrails-2026

# AI-Powered Parametric Income Insurance for Hyperlocal Delivery Workers

---

## The Problem

Chennai's hyperlocal delivery workers — serving Zomato, Swiggy, Zepto, Amazon, Dunzo, and others — are the invisible backbone of the city's daily life. Yet they bear the full financial impact of events entirely outside their control: cyclones, flash floods, extreme heat, political bandhs, and sudden zone lockdowns.

When the Northeast monsoon floods Velachery, or a cyclone warning shuts down the ECR corridor, a delivery worker loses an entire day's earnings — sometimes an entire week's. There is no safety net. No claim process. Just loss.

This platform changes that — a fully automated, zero-touch **parametric** income insurance system. Payouts are not based on what a worker actually lost; they are pre-defined, indexed to the **measured severity of the disruption itself**. If the city gets hit hard, the payout is larger. If it's a mild event, the payout is proportional. Automatically. Same day. No claims.

---

## Our Persona

**Who We Protect:** Hyperlocal delivery workers in Chennai operating across food delivery (Zomato, Swiggy), quick commerce (Zepto, Blinkit), e-commerce last mile (Amazon, Flipkart), and local courier services (Dunzo, Porter).

**Why Chennai?**
- One of India's most cyclone-prone coastal cities — the Northeast Monsoon (Oct–Dec) is a recurring, severe disruption cycle
- Notorious flood zones — Adyar, Tambaram, Velachery — with well-documented inundation histories
- Tamil Nadu's political climate makes bandhs and hartals a frequent income disruptor
- Extreme summer heat (Apr–Jun) regularly pushes temperatures beyond safe outdoor working conditions
- Dense pin-code level variation in risk — a worker in Velachery faces materially different exposure than one in Nungambakkam

**Explicit Exclusions:** Coverage does NOT include health, life, accidents, or vehicle repair costs. This platform insures **income disruption only**, triggered by measurable external parameters.

---

## Core Scenarios

### Scenario A — The Cyclone Week
*A worker delivers for Swiggy from Velachery. IMD issues a Red Alert cyclone warning for Chennai. Wind speeds are measured above the Severe Cyclonic Storm threshold. The trigger engine fires automatically. Within hours, the worker receives a payout indexed to that alert level — no paperwork, no waiting, no claim filed.*

### Scenario B — The Flood Zone
*A worker delivers for Zepto in Tambaram. IMD records rainfall in the "Very Heavy" band (115–204mm in 24 hours) for that zone. The system validates the parameter reading, confirms the worker's active zone, and initiates a payout proportional to that rainfall band — larger than it would have been for a merely "Heavy" rain event.*

### Scenario C — The Bandh
*A district-wide strike is confirmed with a few hours' notice. Major pickup zones are flagged inaccessible. Workers active in those zones receive a payout calibrated to the duration and geographic scope of the disruption — automatically, before the day ends.*

---

## Weekly Premium Model

### Philosophy
Gig workers earn weekly and spend weekly. The premium model is designed to match their cash flow — a weekly charge, never a lump-sum monthly bill. Pay once at the start of the week, covered for the full week.

### Dynamic Tiered Plans

Workers choose a coverage tier at onboarding. Each tier defines:
- Which disruption types are covered
- The worker's **weekly coverage sum** — the pre-agreed maximum payout pool for the week

This coverage sum is not a reimbursement of actual loss. It is the reference figure against which severity-band multipliers are applied when a trigger fires.

| Tier | Disruptions Covered |
|------|---------------------|
| Basic | Heavy rain, Cyclones |
| Standard | Rain, Cyclones, Extreme Heat, Severe AQI |
| Premium | All of the above + Bandhs and zone inaccessibility events |

### What Makes Premiums Dynamic

Premiums are recalculated every Sunday by the ML engine based on:

- **Zone Risk Score** — historical flood/disruption frequency per pin code
- **Seasonal Multiplier** — Oct–Dec Northeast Monsoon season carries higher baseline risk than the dry season
- **Worker Activity Score** — consistent activity history indicates a lower-risk profile
- **Streak Discount** — long-tenured subscribers pay progressively less (see Loyalty System)
- **Disruption Portfolio** — workers can add or remove specific disruption coverage as add-ons

```
Weekly Premium = Base Rate × Zone Risk Index × Seasonal Multiplier × (1 − Streak Discount) × Tier Multiplier
```

---

## Parametric Triggers & Severity Bands (Chennai-Specific)

This is the core of parametric insurance: the payout is not determined by what the worker lost — it is determined by **how severe the measured event was**. Every trigger has defined severity bands with corresponding payout multipliers applied to the worker's pre-agreed coverage sum.

### Rainfall (IMD Classification)

| Band | Rainfall in 24h | Payout Multiplier |
|------|----------------|-------------------|
| Heavy Rain | 64.5–115.5 mm | 0.4× coverage sum |
| Very Heavy Rain | 115.6–204.4 mm | 0.7× coverage sum |
| Extremely Heavy Rain | ≥ 204.5 mm | 1.0× coverage sum |

### Cyclone Alert (IMD Wind Speed Classification)

| Band | Alert Level | Payout Multiplier |
|------|------------|-------------------|
| Cyclonic Storm | Orange Alert | 0.5× coverage sum |
| Severe Cyclonic Storm | Red Alert | 0.8× coverage sum |
| Very Severe / Extremely Severe | Red + Special Bulletin | 1.0× coverage sum |

### Heat Event

| Band | Condition | Payout Multiplier |
|------|-----------|-------------------|
| Heat Wave | ≥ 40°C departure from normal by ≥ 4.5°C | 0.3× coverage sum |
| Severe Heat Wave | ≥ 45°C or departure ≥ 6.5°C | 0.6× coverage sum |

### Air Quality (CPCB AQI)

| Band | AQI Range | Payout Multiplier |
|------|-----------|-------------------|
| Very Poor | 301–400 | 0.3× coverage sum |
| Severe | 401–500 | 0.6× coverage sum |

### Social Disruption (Bandh / Zone Lockdown) — Premium Tier Only

Payout is proportional to the confirmed duration and geographic scope of the disruption, validated through government notification feeds and NLP-based news scanning. Partial-day and zone-limited events yield prorated multipliers.

---

Every trigger requires **confirmation from two independent data sources** before any payout is initiated.

---

## Zero-Touch Automated Payout System

The worker never files a claim.

```
External Disruption Occurs
         ↓
Trigger Engine polls APIs every 30 minutes
         ↓
Parameter threshold crossed (primary source)
         ↓
Cross-validate with secondary data source
         ↓
Determine severity band → compute payout multiplier
         ↓
Identify affected zones → match to active subscribers in zone
         ↓
Fraud validation layer (ML)
         ↓
Payout = Coverage Sum × Severity Band Multiplier
         ↓
Instant disbursement via UPI / Razorpay
         ↓
Worker notified via SMS + push notification
```

**Payout Speed:** Same-day, within a few hours of trigger confirmation.

**Coverage Sum Baseline:** Set at onboarding based on self-reported weekly earnings, cross-validated against platform activity data. Recalibrated periodically to reflect actual income levels.

---

## Streak & Loyalty System

### Abuse Prevention: Gradual Coverage Unlock

To prevent opportunistic subscriptions — workers buying only in the week before the monsoon — coverage unlocks **gradually based on subscription tenure**:

| Subscription Duration | Coverage Available |
|----------------------|--------------------|
| Week 1–2 | None — waiting period |
| Week 3–4 | 40% of tier coverage |
| Week 5–8 | 70% of tier coverage |
| Week 9–12 | 90% of tier coverage |
| Week 13 onwards | Full coverage |

New subscribers during peak cyclone months face this standard waiting period regardless of timing.

### Shield Levels (Streak)

Every consecutive week of active subscription builds a streak, unlocking progressively better terms:

| Level | Streak Required | Benefit |
|-------|-----------------|---------|
| Bronze | 4 weeks | Small premium discount |
| Silver | 12 weeks | Larger discount + priority same-hour payouts |
| Gold | 24 weeks | Significant discount + extended daily coverage window |
| Platinum | 52 weeks | Maximum discount + periodic loyalty bonus payout |

Missing a weekly payment drops the subscriber one level, not to zero — streak is partially preserved.

### No-Claim Loyalty Bonus

Workers who go extended periods without a triggered payout (dry seasons, low-risk zones) are rewarded to ensure year-round subscription remains worthwhile:

- **~2 months** without a claim → incremental premium reduction
- **~3 months** without a claim → loyalty credits added to wallet
- **~4 months** without a claim → one free tier-upgrade week

This ensures that workers in lower-risk areas are not penalised for subscribing consistently.

### Loyalty Credits
- Earned through streak milestones, no-claim bonuses, and referrals
- Redeemable against weekly premiums, tier upgrades, or UPI cashback
- Expire after a period of subscription inactivity

---

## AI / ML Integration

### 1. Dynamic Premium Engine
- **Model:** Gradient Boosted Regressor (XGBoost)
- **Inputs:** Zone-level historical disruption frequency, IMD seasonal patterns, worker activity scores, subscriber cohort risk profiles
- **Output:** Personalised weekly premium per subscriber, recalculated every Sunday

### 2. Coverage Sum Validation Model
- Establishes each worker's credible income baseline at onboarding
- Cross-validated using platform delivery activity signals
- Periodically recalibrated to reflect actual earnings trends
- Prevents inflated coverage sum declarations that would lead to disproportionate payouts

### 3. Disruption Forecast ("Storm Watch")
- ML model trained on IMD historical records predicts high-risk periods several days ahead
- Workers receive proactive alerts advising on coverage adequacy for the coming week
- Insurer dashboard receives next-week predicted payout volume for reserve management

### 4. Hyper-Local Risk Zone Maps
- Pin-code level disruption risk scores across Chennai
- Updated regularly using IMD data, municipal waterlogging history, and historical trigger events
- Used for both premium calculation and trigger zone boundary validation

### 5. Fraud Detection — Multi-Layer

| Layer | Method |
|-------|--------|
| Trigger Validation | Every payout requires confirmation from 2+ independent data sources |
| Location Consistency | Worker's last recorded GPS zone must fall within the triggered disruption zone |
| Activity Anomaly Detection | ML flags workers whose app activity drops abnormally without a confirmed parametric event |
| Cluster Analysis | Flags statistically anomalous payout concentrations in a single micro-zone |
| Subscription Timing Analysis | Rapid new subscriber cohorts ahead of historically high-risk periods are flagged for extended waiting |
| Coverage Sum Inflation Detection | Declared income baseline cross-checked against platform activity history |

---

## Platform

**Mobile-First** (workers are always on the move) with a **Web Admin Dashboard** for insurers.

- **Worker App (React Native):** Onboarding, plan selection, streak tracker, payout history, disruption alerts, loyalty credits wallet
- **Insurer Dashboard (React.js):** Live trigger map, payout volumes, fraud flags, loss ratios, predictive analytics for upcoming risk periods

---

## Tech Stack

| Layer | Technology |
|-------|------------|
| Backend API | Node.js (Express) |
| AI / ML Service | Python + FastAPI |
| Worker Mobile App | React Native |
| Admin Dashboard | React.js |
| Database | PostgreSQL + Redis (task queues + caching) |
| ML Models | scikit-learn, XGBoost, pandas |
| Trigger Engine | Bull (Node.js queue) + Redis |
| Weather Data | OpenWeatherMap API + IMD mock feeds |
| Air Quality | CPCB AQI API (mock) |
| Zone / Traffic Data | OpenStreetMap + Google Maps API (mock) |
| Payments | Razorpay Sandbox / UPI Simulator |
| Notifications | Firebase Cloud Messaging (FCM) |
| Hosting | AWS / GCP free tier |

---

## Development Plan

### Phase 1 — Ideation & Foundation (March 4–20) ✓
- [x] Define Chennai-specific parametric trigger parameters and severity bands
- [x] Design weekly dynamic premium model and tier structure
- [x] Design streak/loyalty and coverage unlock system
- [x] Define fraud detection architecture
- [ ] Set up GitHub repository and project structure
- [ ] Build onboarding flow wireframes (Figma)
- [ ] Prototype ML risk scoring model (baseline)
- [ ] Integrate and test OpenWeatherMap API

### Phase 2 — Automation & Protection (March 21 – April 4)
- Worker registration, KYC, and onboarding flow
- Policy management module
- Dynamic premium calculation engine (ML v1)
- 3–5 live parametric trigger integrations with severity band detection
- Zero-touch automated payout engine
- Fraud detection layers 1–3 (trigger validation, location consistency, anomaly)

### Phase 3 — Scale & Optimise (April 5–17)
- Advanced fraud detection (subscription timing analysis, coverage sum inflation, cluster analysis)
- Instant payout via Razorpay sandbox / UPI simulator
- Worker dashboard: active coverage, streak level, payout history, loyalty credits
- Insurer dashboard: loss ratios, trigger heatmap, next-week risk prediction
- Full demo: simulated cyclone trigger → severity band detected → automated payout
- Final pitch deck and 5-minute demo video

---

## This Platform vs Traditional Insurance

| Dimension | Traditional Insurance | This Platform |
|-----------|----------------------|---------------|
| Claims process | Manual, days to weeks | Zero-touch, automated |
| Payout basis | Actual loss verified | Parameter magnitude (pre-defined) |
| Pricing model | Annual/monthly, fixed | Weekly, dynamic, personalised |
| Payout speed | Days to weeks | Same day |
| Fraud prevention | Manual review | ML-driven, multi-layer |
| Long-term loyalty | None | Streak discounts + no-claim bonuses |
| Abuse prevention | Exclusion clauses | Gradual coverage unlock model |
| Relevant to gig workers | Rarely | Built entirely for them |

---

## Team

Team Name: Beetlejuice

Members:
- Varsha A
- Subrajith R
- Ramana KS
- Prem Danasekaran
- Nikhilesh H

## Demo Video

*[2-minute strategy + prototype walkthrough video link to be added]*

---
