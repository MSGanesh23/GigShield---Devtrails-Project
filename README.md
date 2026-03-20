<div align="center">

# 🛵 GigShield

### Parametric Income Insurance for India's Delivery Workers

*When the weather stops you from working — we make sure you still get paid.*

<br/>

![Status](https://img.shields.io/badge/Status-Phase%201%20Submission-brightgreen?style=for-the-badge)
![Event](https://img.shields.io/badge/Guidewire-DEVTrails%202026-blue?style=for-the-badge)
![Persona](https://img.shields.io/badge/Persona-Q--Commerce%20Delivery-orange?style=for-the-badge)

</div>

---

## 📌 The Problem

Every day, millions of delivery workers power India's instant delivery economy.

But when a storm hits, AQI spikes, or a curfew shuts down their zone — **they lose hundreds of rupees with zero protection.** No employer cover. No union. No insurance built for them.

> A Zepto partner in Bengaluru can lose ₹480 in a single rainy afternoon.
> A Blinkit partner in Delhi loses ₹600 when AQI crosses 400.
> There is currently nothing that pays them back.

**GigShield fixes that.**

---

## 💡 What Is GigShield?

GigShield is a **parametric income insurance platform** built exclusively for Q-Commerce delivery partners on Zepto, Blinkit, and Swiggy Instamart.

When a verified disruption event occurs in a worker's zone, **GigShield automatically detects it and sends a UPI payout — no claim form, no phone call, no waiting.**

```
Disruption detected  →  Zone verified  →  Payout sent  →  Worker protected
        ↑                                                          ↓
   (Weather API)                                           (UPI in < 5 min)
```

---

## 🎯 Our Persona

**Q-Commerce Delivery Partners** — Zepto · Blinkit · Swiggy Instamart

| | Profile |
|---|---|
| 👤 Age | 20–35 years |
| 💰 Daily Income | ₹600 – ₹1,200 |
| ⏱️ Pay Cycle | Weekly |
| 📱 Device | Low-mid range Android |
| 🗺️ Work Zone | Hyper-local micro-zones (2–3 km radius) |
| 📦 Delivery Rate | 8–15 deliveries/hour |

> **Why Q-Commerce?** These workers have the highest delivery frequency of any gig segment. Every disrupted hour costs them more. They need protection the most.

---

## 👥 Real Worker Stories

<table>
<tr>
<td width="33%">

**🌧️ Kamla — Zepto, Bengaluru**

Heavy rain shuts her zone at 4 PM. She loses 3 hours — ₹480 gone.

GigShield detects the rainfall, confirms her zone, and sends ₹480 to her UPI before she gets home.

*She did nothing.*

</td>
<td width="33%">

**😷 Ravi — Blinkit, Delhi**

AQI hits 401. GRAP Stage IV restrictions halt all outdoor delivery for 5 hours — ₹600 lost.

GigShield picks up the AQI alert, matches Ravi's zone, and triggers the payout automatically.

*Zero friction.*

</td>
<td width="33%">

**🚨 Priya — Instamart, Pune**

Section 144 curfew in her zone. 4 hours of lost work — ₹400.

GigShield's news monitoring detects the curfew, cross-checks Priya's zone, and pays her out.

*Instant safety net.*

</td>
</tr>
</table>

---

## ⚙️ How It Works

```
┌─────────────────────────────────────────────────────────────┐
│                      GIGSHIELD FLOW                         │
├──────────────┬──────────────────────┬───────────────────────┤
│   SIGN UP    │   DISRUPTION HITS    │      PAYOUT SENT      │
│              │                      │                       │
│ Phone OTP    │  Weather / AQI /     │  UPI transfer in      │
│ Pick zone    │  Curfew detected     │  under 5 minutes      │
│ Choose plan  │  via public APIs     │                       │
│              │                      │  Worker notified      │
│  ~2 minutes  │  Fully automatic     │  on their phone       │
└──────────────┴──────────────────────┴───────────────────────┘
```

No forms. No calls. No delays.

---

## 💸 Weekly Pricing

> Gig workers earn weekly — so GigShield prices weekly.

| Plan | Daily Payout | Weekly Premium |
|:---:|:---:|:---:|
| 🟢 Basic | ₹300 / day | ₹30 – ₹50 / week |
| 🟡 Standard | ₹500 / day | ₹50 – ₹80 / week |
| 🔴 Premium | ₹800 / day | ₹75 – ₹125 / week |

Pricing is dynamic — workers in higher-risk zones (flood-prone, historically disrupted) pay slightly more. Calmer zones get a discount. **Recalculates every Monday automatically.**

---

## ⚡ Disruption Triggers

Every payout is driven by **real external data** — not by the worker filing anything.

| Disruption | Data Source | Trigger Threshold |
|---|---|---|
| 🌧️ Heavy Rainfall | OpenWeatherMap / IMD | ≥ 50mm/hr for 30 minutes |
| 🌡️ Extreme Heat | OpenWeatherMap | ≥ 44°C + active NDMA advisory |
| 😮‍💨 Severe Pollution | CPCB AQI API | AQI ≥ 400 for 2+ hours |
| 🌊 Flooding | IMD flood alerts | Active flood alert in delivery PIN code |
| 🚨 Curfew / Strike | News API + Govt feed | Official order in delivery zone |
| 📵 App Outage | Platform API (mock) | Zone outage lasting 1+ hour |

> **Two independent sources must confirm a disruption before any payout fires.** This is the first line of defense against false triggers.

---

## 🤖 AI in GigShield

We use AI in two simple, focused ways:

### 📊 Smart Pricing
The AI looks at a zone's past disruption history and the upcoming week's weather forecast to set a fair weekly premium for each worker. Riskier zones cost a bit more. Quieter zones cost less. No manual work — it recalculates every Monday on its own.

### 🔍 Fraud Detection
Before releasing any payout, the system automatically checks: Was this worker active in the claimed zone recently? Does their actual phone location match? Is there an unusual surge of claims from the same area all at once? If something looks off, the claim is held for a quick human review instead of auto-paying.

---

## 🛡️ Adversarial Defense & Anti-Spoofing Strategy

### ⚠️ The Threat

A known attack pattern: a coordinated group of workers uses GPS-spoofing apps to fake their location inside a disrupted zone while sitting safely at home — draining the payout pool in minutes. Standard GPS checks cannot catch this.

**GigShield uses three layers of defense.**

---

### Layer 1 — Phone Location vs. GPS Location

GPS coordinates can be faked by an app. **Cell tower data cannot.**

GigShield cross-references the GPS claim with the cell towers the phone is actually connecting to. A worker whose GPS says Andheri East but whose phone pings Thane towers — flagged immediately, regardless of what GPS reports.

---

### Layer 2 — How the Phone is Behaving

A real worker outdoors in rain looks different from someone lying at home running a spoof script:

| Signal | Genuine Worker | Spoofer at Home |
|---|---|---|
| Movement (accelerometer) | Slight vibration, movement | Completely still |
| Delivery app | Open and active | Backgrounded |
| Battery drain | Higher (GPS + data active) | Lower (idle, on Wi-Fi) |

These behavioral signals are checked automatically before every payout.

---

### Layer 3 — Coordinated Group Detection

Real claims arrive spread out over time. **A Telegram-organized syndicate submitting 50+ claims in a 2-minute window is statistically obvious.**

GigShield monitors claim rates per zone in real time. If a sudden spike is detected, all payouts in that zone are paused and routed to review before any money moves.

---

### ✅ Protecting Honest Workers

Bad weather causes weak GPS, poor signal, and draining batteries — the same signals that could look suspicious. We make sure genuine workers aren't unfairly caught:

```
No flags        →  Auto-approved. Payout in < 5 minutes.

One unclear     →  Short hold. Worker gets a tap-to-confirm
signal             notification. Clears in 15 minutes.

Multiple flags  →  Manual review. Worker notified:
                   "We'll update you in 2 hours."

Signal lost     →  Last known location held for 30 minutes.
during event       Reconnect in same zone = claim goes through.
```

Every denied claim has a **one-tap dispute option**. We respond within 24 hours.

---

## 📱 Platform

We're building a **Progressive Web App (PWA).**

Workers open a link — no app store, no download, no storage used. Works on any low-end Android phone on a 3G connection. The insurer gets a separate web dashboard for monitoring claims, zones, and flagged cases.

---

## 🔧 Tech Stack

| Layer | Tech |
|---|---|
| 📱 Worker App | React PWA |
| ⚙️ Backend | Node.js + Express |
| 🤖 AI / ML | Python — pricing model + fraud checks |
| 🗄️ Database | PostgreSQL + Redis |
| 🌦️ Weather & AQI | OpenWeatherMap, CPCB (free APIs) |
| 💳 Payments | Razorpay test mode (UPI simulation) |
| 🔐 Auth | Firebase Phone OTP |

---

## 🚫 What GigShield Does NOT Cover

To be completely clear about our scope:

- ❌ Health or medical expenses
- ❌ Accidents or injuries
- ❌ Vehicle damage or repair
- ❌ Life insurance

**✅ GigShield covers one thing only: income lost because an external disruption made it impossible to work.**

---

<div align="center">

*Built for DEVTrails 2026 — Guidewire*

**GigShield — because every disrupted hour deserves a safety net. 🛵**

</div>
