# 🛡️ ShieldWage — AI-Powered Parametric Income Insurance for India's Gig Economy

> **Guidewire DEVTrails 2026** | University Hackathon | Phase 1 Submission
> **Deadline:** March 20, 2026

---

## 📌 Table of Contents

1. [Problem Statement](#1-problem-statement)
2. [Our Solution](#2-our-solution)
3. [Persona & Scenarios](#3-persona--scenarios)
4. [Application Workflow](#4-application-workflow)
5. [Weekly Premium Model](#5-weekly-premium-model)
6. [Parametric Triggers](#6-parametric-triggers)
7. [Platform Choice: Web vs Mobile](#7-platform-choice-web-vs-mobile)
8. [AI/ML Integration Plan](#8-aiml-integration-plan)
9. [Tech Stack](#9-tech-stack)
10. [Development Plan](#10-development-plan)
11. [Compliance with Golden Rules](#11-compliance-with-golden-rules)

---

## 1. Problem Statement

India has over **12 million platform-based delivery partners** working for Zomato, Swiggy, Zepto, Amazon, Dunzo, and Blinkit. These workers are the arteries of the digital economy — yet they are completely unprotected against income loss caused by external disruptions.

| Disruption Event | Frequency | Avg. Income Lost per Day |
|---|---|---|
| Heavy Monsoon Rain (>40mm/hr) | 40–60 days/year in metros | ₹600–₹1,200 |
| Extreme Heat (>44°C) | 20–30 days/year (Delhi/Jaipur) | ₹400–₹800 |
| Severe AQI (>400, GRAP IV) | 10–20 days/year (Delhi NCR) | ₹700–₹1,100 |
| Unplanned Curfew / Bandh | 5–10 events/year | ₹800–₹1,200 (full day) |
| Platform App Outage (>2hrs) | 4–8 incidents/year | ₹300–₹600 |

**Result:** A delivery partner loses ₹18,000–₹36,000 per year (~20–30% of annual income) to disruptions entirely outside their control, with **zero financial safety net**.

---

## 2. Our Solution

**ShieldWage** is a zero-touch, AI-enabled **parametric income insurance platform** for food delivery partners.

### How It's Different from Traditional Insurance

| Traditional Insurance | ShieldWage (Parametric) |
|---|---|
| File a claim → wait 7–30 days | No claim to file — payout is automatic |
| Prove your loss with documents | External data (weather API, AQI) IS the proof |
| Monthly premium (misaligned) | Weekly premium (matches gig pay cycle) |
| High rejection rate | Pre-defined triggers = guaranteed payout |
| Designed for salaried workers | Designed for ₹800/day gig workers |

### The ShieldWage Promise
> *"If the weather or the city shuts you down, ShieldWage pays you within 2 hours. Automatically. No forms. No waiting. Just money."*

---

## 3. Persona & Scenarios

### 🎯 Chosen Persona: Food Delivery Partners (Zomato / Swiggy)

We chose food delivery over e-commerce or Q-commerce because:
- Largest workforce segment (~7M+ active riders)
- Highest weather exposure (outdoor, two-wheeler only, peak orders during rain = peak danger)
- Most predictable income baseline (daily active hours trackable via platform API)
- WhatsApp-first, UPI-native — perfect for zero-friction notifications and payouts

### 👤 User Persona: "Raju"

```
Name        : Raju Kumar
Age         : 27
City        : Mumbai (operates in Andheri–Kurla zone)
Platform    : Zomato (primary) + Swiggy (secondary)
Device      : Android smartphone (₹8,000 range), WhatsApp daily user
Hours/Day   : 8–10 hours active
Daily Earn  : ₹750–₹1,100 (depending on orders + weather)
Monthly     : ₹18,000–₹24,000
Pain Point  : Lost ₹4,200 last monsoon week. No savings. No insurance.
Tech Comfort: UPI payments, WhatsApp, basic apps — NOT complex portals
```

### 📖 Scenario A — Mumbai Monsoon (Environmental: Heavy Rain)

**Event:** Heavy rainfall 52mm/hr hits Andheri-Kurla zone from 11:00am–3:00pm on a Sunday.

**Without ShieldWage:** Raju parks his bike, earns ₹0 for 4 hours. His Sunday average was ₹1,100. He loses ₹440 in a day he cannot recover.

**With ShieldWage:**
1. Weather API detects rainfall crossing 40mm/hr threshold at 11:07am
2. System validates Raju was **online** on the platform during the window (API cross-check)
3. Fraud engine runs: GPS trace confirms he was stationary in affected zone ✅
4. Auto-claim initiated at 11:15am
5. ₹440 credited to Raju's UPI by 1:00pm
6. WhatsApp message: *"Rain protected ✅ ₹440 added to your wallet. Stay safe, Raju."*

---

### 📖 Scenario B — Delhi Bandh (Social: Unplanned Curfew)

**Event:** Local political strike declared at 6am, all of East Delhi zones locked till 6pm.

**With ShieldWage:**
1. ShieldWage monitors news APIs + Zomato/Swiggy zone suspension data
2. Detects zone-level app suspension at 6:12am (platform API reports 0 active orders in affected zones)
3. Confirms Raju's registered zone is affected
4. Full-day payout (₹850 — his 30-day average) credited by 8am
5. WhatsApp: *"Curfew detected in your zone 🔴 Income for today protected. ₹850 sent."*

---

### 📖 Scenario C — Delhi AQI Severe Alert (Environmental: Pollution)

**Event:** AQI hits 427 (Severe+). GRAP Stage IV restrictions imposed. All outdoor work halted by CPCB advisory.

**With ShieldWage:**
1. CPCB/AQI API breach detected at 7:00am (threshold: AQI ≥ 400 sustained 2hrs)
2. Delivery platform confirms order volumes dropped 80% in affected zones
3. Payout = 80% of Raju's daily average (₹680)
4. WhatsApp: *"Air is unsafe ⚠️ GRAP IV active. ₹680 protected today. Don't ride."*

---

## 4. Application Workflow

```
┌─────────────────────────────────────────────────────────────────┐
│                     GIGSHIELD PLATFORM                          │
│                                                                 │
│  [WORKER FLOW]                    [SYSTEM FLOW]                 │
│                                                                 │
│  1. ONBOARD                       AI Risk Profiling             │
│     Phone + KYC + Platform ID ──► Zone Risk Score               │
│     Earnings history import       Tenure + City analysis        │
│                    │                                            │
│                    ▼                                            │
│  2. SUBSCRIBE                     ML Premium Calc               │
│     Choose Plan (Basic/Std/Pro)──► Dynamic weekly rate          │
│     Pay via UPI                   Personalised quote            │
│                    │                                            │
│                    ▼                                            │
│  3. ACTIVE COVERAGE               Real-time Monitor             │
│     7-day policy window    ◄───── Weather/AQI/Traffic APIs      │
│     Rider works normally          Curfew/news feed              │
│                    │                                            │
│                    ▼                                            │
│  4. DISRUPTION DETECTED           Parametric Engine             │
│     Threshold breach alert ◄───── Event validated               │
│     Rider notified via WA         Fraud checks run              │
│                    │                                            │
│                    ▼                                            │
│  5. AUTO PAYOUT                   Claims Engine                 │
│     UPI credited within 2hrs◄──── Razorpay/UPI disbursal       │
│     WhatsApp confirmation         Audit log created             │
│                    │                                            │
│                    ▼                                            │
│  6. DASHBOARD                     Analytics Engine              │
│     Rider: earnings protected     Admin: loss ratios            │
│     Claim history                 Risk heatmaps                 │
│     Renewal prompt                Predictive forecast           │
└─────────────────────────────────────────────────────────────────┘
```

### Screen-by-Screen Breakdown

| Screen | User Type | Purpose |
|---|---|---|
| Onboarding (3 steps) | Rider | Phone OTP → Platform ID link → Zone confirm |
| Plan Selection | Rider | Compare Basic/Standard/Premium with dynamic price |
| Active Policy Card | Rider | Current coverage status, days remaining, triggers watching |
| Alert Notification | Rider | WhatsApp push: disruption detected, payout incoming |
| Wallet / Payout History | Rider | All payouts received, breakdown by disruption type |
| Risk Dashboard | Admin/Insurer | Zone heatmaps, claim frequency, loss ratios |
| Predictive Alerts | Admin/Insurer | 7-day forecast of likely payout exposure |

---

## 5. Weekly Premium Model

### Why Weekly?

- Zomato pays riders **every 7 days** (Wednesday cycle)
- Swiggy pays every **Monday**
- A monthly premium requires saving across 4 weeks — unnatural for cash-flow-constrained gig workers
- Weekly aligns perfectly: pay from this week's earnings → covers next 7 days

### Premium Tiers

| Plan | Weekly Premium | Max Payout/Week | Coverage Triggers |
|---|---|---|---|
| **Basic** | ₹29/week | ₹500 | Heavy Rain, Extreme Heat |
| **Standard** | ₹49/week | ₹900 | + Severe AQI, Flood, Curfew |
| **Premium** | ₹79/week | ₹1,500 | All triggers + Platform Outage + partial low-order coverage |

> **Critical Constraint Compliance:** No health, life, accident, or vehicle repair coverage at any tier.

### Dynamic Premium Formula

```
Base Rate (tier) 
  + Zone Risk Loading    (+0% to +20% based on historical disruption freq in zone)
  + Season Loading       (+0% to +30% during Jun-Sep monsoon, Dec-Jan fog)
  - Tenure Discount      (-₹2 to -₹5/week for 6+ months on-platform)
  - Safe Zone Discount   (-₹2/week for zones with <2 disruptions/90 days)
  
Final Weekly Premium = max(₹29, min(₹99, calculated_value))
Cap at 0.5% of declared weekly earnings
```

**Example:** Raju (Standard plan, Andheri zone, July, 8 months tenure):
```
Base: ₹49
Zone loading: +₹7 (Andheri — frequent waterlogging)
Season loading: +₹8 (July monsoon peak)
Tenure discount: -₹4
Final: ₹60/week
```

---

## 6. Parametric Triggers

Parametric insurance pays when a **measurable, external threshold** is crossed — no manual claim needed.

| # | Trigger | Threshold | Data Source | Payout Basis |
|---|---|---|---|---|
| 1 | **Heavy Rain** | ≥40mm/hr sustained ≥2 hrs | OpenWeatherMap API + IMD | % of daily avg × hours affected |
| 2 | **Extreme Heat** | ≥45°C sustained ≥3 hrs | OpenWeatherMap API | 50% of daily avg (reduced orders) |
| 3 | **Flood / Waterlogging** | IMD Red Alert + 0 orders in zone ≥4 hrs | IMD API + Platform feed | 100% of daily avg |
| 4 | **Severe AQI** | AQI ≥400 (Severe+) sustained ≥2 hrs | CPCB API / AQI India | 80% of daily avg |
| 5 | **Curfew / Bandh** | Govt advisory OR zone app suspension ≥2 hrs | NewsAPI + Platform zone data | 100% of affected hours avg |
| 6 | **Platform Outage** | App down ≥2 hrs (multi-source verified) | StatusPage + UptimeRobot | 100% of downtime period avg |

### Trigger Validation Pipeline

```
External API → Threshold Check → Zone Cross-Reference → Rider Online Validation
     │                                                          │
     └──── FRAUD ENGINE ─── GPS Trace ─── Velocity Check ──────┘
                                  │
                            Pass → AUTO PAYOUT
                            Fail → Manual Review Queue
```

---

## 7. Platform Choice: Web vs Mobile

**Decision: Progressive Web App (PWA) — Web-first, Mobile-responsive**

### Justification

| Factor | Native App | PWA (Our Choice) |
|---|---|---|
| Installation friction | Requires Play Store download | Opens in browser, installable in 1 tap |
| Update cycle | App Store review delay | Instant updates, no approval needed |
| Offline support | Yes (complex) | Yes (Service Workers) |
| Hackathon speed | Very slow (build pipeline) | Fast iteration |
| Admin dashboard | Separate build needed | Same codebase, responsive |
| Data cost for users | Higher (download) | Lower (cached PWA) |

**Worker UX:** Open browser link → install to home screen → use like an app.
**Notifications:** WhatsApp Business API (not push notifications) — Raju already uses WhatsApp 20x/day. Zero learning curve.

---

## 8. AI/ML Integration Plan

### Model 1: Dynamic Premium Calculator (XGBoost Regressor)

```python
# Input features:
features = [
    'worker_zone_risk_score',    # GPS zone → historical disruption freq
    'city_tier',                 # Metro/Tier-1/Tier-2
    'season_month',              # 1–12 → monsoon/winter loading
    'platform_tenure_weeks',     # loyalty discount
    'avg_weekly_earnings',       # premium cap check
    'chosen_tier'                # Basic/Standard/Premium
]
# Output: recommended_weekly_premium (₹29–₹99)
# Training: Synthetic dataset of 50,000 worker-week records + historical weather data
```

### Model 2: Risk Profiling at Onboarding (K-Means + Random Forest)

- **Clustering:** Group workers by zone, hours, platform, city → Low/Medium/High risk tiers
- **Classifier:** Predict tier for new worker at signup (cold-start problem)
- **Output:** Risk tier → maps to starting premium bracket and coverage limits

### Model 3: Fraud Detection Engine (Isolation Forest + Rule Engine)

```
Signals evaluated per claim:
├── GPS Trace Validation     → Was rider stationary in declared zone?
├── Online Window Check      → Was rider logged into platform during event?
├── Earnings Velocity        → Unusual low-earning days outside disruption?
├── Claim Frequency          → >3 claims in 4 weeks → manual review flag
├── Network Collusion Graph  → Multiple riders always claiming same event?
└── Historical Pattern       → Zone-event pair seen before with this rider?
```

### Model 4: Predictive Analytics Dashboard (Time Series — Prophet / LSTM)

- Input: 7-day weather forecast + historical claim data per zone
- Output: Predicted payout liability for next 7 days per city zone
- Insurer use: Pre-position reserves, flag high-risk weeks

---

## 9. Tech Stack

### Frontend
```
React.js (PWA) + TailwindCSS
Vite (build tool)
Workbox (Service Worker / offline support)
Recharts (analytics dashboards)
React Hook Form + Zod (onboarding validation)
```

### Backend
```
Node.js + Express.js (REST API)
PostgreSQL (primary DB — policies, claims, riders)
Redis (real-time trigger cache, event deduplication)
Prisma ORM
JWT authentication
```

### ML Service
```
Python 3.11 + FastAPI
scikit-learn (risk profiling, fraud detection)
XGBoost (premium calculation)
Prophet (predictive analytics)
Pandas + NumPy (data processing)
```

### External Integrations (Free Tier / Mock)
```
OpenWeatherMap API     → Rain, temperature data (free tier: 1000 calls/day)
CPCB AQI API           → Air quality index (free, government open data)
NewsAPI.org            → Curfew/bandh detection (free tier)
Razorpay Test Mode     → UPI payout simulation
WhatsApp Business API  → Rider notifications (free tier: 1000 msgs/month)
Mock Platform API      → Simulated Zomato/Swiggy earnings feed (JSON server)
```

### DevOps
```
GitHub (monorepo: /frontend, /backend, /ml-service, /mock-api)
Docker + Docker Compose (local dev)
GitHub Actions CI/CD
Railway.app or Render (free-tier deployment)
```

### Repository Structure
```
shieldwage/
├── frontend/               # React PWA
│   ├── src/
│   │   ├── pages/          # Onboarding, Dashboard, Policy, Claims
│   │   ├── components/     # Shared UI components
│   │   └── services/       # API clients
│   └── public/
├── backend/                # Node.js API
│   ├── src/
│   │   ├── routes/         # auth, policy, claims, triggers, payouts
│   │   ├── services/       # premium-calc, fraud, payout, notification
│   │   └── jobs/           # Cron: trigger monitoring every 15 mins
│   └── prisma/             # DB schema
├── ml-service/             # Python FastAPI
│   ├── models/             # trained model artifacts
│   ├── api/                # /predict-premium, /risk-profile, /fraud-score
│   └── notebooks/          # Training notebooks
└── mock-api/               # JSON Server
    └── data/               # Simulated platform earnings, zone data
```

---

## 10. Development Plan

### Phase 1 — Ideation & Foundation (Weeks 1–2) | Mar 4–20
**Theme:** *"Ideate & Know Your Delivery Worker"*

- [x] Persona research and scenario definition
- [x] System architecture design
- [x] Database schema design (riders, policies, claims, triggers, payouts)
- [x] Repository setup with monorepo structure
- [x] Mock API scaffolding (Zomato/Swiggy simulated data)
- [x] Low-fidelity wireframes for all 7 screens
- [x] README.md (this document)
- [ ] 2-minute strategy video (recording in progress)

**Deliverables:** ✅ This README + GitHub Repo + 2-min video

---

### Phase 2 — Automation & Protection (Weeks 3–4) | Mar 21–Apr 4
**Theme:** *"Protect Your Worker"*

- [ ] Rider onboarding UI (3-step: Phone OTP → Platform link → Zone)
- [ ] Policy creation flow with dynamic premium display
- [ ] ML v1: Premium calculation model (XGBoost, trained on synthetic data)
- [ ] 5 parametric triggers wired (Rain, Heat, AQI, Curfew, Outage)
- [ ] Auto-claim initiation engine
- [ ] Razorpay test mode payout integration
- [ ] WhatsApp notification on trigger + payout
- [ ] Basic rider dashboard (policy status, earnings protected)

**Deliverables:** Working prototype + 2-min demo video

---

### Phase 3 — Scale & Optimise (Weeks 5–6) | Apr 5–17
**Theme:** *"Perfect for Your Worker"*

- [ ] Advanced fraud detection (GPS spoof, velocity, network graph)
- [ ] Insurer/Admin dashboard (loss ratios, zone heatmaps, predictive analytics)
- [ ] Prophet/LSTM 7-day payout forecasting
- [ ] End-to-end disruption simulation demo (fake rainstorm → auto-payout)
- [ ] Final pitch deck (PDF)
- [ ] 5-minute walkthrough video

**Deliverables:** Final submission package

---

## 11. Compliance with Golden Rules

| Golden Rule | ShieldWage Status |
|---|---|
| ✅ Persona: Food delivery (Zomato/Swiggy) only | **Confirmed** — Raju persona, food delivery |
| ✅ Coverage: INCOME LOSS ONLY | **Confirmed** — No health, vehicle, accident coverage |
| ✅ Weekly pricing model | **Confirmed** — ₹29/₹49/₹79 per week |
| ✅ AI-powered risk assessment | **Confirmed** — XGBoost premium calc |
| ✅ Intelligent fraud detection | **Confirmed** — Isolation Forest + GPS + rule engine |
| ✅ Parametric automation | **Confirmed** — 6 triggers, auto-payout pipeline |
| ✅ Integration capabilities | **Confirmed** — OpenWeatherMap, CPCB, Razorpay, WhatsApp |
| ✅ Analytics dashboard | **Confirmed** — Rider + Insurer dashboards |

---

## 👥 Team

> *[Team name and member details to be added]*

---

## 📄 License

MIT License — Open source for hackathon purposes.

---

*ShieldWage — Because every delivery matters. Even on rainy days.* 🌧️
