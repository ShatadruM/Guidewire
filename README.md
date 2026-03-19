<div align="center">

#  ParaGuard

### AI-Powered Parametric Insurance for India's Gig Economy

*Zero-touch income protection for delivery riders — automated triggers, instant payouts, no paperwork.*


</div>

---

## 📋 Table of Contents

- [The Problem](#-the-problem)
- [Market Size](#-market-size)
- [Target Persona](#-target-persona--q-commerce-rider)
- [Disruption Data](#-disruption-data)
- [How ParaGuard Works](#-how-paraguard-works)
- [Financial Model](#-financial-model)
  - [The 3 Weekly Plans](#the-3-weekly-plans)
  - [All 52 Weeks Priced](#all-52-weeks-priced--safeweek-pro)
  - [City × Month Pricing Matrix](#city--month-pricing-matrix)
  - [Weekly P&L](#weekly-pl--at-25-lakh-workers)
  - [3-Year P&L](#3-year-profit--loss)
  - [Insurance Scale Scenarios](#insurance-profit-model--3-scenarios)
  - [App Build Costs](#app-build-cost-breakdown)
  - [Regulatory Path](#regulatory-path)
- [Go-to-Market Strategy](#-go-to-market-strategy)
- [Technical Architecture](#-technical-architecture)
- [AI / ML Integration](#-aiml-integration)
- [Tech Stack](#-tech-stack)
- [Microservice File Structures](#-microservice-file-structures)
- [Summary](#-summary)

---

## ❗ The Problem

India's platform-based delivery partners (Zomato, Swiggy, Zepto, Blinkit, Amazon, Dunzo, Porter) are the backbone of our fast-paced digital economy.

External disruptions — **extreme weather, pollution, and natural disasters** — can reduce their working hours and cause them to lose **20–30% of their monthly earnings**. Currently, gig workers have **no income protection** against these uncontrollable events.

> When disruptions occur, workers bear the full financial loss with no safety net. ParaGuard changes that with automated, zero-touch parametric insurance.

### Disruption Types Covered

| Type | Examples | Trigger Source | Income Impact |
|------|----------|---------------|---------------|
| 🌡️ **Environmental — Heat** | Temperature >44°C for 3+ days | IMD API | 25–40% weekly loss |
| 🌧️ **Environmental — Floods** | Rainfall >50mm/day, waterlogging | IMD / OpenWeather | 30–50% weekly loss |
| 🌫️ **Environmental — Pollution** | AQI >300 (Severe) | CPCB API | 15–25% weekly loss |
| 🌀 **Environmental — Cyclone** | IMD cyclone warning issued | NDMA Alerts | 50–100% for 2–5 days |
| 🚫 **Social — Curfew** | Section 144, emergency order | District admin | 100% while in effect |
| 🛑 **Social — Strike / Bandh** | Market closures, transport strikes | News API / manual | 50–100% loss |

> ⚠️ **Coverage scope:** Loss of income **only**. ParaGuard does **not** cover health, life, accidents, or vehicle repairs.

---

## 📊 Market Size

| Segment | Worker Count | Key Platforms | Avg Weekly Income |
|---------|-------------|---------------|-------------------|
| Total gig workers (India 2025) | ~1.12 Cr (11.2M) | All platforms | ₹3,000–6,500 |
| Platform delivery workers | **~35 Lakh** | Zomato, Swiggy, Blinkit, Zepto, Amazon | ₹3,500–6,000 |
| Food delivery riders | ~15.85 Lakh active/month | Zomato 8.94L · Swiggy 6.91L | ₹4,500–6,500 |
| **Q-Commerce (target) ★** | **~9 Lakh** | Blinkit 3.5L · Zepto 2.5L · Instamart 2L | ₹3,500–5,500 |
| E-Commerce & Logistics | ~7 Lakh | Amazon 2.5L · Flipkart 2L · Porter 1.5L | ₹3,000–5,000 |
| Workers earning <₹2.5L/yr | **77.6%** of all gig workers | Borzo survey, 40 cities 2025 | — |

### Platform-wise Worker Breakdown

| Platform | Segment | Est. Active Workers | Avg Weekly Gross | Avg Weekly Net | Peak Risk |
|----------|---------|-------------------|-----------------|----------------|-----------|
| Zomato | Food delivery | **8.94 Lakh** (Q3 FY25) | ₹5,000–6,500 | ₹3,800–5,000 | 🔴 Very High |
| Swiggy | Food delivery | **6.91 Lakh** (Q3 FY25) | ₹4,500–6,000 | ₹3,500–4,600 | 🔴 Very High |
| Blinkit (Zomato) | Q-Commerce | ~3.5 Lakh | ₹4,200–5,500 | ₹3,200–4,200 | 🔴 Very High |
| Zepto | Q-Commerce | ~2.5 Lakh | ₹3,800–5,000 | ₹2,900–3,800 | 🔴 Very High |
| Swiggy Instamart | Q-Commerce | ~2 Lakh | ₹3,500–4,800 | ₹2,700–3,700 | 🔴 Very High |
| Amazon Flex/Now | E-Commerce | ~2.5 Lakh | ₹3,500–5,000 | ₹2,700–3,800 | 🟠 Medium-High |
| Flipkart (Ekart) | E-Commerce | ~2 Lakh | ₹3,200–4,500 | ₹2,500–3,500 | 🟡 Medium |
| Porter | Logistics | ~1.5 Lakh | ₹3,500–5,500 | ₹2,600–4,200 | 🟠 High |
| Rapido (packages) | Logistics | ~1 Lakh | ₹3,000–4,500 | ₹2,300–3,500 | 🟠 High |
| BigBasket Now | Q-Commerce | ~60,000 | ₹3,200–4,200 | ₹2,500–3,200 | 🟠 Medium-High |
| Dunzo | Food/Q-Commerce | ~40,000 | ₹3,800–5,000 | ₹2,900–3,800 | 🟡 Medium |
| **TOTAL** | | **~35 Lakh** | | | |

---

## 👤 Target Persona — Q-Commerce Rider

ParaGuard's primary persona is the **Q-Commerce delivery rider** — working for Blinkit, Zepto, or Swiggy Instamart on 10-minute delivery SLAs. These riders face the **highest disruption sensitivity** of any delivery segment.

| Profile Dimension | Details |
|-------------------|---------|
| Platform | Blinkit / Zepto / Swiggy Instamart |
| Work hours | 8–12 hrs/day, 6–7 days/week |
| Avg gross monthly income | ₹18,000–22,000 |
| Avg net take-home (after fuel) | ₹14,000–18,000 |
| Avg weekly gross income | ₹4,500–5,500 |
| Orders per day | 15–20 deliveries |
| Income at risk per disruption month | ₹2,800–4,500 (20–30%) |
| Disrupted days per year | 25–40 days |
| Why highest risk | 10-min SLAs mean any rain/heat immediately kills order volume AND makes riding dangerous |

### Three Sub-Personas

| Tier | Segment | Platforms | Weekly Net | Risk | Insurance Value |
|------|---------|-----------|-----------|------|----------------|
| Tier 1 | Food Delivery | Zomato, Swiggy, Dunzo | ₹3,500–5,000 | Very High | High |
| **Tier 2 ★** | **Q-Commerce (chosen)** | Blinkit, Zepto, Instamart | ₹3,200–4,200 | Very High | **Highest** |
| Tier 3 | E-Commerce & Logistics | Amazon, Porter, Flipkart | ₹2,700–4,200 | Medium–High | Medium |

### Real Rider Examples

**🧑 Ravi — Zomato Rider, Delhi NCR**
> Ravi earns ₹5,200/week gross. During a June heatwave (IMD declares 44°C+ for 4 days), order volume drops 40%. His app shows only 9 orders over 3 days vs his usual 21. Without insurance he loses ₹1,400. With **SafeWeek Pro at ₹69/week**, the parametric trigger fires automatically and he receives **₹1,200 to his UPI within 24 hours**. Net benefit: ₹1,131.

**👩 Kavitha — Zepto Rider, Chennai**
> During a Cyclone Michaung-type event, all zones shut for 4 days. IMD issues Red Alert — ParaGuard fires city-wide for all enrolled Zepto riders. Kavitha receives **₹1,050 same day**. Monthly premium paid: ₹188. One payout covers 5 months of premiums.

**🧑 Mehul — Blinkit Rider, Ahmedabad**
> In May, 5 days over 45°C trigger two payout events totalling ₹2,300. Total May–June premiums paid: ₹400. **Net benefit: ₹1,900 over 8 weeks.**

---

## 📈 Disruption Data

| Metric | Data Point | Source |
|--------|-----------|--------|
| Workers reporting heat exhaustion (2024) | **52%** of surveyed gig workers | TGPWU / HeatWatch 2024 |
| Supply drop in peak summer (May–Jul) | **~20%** fewer active riders | Platform data estimates |
| Extreme heat days per year (2024) | **~20 days**; 37 cities crossed 45°C | IMD 2024 |
| Productivity drop on hot days | **25–40%** fewer orders completed | NCAER / field surveys |
| Total disrupted workdays per year (Delhi/Mumbai) | **35–55 days** | IMD + CPCB historical |
| Monthly income loss per disruption event | **₹2,800–6,000** (20–30% of monthly) | Calculated from earnings data |
| Workers with zero income protection | **~100%** of gig workers | No existing product covers this |

### Monthly Disruption Calendar

| Month | Primary Disruption | Affected Cities | Disrupted Days | Risk | Claim Probability |
|-------|--------------------|----------------|---------------|------|-------------------|
| January | Dense fog (North) | Delhi, Lucknow, Jaipur | 3–5 days | 🟡 Medium | 15–20% |
| February | None significant | None | 0–1 days | 🟢 Low | 3–5% |
| March | Pre-summer heat (West) | Ahmedabad, Rajasthan | 0–2 days | 🟢 Low | 5–10% |
| April | Heat building, dust storms | Delhi, Jaipur, Ahmedabad | 3–6 days | 🟡 Medium | 15–25% |
| **May** | **Peak heatwave (national)** | Delhi, Ahmedabad, Jaipur, Hyderabad | **8–12 days** | 🔴 Very High | **55–70%** |
| **June** | **Heat + monsoon onset** | All major cities (double risk) | **7–10 days** | 🔴 Very High | **60–75%** |
| July | Peak monsoon flooding | Mumbai, Chennai, Kolkata, Pune | 6–9 days | 🟠 High | 40–55% |
| August | Heavy rain, flooding | Mumbai, Kolkata, Hyderabad | 5–8 days | 🟠 High | 35–50% |
| September | Residual monsoon, cyclone watch | East coast, Kerala | 3–5 days | 🟡 Medium | 15–25% |
| October | NE monsoon (South), Delhi smog | Chennai, Delhi NCR | 4–7 days | 🟠 High | 30–45% |
| November | Severe smog (North), cyclones (East) | Delhi NCR (AQI 400+), Kolkata | 5–8 days | 🟠 High | 35–50% |
| December | Fog, cold (North), NE monsoon tail | Delhi, Lucknow, Chennai | 3–5 days | 🟡 Medium | 15–20% |

---

## ⚙️ How ParaGuard Works

```
1. ONBOARDING        → Rider connects platform ID · AI calculates Average Weekly Wage
        ↓
2. WEEKLY PLAN       → Pays dynamic premium every Sunday for coverage next week
        ↓
3. REAL-TIME MONITOR → System polls IMD · CPCB · NDMA APIs for rider's geo-fenced area
        ↓
4. AUTO-CLAIM        → Disruption detected → claim initiated automatically (no manual filing)
        ↓
5. AI VERIFICATION   → Fraud model checks GPS · zone presence · activity drop · duplicates
        ↓
6. INSTANT PAYOUT    → Funds disbursed to UPI/wallet same day (Lite: next day · Max: instant)
```

### The Sunday 8pm Automated Pricing Flow

Every Sunday at 8pm the AI pricing engine runs automatically:

| Step | Action | System | Output |
|------|--------|--------|--------|
| 1 | Poll 7-day weather forecast for all 10 cities | Monitor Service (cron) | Temperature, rainfall forecasts |
| 2 | Poll AQI forecast | Monitor Service | Air Quality Index by city |
| 3 | Check disaster / cyclone alerts | Monitor Service | Active NDMA warnings |
| 4 | Run risk tier classification | Claims AI (Python) | Low / Med / High / Very High per city |
| 5 | Calculate premium per plan per city | Policy Service (Java) | ₹ amount for each plan × city |
| 6 | Update all active weekly policies | Policy Service | PostgreSQL records updated |
| 7 | Push notification to enrolled workers | User Service (Node.js) | "Next week: High risk. Your premium: ₹55" |
| 8 | Auto-deduct from platform payout (partner cities) | Payment Service | Premium collected, policy active |

### Parametric Trigger → Payout Flow

| Step | Action | Threshold / Logic |
|------|--------|-------------------|
| 1 | Weather threshold crossed in geo-fenced zone | Temp >44°C OR Rain >50mm/day OR AQI >300 OR Red Alert |
| 2 | Disruption event broadcast via message queue | `{ city, zone, type, severity, timestamp }` |
| 3 | Claims AI validates rider presence in affected zone | GPS cross-check: rider within geo-fence during disruption |
| 4 | Activity validation: was rider unable to work? | Order count drop >30% vs 30-day rolling average = validated |
| 5 | Fraud score generated | GPS spoof + activity anomaly + duplicate detection (0–1 score) |
| 6 | Auto-approve if fraud score < 0.3 | ~85% of claims — payout calculated from policy tier |
| 7 | Manual review if score 0.3–0.7 | Ops team reviews within 4 hours (~12% of claims) |
| 8 | Auto-reject if score > 0.7 | Worker notified, appeal available (~3% of claims) |
| 9 | Instant payout to UPI/wallet | Lite: next day · Pro: same day · Max: instant |

---

## 💰 Financial Model

### Weekly Pricing Philosophy

> **Weekly Price = Base Rate × City Multiplier × Week Risk Factor × Plan Multiplier**

Every single week must be independently profitable. The price each week reflects actual risk — not a blended annual average.

### Weekly Risk Tiers

| Risk Tier | Weeks/Year | Risk Factor | Trigger Condition | Months | Pro Price/Wk |
|-----------|-----------|------------|-------------------|--------|-------------|
| 🔴 Very High | 6 weeks | 1.77× | IMD Red Alert / Temp >44°C 3+ days / Cyclone | May–Jun peak | **₹69** |
| 🟠 High | 14 weeks | 1.41× | IMD Orange Alert / Rain >50mm / AQI >300 | Jun–Aug, Oct–Nov | **₹55** |
| 🟡 Medium | 16 weeks | 1.15× | IMD Yellow Alert / Seasonal elevated risk | Apr, Sep, Nov, Dec | **₹45** |
| 🟢 Low | 16 weeks | 1.00× | No active alerts — baseline historical risk | Jan, Feb, Mar, Dec | **₹39** |

### City Risk Multipliers

| City | Multiplier | Risk Tier | Est. Workers | Annual Premium (Pro) | Primary Disruptions |
|------|-----------|----------|-------------|---------------------|---------------------|
| Delhi NCR | 1.15× | 🔴 Very High | ~5.5 Lakh | ₹2,156 | Heat 45°C+, floods, smog AQI 400+ |
| Mumbai | 1.10× | 🔴 Very High | ~4.8 Lakh | ₹2,028 | Monsoon flooding, humidity |
| Bengaluru | 1.00× | 🟡 Medium | ~4.2 Lakh | ₹1,744 | Rain, urban flooding |
| Hyderabad | 1.08× | 🟠 High | ~2.8 Lakh | ₹1,964 | Extreme heat, flash floods |
| Chennai | 1.10× | 🟠 High | ~2.5 Lakh | ₹2,160 | Cyclones, NE monsoon |
| Pune | 1.00× | 🟡 Medium | ~1.8 Lakh | ₹1,756 | Monsoon, heat Apr–Jun |
| Kolkata | 1.05× | 🟠 High | ~1.7 Lakh | ₹2,004 | Monsoon, cyclones, heat |
| Ahmedabad | 1.12× | 🔴 Very High | ~1.2 Lakh | ₹1,988 | Extreme heat 47°C+, hot winds |
| Jaipur | 1.08× | 🟠 High | ~0.7 Lakh | ₹1,968 | Heat, dust storms |
| Lucknow | 1.00× | 🟡 Medium | ~0.6 Lakh | ₹1,832 | Heat, winter fog |

---

### The 3 Weekly Plans

| Feature | SafeWeek Lite | SafeWeek Pro ⭐ | SafeWeek Max |
|---------|--------------|----------------|--------------|
| Low risk week (16 wks) | ₹29/wk | ₹39/wk | ₹55/wk |
| Medium risk week (16 wks) | ₹35/wk | ₹45/wk | ₹65/wk |
| High risk week (14 wks) | ₹45/wk | ₹55/wk | ₹79/wk |
| Very high risk week (6 wks) | ₹49/wk | ₹69/wk | ₹99/wk |
| **Annual total (52 weeks)** | **₹1,724** | **₹2,184** | **₹3,148** |
| Max weekly payout | ₹700 | ₹1,200 | ₹2,000 |
| Trigger threshold | 3+ disrupted days | 2+ disrupted days | 1+ disrupted day |
| Max payouts/month | 1 event | 2 events | 3 events |
| Max annual payout | ₹8,400 | ₹24,000 | ₹48,000 |
| Monthly premium cap | ₹160 | **₹220** | ₹340 |
| Payout speed | Next day — UPI | Same day — UPI | Instant — UPI/wallet |
| Target worker income | <₹12K/month | ₹12K–25K/month | >₹25K/month |
| Expected plan mix | 20% | **65%** | 15% |

---

### All 52 Weeks Priced — SafeWeek Pro

| Weeks | Period | Risk Tier | Price/Week | Reason | Sub-total |
|-------|--------|----------|-----------|--------|-----------|
| Wk 1–3 | Early January | 🟢 Low | ₹39 | Mild weather, post-festival lull | ₹117 |
| Wk 4 | Late January | 🟡 Medium | ₹45 | Dense fog in North India | ₹45 |
| Wk 5–8 | February | 🟢 Low | ₹39 | Best month — pleasant across India | ₹156 |
| Wk 9–11 | Early–Mid March | 🟢 Low | ₹39 | Mild, minimal disruption | ₹117 |
| Wk 12 | Late March | 🟡 Medium | ₹45 | Pre-summer heat starts in West India | ₹45 |
| Wk 13–15 | April (most) | 🟡 Medium | ₹45 | Heat building in Delhi, Rajasthan, Gujarat | ₹135 |
| Wk 16 | Late April | 🟠 High | ₹55 | Heatwave begins in North/West | ₹55 |
| Wk 17 | Early May | 🟠 High | ₹55 | Heat spreading nationally | ₹55 |
| **Wk 18–21** | **May peak + early Jun** | **🔴 Very High** | **₹69** | Peak heatwave 44–47°C North/West | **₹276** |
| **Wk 22** | **Mid June** | **🔴 Very High** | **₹69** | Heat + monsoon onset — double risk | **₹69** |
| Wk 23–24 | Late June | 🟠 High | ₹55 | Monsoon active — Mumbai/coastal flooding | ₹110 |
| Wk 25–30 | July – early August | 🟠 High | ₹55 | Peak monsoon — Mumbai, Chennai, Kolkata | ₹330 |
| Wk 31 | Late August | 🟡 Medium | ₹45 | Monsoon weakening | ₹45 |
| Wk 32–33 | Early–Mid September | 🟡 Medium | ₹45 | Residual rain + cyclone watch | ₹90 |
| Wk 34–35 | Late September | 🟢 Low | ₹39 | Monsoon retreating, pleasant | ₹78 |
| Wk 36–38 | October (most) | 🟡 Medium | ₹45 | NE monsoon (Chennai), Delhi smog starting | ₹135 |
| Wk 39 | Late October | 🟠 High | ₹55 | Cyclone season peak, smog worsens | ₹55 |
| Wk 40–41 | November (smog) | 🟠 High | ₹55 | Delhi AQI 400+, East coast cyclones | ₹110 |
| Wk 42–43 | November (later) | 🟡 Medium | ₹45 | Smog reducing, post-cyclone | ₹90 |
| Wk 44–46 | Early–Mid December | 🟢 Low | ₹39 | Pleasant, good riding weather | ₹117 |
| Wk 47 | Mid December | 🟡 Medium | ₹45 | Dense fog begins in North India | ₹45 |
| Wk 48–50 | Late December | 🟢 Low | ₹39 | Festive, mild | ₹117 |
| Wk 51 | Year-end | 🟡 Medium | ₹45 | Fog + cold in North | ₹45 |
| Wk 52 | Final week | 🟢 Low | ₹39 | New Year — low disruption | ₹39 |
| | | | | **Annual Total** | **₹2,184** |

> 📊 **Blended average: ₹42/week · Lowest week: ₹39 (Feb) · Highest week: ₹69 (May peak)**

---

### City × Month Pricing Matrix

> Monthly premium (₹) for SafeWeek Pro. Divide by 4 for weekly equivalent.

| City | Jan | Feb | Mar | Apr | May | Jun | Jul | Aug | Sep | Oct | Nov | Dec | **Annual** |
|------|-----|-----|-----|-----|-----|-----|-----|-----|-----|-----|-----|-----|-----------|
| Delhi NCR | 148 | 112 | 120 | 160 | **260** | **248** | 200 | 192 | 148 | 196 | 216 | 156 | **₹2,156** |
| Mumbai | 120 | 108 | 116 | 148 | 200 | **260** | **256** | **248** | 160 | 152 | 140 | 120 | **₹2,028** |
| Bengaluru | 108 | 100 | 108 | 140 | 156 | 188 | 196 | 188 | 148 | 152 | 148 | 112 | **₹1,744** |
| Hyderabad | 116 | 108 | 132 | 188 | **244** | 216 | 200 | 196 | 156 | 148 | 140 | 120 | **₹1,964** |
| Chennai | 140 | 108 | 116 | 148 | 196 | 188 | 196 | 200 | 188 | **236** | **248** | 196 | **₹2,160** |
| Pune | 108 | 100 | 108 | 140 | 188 | 196 | 200 | 188 | 148 | 140 | 132 | 108 | **₹1,756** |
| Kolkata | 120 | 108 | 116 | 148 | 196 | 200 | **244** | **236** | 160 | 188 | 156 | 132 | **₹2,004** |
| Ahmedabad | 116 | 108 | 132 | 196 | **260** | **252** | 200 | 188 | 148 | 140 | 132 | 116 | **₹1,988** |
| Jaipur | 140 | 108 | 132 | 188 | **252** | 220 | 196 | 188 | 140 | 132 | 132 | 140 | **₹1,968** |
| Lucknow | 140 | 100 | 108 | 148 | 196 | 188 | 172 | 164 | 132 | 148 | 188 | 148 | **₹1,832** |

---

### Weekly P&L — At 2.5 Lakh Workers

> Every single week type is independently profitable — the model never relies on good months to subsidise bad months.

| Week Type | Price/Wk | Premium Revenue | Claims Paid | Reinsurance (15%) | **Net/Week** | **Margin %** |
|-----------|---------|----------------|------------|------------------|-------------|-------------|
| 🟢 Low risk (16 wks) | ₹39 | ₹97.5L | ₹25L | ₹14.6L | **₹57.9L** | **59.4%** |
| 🟡 Medium risk (16 wks) | ₹45 | ₹112.5L | ₹60L | ₹16.9L | **₹35.6L** | **31.6%** |
| 🟠 High risk (14 wks) | ₹55 | ₹137.5L | ₹95L | ₹20.6L | **₹21.9L** | **15.9%** |
| 🔴 Very high risk (6 wks) | ₹69 | ₹172.5L | ₹130L | ₹25.9L | **₹16.6L** | **9.6%** |
| **Weighted avg (52 wks)** | **₹42** | **₹115L/wk** | **₹66L/wk** | **₹17.3L/wk** | **₹31.7L/wk** | **27.6%** |

> ✅ Even in the worst Very High risk week, you make ₹16.6 Lakh net on 2.5L workers (9.6% margin).

---

### 3-Year Profit & Loss

| P&L Line Item | Year 1 | Year 2 | Year 3 |
|---------------|--------|--------|--------|
| **Workers enrolled** | 50,000 | 2,50,000 | 8,00,000 |
| | | | |
| **REVENUE** | | | |
| Gross premium collected | +₹77L | +₹572L | +₹1,914L |
| | | | |
| **COST OF INSURANCE** | | | |
| Claims paid to workers | −₹42L | −₹210L | −₹650L |
| Reinsurance premium (15%→12% at Y3) | −₹11.6L | −₹85.8L | −₹229.6L |
| **Gross underwriting profit** | **₹23.4L (30.4%)** | **₹276.2L (48.3%)** | **₹1,034.4L (54%)** |
| | | | |
| **APP & TECHNOLOGY** | | | |
| App build / MVP development | −₹28L | −₹5L | −₹5L |
| AI / ML risk + fraud engine | −₹18L | −₹8L | −₹10L |
| UI/UX, QA, security audit | −₹14L | −₹3L | −₹3L |
| Cloud infrastructure (AWS/GCP) | −₹5L | −₹18L | −₹40L |
| API integrations + admin panel | −₹10L | −₹6.5L | −₹7L |
| **Total tech** | **−₹75L (97.4%)** | **−₹40.5L (7.1%)** | **−₹65L (3.4%)** |
| | | | |
| **REGULATORY & COMPLIANCE** | | | |
| IRDAI broker license + filing | −₹5L | −₹0.5L | −₹0.5L |
| Regulatory capital *(blocked, not burned)* | −₹75L | — | — |
| Compliance officer + legal + audits | −₹19.1L | −₹18L | −₹23.5L |
| **Total regulatory** | **−₹99.1L** | **−₹18.5L** | **−₹24L** |
| | | | |
| **PEOPLE & OPERATIONS** | | | |
| Engineering + product team salaries | −₹42L | −₹90L | −₹216L |
| Customer support + office + misc | −₹23.1L | −₹33L | −₹66L |
| **Total opex** | **−₹65.1L** | **−₹123L** | **−₹282L** |
| | | | |
| **SALES & MARKETING** | | | |
| CAC per worker | ₹180 | ₹140 | ₹80 |
| Total CAC spend | −₹90L | −₹280L | −₹440L |
| Marketing + partnerships | −₹23L | −₹25L | −₹20L |
| **Total sales & marketing** | **−₹113L** | **−₹305L** | **−₹460L** |
| | | | |
| **NET PROFIT / (LOSS)** | **🔴 −₹3.24 Cr** | **🟡 −₹1.94 Cr** | **🟢 +₹2.27 Cr** |
| Net margin | — | — | **11.9%** |
| Cumulative cash position | −₹3.24 Cr | −₹5.18 Cr | −₹2.91 Cr |

> 📌 **Break-even: Month ~26 (Q2 Year 3)** · **Seed required: ₹4–5 Cr** · **Real cash burn Y1: ~₹2.5 Cr** *(₹75L regulatory capital stays on balance sheet)*

---

### Insurance Profit Model — 3 Scenarios

| Metric | Conservative | Base Case | Aggressive |
|--------|-------------|-----------|-----------|
| Workers enrolled | 5,00,000 | 15,00,000 | 35,00,000 |
| Monthly premium (Pro) | ₹150 | ₹199 | ₹249 |
| Annual premium/worker | ₹1,800 | ₹2,388 | ₹2,988 |
| Expected claim rate | 25% | 30% | 38% |
| Avg payout per event | ₹2,500 | ₹3,000 | ₹4,000 |
| Gross premium income/yr | +₹90 Cr | +₹358 Cr | +₹1,046 Cr |
| Total claims paid | −₹31.25 Cr | −₹135 Cr | −₹532 Cr |
| Reinsurance (15%) | −₹13.5 Cr | −₹53.7 Cr | −₹157 Cr |
| Tech + ops | −₹12 Cr | −₹36 Cr | −₹85 Cr |
| CAC + marketing | −₹9 Cr | −₹25 Cr | −₹60 Cr |
| **NET PROFIT/YEAR** | **₹24.25 Cr** | **₹108.5 Cr** | **₹211.8 Cr** |
| Net margin | 26.9% | 30.3% | 20.3% |
| Combined ratio | 73.1% | 69.7% | 79.7% |

---

### App Build Cost Breakdown

| Category | Item | Year 1 Cost | Notes |
|----------|------|------------|-------|
| App Build | MVP development (Android + backend) | ₹28L | India-based team |
| App Build | AI/ML risk + fraud engine | ₹18L | Scikit-learn, FastAPI |
| App Build | UI/UX, QA, security audit | ₹14L | Onboarding + claims flow |
| App Build | API integrations (weather, payment) | ₹5L | IMD, CPCB, Razorpay |
| App Build | Admin panel + analytics dashboard | ₹5L | React web |
| Regulatory | IRDAI broker license + filing | ₹5L | One-time |
| Regulatory | **Minimum capital (BLOCKED — not burned)** | **₹75L** | Stays on balance sheet |
| Regulatory | Compliance + legal + audits | ₹19.1L | Year 1 total |
| Operations | Core team (2 dev, 1 PM, 1 ops) | ₹48L | Annual salaries |
| Operations | Cloud + support + office | ₹17.1L | Annual |
| Go-to-Market | CAC — 50,000 workers @ ₹180 | ₹90L | Direct acquisition |
| Go-to-Market | Marketing + partnerships | ₹23L | Social, WhatsApp, BD |
| | **TOTAL INVESTMENT YEAR 1** | **~₹3.47 Cr** | |
| | Seed round needed | **₹4–5 Cr** | Covers Y1 + Y2 buffer |
| | Real cash burn Y1 | **~₹2.5 Cr** | Capital stays on BS |

---

### Regulatory Path

| Path | Option | Capital Required | Timeline | Best For | Recommendation |
|------|--------|-----------------|----------|----------|---------------|
| **A ⭐** | **IRDAI Regulatory Sandbox** | ~₹25L | 3–4 months | MVP validation with real users | **Start here** |
| B | IRDAI Direct Broker License | ₹75L (blocked) | 6–9 months | Full product launch | After sandbox |
| C | Full General Insurer License | ₹100 Cr | 2–3 years | Own the risk, max margin | Series B stage |

> 💡 **Recommended first move:** Apply to IRDAI Regulatory Sandbox (12-month pilot). Validate parametric triggers with real riders before committing ₹75L to broker license. Use sandbox data to raise seed round.

---

## 🚀 Go-to-Market Strategy

### Platform Partnership — The Distribution Moat

> *"Auto-deduct ₹45/week from Zomato/Swiggy weekly payout. Zero UX friction for the worker."*

| Distribution Channel | CAC | Conversion Rate | Retention Rate | Notes |
|---------------------|-----|----------------|---------------|-------|
| Direct (app download, social) | ₹180/worker | 15–20% | 65% | Year 1 primary channel |
| Referral (worker-to-worker) | ₹120/worker | 25–35% | 72% | Year 1–2 supplementary |
| Platform embed (auto-deduct) | ₹80/worker | 70–85% | 90%+ | Year 2–3 primary |
| **Zomato/Swiggy deal (target)** | **₹30–50/worker** | **85–95%** | **92%+** | Target: close by Y2 Q2 |

> 🎯 Closing a Zomato/Swiggy auto-deduct deal pushes net margin from **11.9% → 20–22%** and adds ~₹1.5 Cr to Year 3 bottom line.

### City Launch Sequence

| Phase | Cities | Timeline | Rationale | Target Workers |
|-------|--------|----------|-----------|---------------|
| Phase 1 (Pilot) | **Bengaluru** | Month 1–4 | Medium risk, tech-savvy riders, lowest CAC — validate model | 10,000–20,000 |
| Phase 2 (Scale) | **Delhi NCR + Mumbai** | Month 5–12 | Highest worker density, prove Very High risk weeks work | +30,000–50,000 |
| Phase 3 (Expand) | **Hyderabad + Chennai** | Year 2 Q1–Q2 | High disruption, strong Q-commerce presence | +50,000–1,00,000 |
| Phase 4 (National) | **Pune, Kolkata, Ahmedabad, Jaipur, Lucknow** | Year 2 Q3–Year 3 | Complete Tier 1+2 city coverage | +1,50,000+ |

### Retention Mechanics — Weekly Streak Rewards

| Streak Milestone | Reward | Cost to ParaGuard | Retention ROI |
|-----------------|--------|------------------|--------------|
| 12 continuous weeks | ₹50 cashback via UPI | ₹50/worker | 9.4× |
| 26 continuous weeks | ₹150 cashback via UPI | ₹150/worker | 7.3× |
| **52 weeks (full year)** | **₹400 cashback + Gold badge** | ₹400/worker | **5.5×** |
| Max annual cashback | ₹600/worker/year | 2.75% of annual premium | **Avg 7× ROI** |

### Default-On Enrollment Logic

| Design Choice | Impact |
|---------------|--------|
| Default enrolled = active (opt-out model) | **85% weekly renewal** vs 60% with active opt-in |
| 1 skip allowed per quarter (no questions asked) | Removes "I'll cancel" reaction — paradoxically increases retention ~15% |
| Saturday midnight opt-out deadline | Gives workers full week to decide; Sunday deduction aligns with platform payout |
| Sunday 8pm next-week notification | Worker knows price 36hrs before deduction — no surprises = trust |

---

## 🏗️ Technical Architecture

ParaGuard follows a **Microservices Architecture** to ensure:
- ✅ Scalability
- ✅ Independent deployment
- ✅ Better fault isolation
- ✅ Separate handling of AI/ML workloads

### Free Government APIs — Parametric Triggers

| API | Data Provided | Trigger Use | Cost |
|-----|--------------|------------|------|
| **IMD API** (India Meteorological Dept) | 7-day forecasts, real-time temp, rainfall, alerts | Heat (>44°C), floods (>50mm), Red/Orange/Yellow alerts | Free |
| **CPCB API** (Central Pollution Control Board) | Real-time AQI by city and monitoring station | Pollution trigger (AQI >300) | Free |
| **NDMA Alerts** (National Disaster Mgmt Authority) | Cyclone, flood, disaster warnings | Cyclone and disaster triggers | Free |
| **OpenWeather API** | Global weather, 7-day forecast, hourly data | Backup / cross-validation for IMD | Free tier (1,000 calls/day) |

---

## 🤖 AI/ML Integration

### Dynamic Pricing Formula

```
Weekly Price = Base Rate × City Multiplier × Week Risk Factor × Plan Multiplier
```

| Variable | Values |
|----------|--------|
| Base Rate (SafeWeek Pro) | ₹39/week (Low risk floor) |
| City Multiplier | Delhi 1.15 · Mumbai 1.10 · Bengaluru 1.00 · Ahmedabad 1.12 · Chennai 1.10 · Others 1.00–1.08 |
| Week Risk Factor | Low 1.00 · Medium 1.15 · High 1.41 · Very High 1.77 |
| Plan Multiplier | Lite 0.74 · Pro 1.00 · Max 1.44 |
| Monthly Cap | Lite ₹160 · Pro ₹220 · Max ₹340 (hard-coded ceiling) |

### Fraud Detection Model

Composite fraud scoring model (0–1). No single signal triggers rejection — all signals combined into a weighted score.

| Signal | How It Works | Weight |
|--------|-------------|--------|
| GPS Spoofing Detection | Location delta >0.5km/min = likely spoofed | 25% |
| Zone Presence Validation | Was rider within geo-fenced disrupted area during event? | 30% |
| Activity Cross-Check | Order count drop <30% vs 30-day avg = suspicious | 25% |
| Platform API Activity | Active deliveries during claimed downtime = reject | 15% |
| Duplicate Claim Detection | Same worker, same event, second claim = auto-reject | 5% |

| Fraud Score | Action | Volume |
|-------------|--------|--------|
| 0.0 – 0.29 | ✅ Auto-approve and pay | ~85% of claims |
| 0.30 – 0.69 | ⏳ Manual review (within 4 hours) | ~12% of claims |
| 0.70 – 1.00 | ❌ Auto-reject (appeal available) | ~3% of claims |

### Risk Profiling

| Profile Dimension | Data Source | Used For |
|-------------------|------------|---------|
| Rider's home zone vs disruption-prone zones | GPS history + platform data | Adjusting personal risk multiplier |
| Historical earnings baseline (8-week rolling avg) | Platform API (weekly payout data) | Calculating payout = % of baseline lost |
| Disruption sensitivity by season | Past claim history + earnings dips | Personalising plan recommendation |
| Platform tenure and activity patterns | Platform ID + activity data | Fraud baseline — new accounts flagged |

---

## 🛠️ Tech Stack

| Layer | Technology | Purpose |
|-------|-----------|---------|
| Backend | Node.js (Express) | User service, monitor service, payment, notifications |
| Backend | Java (Spring Boot) | Policy & premium service — transactional data |
| AI / ML | Python + FastAPI | Claims validation, fraud detection, risk profiling |
| AI / ML | Scikit-learn | Anomaly detection models, fraud scoring |
| Database | PostgreSQL | Transactional data — policies, claims, payouts |
| Database | MongoDB | Persona data, delivery profiles, activity logs |
| Database | Redis | Real-time triggers, caching, session data |
| Messaging | RabbitMQ / AWS SQS | Async communication between services |
| Frontend | React | Web dashboard — admin analytics, claim review queue |
| Mobile | React Native | Rider app — onboarding, weekly plan, payout notifications |

---

## 📂 Microservice File Structures

### 1. User & Persona Service (Node.js / MongoDB)

```
user-service/
├── src/
│   ├── controllers/      # Onboarding logic
│   ├── models/           # MongoDB Schema (Persona/Earnings)
│   ├── routes/           # API Endpoints
│   └── services/         # Integration with Platform APIs (Mocks)
├── tests/
└── server.js
```

### 2. Policy & Premium Service (Java / PostgreSQL)

```
policy-service/
├── src/main/java/com/paraguard/
│   ├── controller/       # Premium & Policy API
│   ├── entity/           # JPA Entities (WeeklyPolicy)
│   ├── repository/       # PostgreSQL Repositories
│   └── service/          # Dynamic Pricing Logic (week risk factor × city multiplier)
└── src/main/resources/
    └── application.properties
```

### 3. Monitor & Trigger Service (Node.js / Redis)

```
monitor-service/
├── src/
│   ├── cron/             # API Polling Jobs (IMD/CPCB/NDMA — every 30 min)
│   ├── triggers/         # Threshold Logic (Temp >44°C, Rain >50mm, AQI >300)
│   └── utils/            # Redis Client
├── mock-apis/            # Mocked IMD/CPCB/NDMA responses for testing
└── app.js
```

### 4. Claims & Fraud AI Service (Python / FastAPI)

```
claims-ai-service/
├── models/               # Saved ML Models (.pkl) — fraud scorer, risk profiler
├── src/
│   ├── api/              # Claim Validation Endpoints
│   ├── core/             # Fraud Logic (GPS Spoofing, Zone Check, Activity Check)
│   └── ml_engine/        # Risk Profiling Scripts + Weekly Tier Classifier
├── main.py
└── requirements.txt
```

### 5. Payment Service (Node.js)

```
payment-service/
├── src/
│   ├── controllers/      # Payout disbursement logic
│   ├── gateways/         # Razorpay mock + UPI integration
│   └── services/         # Premium collection, weekly deduction
└── server.js
```

### 6. Notification Service (Node.js / Redis)

```
notification-service/
├── src/
│   ├── templates/        # Sunday pricing alert, payout confirmation, streak reward
│   ├── channels/         # FCM (push), WhatsApp Business API, SMS
│   └── scheduler/        # Sunday 8pm cron — weekly tier announcement
└── app.js
```

---

## ✅ Summary

| Dimension | ParaGuard's Approach |
|-----------|---------------------|
| Coverage scope | Income loss **only** — not health, life, accidents, or vehicle repairs |
| Pricing model | Weekly dynamic: ₹39–₹99/week depending on risk tier, city, and plan |
| Trigger mechanism | 100% parametric — IMD/CPCB/NDMA APIs auto-trigger. Zero manual filing. |
| Fraud prevention | ML fraud scorer (0–1): GPS + zone + activity + duplicate. 85% auto-approved. |
| Target persona | Q-Commerce riders (Blinkit, Zepto, Instamart) — highest disruption sensitivity |
| Addressable market | ~35 Lakh delivery workers; 9 Lakh Q-Commerce riders as core target |
| Financial model | Break-even Month 26 · Year 3: ₹2.27 Cr net profit at 11.9% margin (8L workers) |
| Regulatory path | IRDAI Sandbox → Broker License (₹75L) → Full Insurer (Series B) |
| Distribution moat | Platform auto-deduction — CAC drops to ₹30–50 at scale |
| Seed requirement | ₹4–5 Cr (₹2.5 Cr real cash burn; ₹75L regulatory capital on balance sheet) |

---

> **ParaGuard's core value proposition:**
> *"Pay ₹45 this week — if weather shuts you down, get ₹1,200 back the same day. Automatically. No forms. No waiting."*

---

<div align="center">

**Data Sources:** NCAER 2022 · TGPWU/HeatWatch 2024 · IMD 2024 · CPCB · Zomato/Swiggy Q3 FY25 filings · Borzo Gig Worker Survey 2025 · IRDAI Regulations 2024

*ParaGuard — Protecting India's Gig Economy, One Week at a Time* 🛡️

</div>
