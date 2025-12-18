# Data_Sources_and_Truth_Model.md
Authoritative definition of data usage, certainty, and truth handling in ChargeTimerPro
---
## Governance Clause
This document is governed by **ChargeTimerPro Constitution v1.3** and **Feature_List_v1_0.md**.
- It may elaborate or describe implementation, process, or design details for **canonical product features** only.
- It must not add, remove, subdivide, or redefine any **product feature scope**.
- It must not introduce new **product features, user flows, or capabilities** outside the canonical feature list.
- Any conflict with the Constitution or Feature List is invalid — **the Constitution prevails**.
Last reviewed: December 17, 2025
---
## 1. Purpose
This document defines how ChargeTimerPro understands, classifies, and presents data.
Its goals are to:
- Enforce truthfulness and honesty in all user-facing information
- Prevent accidental fabrication, exaggeration, or false certainty
- Define acceptable data sources and confidence levels
- Ensure uncertainty is handled explicitly and calmly
This document applies to **all features and all data flows**.
---
## 2. Core Principle: Truth Over Completeness
ChargeTimerPro **must deliver accurate partial truth** and **must never deliver confident false completeness**.
If high-confidence data is unavailable:
- The app must reduce precision
- The app must surface uncertainty
- The app must avoid implication or assumption
Silence **must be chosen** over misleading certainty.
---
## 3. Data Classification Model
All data used by the app must be classified into one of the following categories.
### 3.1 Direct Data
Data obtained directly from an authoritative source.
Examples:
- Electricity tariff pricing from a provider
- Vehicle-reported battery percentage
- Charger-reported availability (where supported)
Rules:
- May be presented directly to the user
- Must include freshness context when relevant
- Must not be altered beyond normalisation
---
### 3.2 Derived Data
Data calculated by the app using direct data and transparent logic.
Examples:
- Savings calculations
- Distance-based battery sufficiency estimates
- Cheap charging windows derived from tariffs
Rules:
- Must be explainable
- Must not imply greater certainty than inputs allow
- Must degrade gracefully if inputs are missing or stale
---
### 3.3 Inferred Data
Data estimated using indirect signals or assumptions.
Examples:
- Estimated reach based on battery percentage and distance
- Confidence estimates for trip feasibility
Rules:
- Must be clearly framed as estimates
- Must never be presented as guaranteed outcomes
- Must always err on the side of caution and never overestimate capability
---
### 3.4 Unsupported Data
Data that cannot be justified with a defensible source.
Examples:
- Guessed battery state
- Simulated charger availability
- Assumed driving behavior
Rules:
- Must never be used
- Must never be presented
- Must never influence decisions
---
## 4. Confidence Levels & Presentation
All user-facing data must implicitly or explicitly fall into one of these confidence levels:
- **High confidence** — direct, fresh, authoritative data
- **Medium confidence** — derived or slightly stale data
- **Low confidence** — inferred or partially incomplete data
Presentation rules:
- Lower confidence **must use** calmer language
- Icons, wording, or placement **must** reflect uncertainty
- The app **must never** visually overstate confidence
---
## 5. Feature-Level Data Expectations
### 5.1 Cheap Charge Time Alerts
- Relies on direct tariff data and derived price windows
- Must clearly indicate when pricing is estimated or time-limited
- Savings calculations must state comparison baseline implicitly or explicitly
---
### 5.2 Charger Map
- Uses direct charger listings and availability where supported
- Reliability indicators must be based on observed outcomes, not assumptions
- Absence of data must never be framed as availability
---
### 5.3 Savings Tracker
- Uses derived calculations only
- Historical data must remain immutable once recorded
- Totals must reflect calculation method consistently
---
### 5.4 Apple Integration
- Displays existing app state only
- Must not introduce new calculations or assumptions
- Must respect the same confidence rules as the main app
---
### 5.5 Battery Alerts
- Combines direct battery data with derived distance logic
- Alerts must trigger sufficiently early to enable calm decision-making
- Language must reflect guidance, not prediction
---
### 5.6 AutoCharge
- Acts only on explicit, high-confidence conditions
- Must fail safely when data is incomplete or stale
- No automatic action may occur on inferred-only data
---
### 5.7 Trip Confidence
- Focuses on sufficiency, not optimisation
- Must clearly distinguish “possible” from “comfortable”
- Must never guarantee successful arrival
---
### 5.8 Family / Fleet Awareness
- Shares awareness, not raw telemetry
- Must minimise frequency and detail
- Must never imply tracking or surveillance
---
## 6. Data Freshness Rules
Where time sensitivity matters:
- Data must include an implicit freshness window
- Stale data must be treated as lower confidence
- Outdated data must not silently persist
---
## 7. Non-Surveillance Enforcement
ChargeTimerPro must not:
- Continuously track movement
- Maintain background location histories
- Collect data without a clear feature-level need
Data use must be:
- Intentional
- Minimal
- Feature-scoped
---
## 8. Failure & Degradation Strategy
When data is unavailable or unreliable:
- Must reduce functionality
- Must reduce precision
- Must preserve calm guidance
The app must never:
- Compensate by guessing
- Mask failure with confidence
- Escalate urgency artificially
---
## 9. Change Discipline
Any change that:
- Introduces a new data source
- Alters confidence classification
- Changes how uncertainty is presented
Must be:
- Proposed explicitly
- Audited for constitutional compliance
- Approved before implementation
---
## 10. Summary
ChargeTimerPro treats data as **a responsibility, not a resource**.
Every feature must:
- Know what it knows
- Know what it does not know
- Communicate that difference clearly
Trust is built by restraint, not bravado.
---
— End of Data_Sources_and_Truth_Model.md —