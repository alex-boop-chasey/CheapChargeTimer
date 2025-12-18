# Cheap Charge Timer

## Feature Definition & Behaviour (Standalone Phase 1)

**Status:** Draft – Editable

---

## 1. Purpose

This document defines the **feature set, behavioural rules, and user-facing intent** of the **Cheap Charge Timer** standalone app.

Cheap Charge Timer is a **Phase 1 standalone extraction** of ChargeTimerPro. It implements a subset of canonical features with identical intent, wording discipline, and truth-handling rules, while remaining foldable into the larger app with minimal, non-conceptual changes.

This document explicitly clarifies:

* How **Savings Tracker** works (retrospective only, no projections)
* What forms of **gamification are allowed**
* The exact **feature list**, **real-life scenarios**, and **one-sentence locks** used by the app

---

## 2. Canonical Feature Set (Phase 1)

Cheap Charge Timer implements **only** the following canonical features:

| Feature ID | Feature Name             | Availability |
| ---------- | ------------------------ | ------------ |
| 1          | Cheap Charge Time Alerts | Free         |
| 3          | Savings Tracker          | Free         |
| 6          | AutoCharge               | Subscription |

No additional features are introduced.

---

## 3. Feature 1 – Cheap Charge Time Alerts

### What it does

Connects to the user’s electricity tariff to identify when power is cheapest during a given period. The app highlights these low-cost windows and alerts the user when they arrive, enabling informed charging decisions without urgency or pressure.

Tariff pricing is treated as authoritative, time-scoped data. If pricing data is unavailable, stale, or low confidence, the feature degrades calmly by withholding alerts rather than guessing.

### Real-life scenario

You arrive home in the evening and open Cheap Charge Timer. The app shows that electricity will be significantly cheaper later that night based on your power plan. You choose to wait.

When the cheap charging window begins, you receive a notification. You plug in and start charging at the lower rate, knowing the decision is based on real pricing data, not estimates.

### One-sentence lock

**Cheap Charge Time Alerts shows you when electricity is cheapest for your specific power plan and alerts you when those times arrive.**

---

## 4. Feature 3 – Savings Tracker

### What it does

Savings Tracker shows **what you have already saved**, based on real charging sessions and real electricity prices.

Savings are calculated **after a charging period completes**, by comparing:

* The price paid during the charge window
* Against the **highest electricity price during that same period**

The feature does **not**:

* Estimate future savings
* Project annual or lifetime outcomes
* Assume alternative user behaviour

All savings figures are retrospective, defensible, and grounded in actual tariff data.

### Real-life scenario

After charging overnight, you open Cheap Charge Timer. The app shows that charging during the cheap window cost less than it would have during peak pricing earlier that day.

Later in the week, you view your weekly total and see how several small savings have accumulated. There are no promises about the future — only a clear record of what has already happened.

### One-sentence lock

**Savings Tracker shows how much money you save by charging at cheaper times, using real prices from the same period.**

---

## 5. Gamification Rules (Savings Tracker)

### Allowed gamification (truth-based)

Gamification is permitted **only** when it reflects real, completed outcomes. Allowed patterns include:

* Accumulated savings totals (day, week, month)
* Milestones based on actual savings achieved
* Streaks for consecutive charges during cheap windows
* Visual reinforcement (progress bars, counters, celebratory copy)

All gamified elements must map directly to **historical data**.

### Forbidden gamification

The app must never:

* Project future savings ("On track to save…")
* Compare against hypothetical behaviour ("If you had charged at peak…")
* Use urgency or loss framing ("You’re losing money right now")
* Use leaderboards or social comparison

The guiding rule is:

> **Savings Tracker may celebrate what already happened, but must never speculate about what might happen.**

---

## 6. Feature 6 – AutoCharge (Subscription)

### What it does

AutoCharge automatically starts and stops charging during the cheapest electricity periods using compatible smart home-connected charging devices.

AutoCharge acts **only** on:

* High-confidence tariff data
* Explicit user authorisation
* Supported smart home integrations

If confidence drops, AutoCharge disables itself safely and visibly.

### Real-life scenario

You enable AutoCharge and link your supported smart home charger. That night, when electricity prices drop, charging begins automatically.

When the cheap window ends, charging stops. If pricing data becomes unavailable, AutoCharge does nothing rather than guessing.

### One-sentence lock

**AutoCharge uses compatible smart home-connected charging devices to automatically start and stop charging during the cheapest electricity periods.**

---

## 7. Behavioural Guarantees

Cheap Charge Timer guarantees that it will:

* Never exaggerate savings
* Never imply certainty about future outcomes
* Never pressure users through urgency or fear
* Always degrade gracefully when data is incomplete

Trust is prioritised over persuasion.

---

## 8. Fold-Into-Main-App Principle

The Cheap Charge Timer framework is designed to be folded into ChargeTimerPro as Feature 1, Feature 3, and Feature 6.

Cheap Charge Timer is built as a **complete standalone app** to enable independent release and testing (e.g., for App Store approvals and early user feedback), ensuring the fold-in process is **seamless and additive only**.

Refactoring is permitted where it:

* Improves composability
* Reduces duplication
* Aligns with canonical feature definitions

Refactoring must not:

* Change feature intent
* Introduce standalone-only assumptions
* Require conceptual rewrites during fold-in

---

*End of Cheap Charge Timer – Feature Definition & Behaviour*
