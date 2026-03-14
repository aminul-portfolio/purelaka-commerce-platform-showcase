# PureLaka Commerce Platform — Reviewer Guide

This guide is written for mentors, recruiters, and hiring managers who want to evaluate PureLaka efficiently and draw accurate conclusions about the capabilities it demonstrates.

It covers: what to look at, in what order, and what each surface is designed to prove.

---

## Before You Start — What Kind of Project This Is

PureLaka is not a storefront demo. It is not a Stripe integration walkthrough. It is a **transactional data product**: a system that takes raw commerce data — orders, payments, refunds, subscriptions — and turns it into KPI dashboards, operational monitoring surfaces, and business-facing reporting outputs.

The project is positioned at the intersection of analytics engineering, data product design, and backend development. The right lens for reviewing it is: *does this show the judgment and capability of someone who can build reliable, business-facing data systems?*

---

## Recommended Review Path

Follow this sequence for the most representative overview. Each step builds on the last.

---

### Step 1 — Analytics Dashboard

**What to open:** Analytics Dashboard

**What it shows:**
- KPI reporting structure and chart output quality
- Date-range filter design (7d / 30d / 90d / custom snapshot windows)
- CSV export availability for analyst handoff
- How raw transactional records are surfaced as business metrics

**What to look for:**
Assess whether the KPIs are meaningfully chosen — revenue trends, payment success rates, subscription MRR — and whether the chart outputs would be usable by a non-technical stakeholder. This is the primary business-facing output of the project.

---

### Step 2 — Monitoring Dashboard

**What to open:** Monitoring Dashboard

**What it shows:**
- Operational data quality awareness — not just reporting, but trust in the data
- Payment/order mismatch detection logic
- Invalid state and negative stock checks
- Run-on-demand check design

**What to look for:**
This surface separates PureLaka from projects that only report what the data says, without questioning whether the data is correct. Mismatch detection — where payment state and order state are compared and discrepancies surfaced — is a production-relevant capability most portfolio projects omit entirely. The check runner design (discrete, independently runnable units) reflects how operational data quality is managed in real analytics teams.

---

### Step 3 — Orders List and Order Detail

**What to open:** Orders List, then any individual Order Detail view

**What it shows:**
- Order lifecycle state management (pending → confirmed → fulfilled → canceled)
- Payment state tracking alongside order state
- Refund handling and state visibility
- Audit log entries at the order level

**What to look for:**
The order detail view is where the payment, refund, and audit layers come together. Look for whether the audit log is genuinely useful — timestamped, action-attributed, covering the key state transitions — rather than decorative. The separation of payment state from order state (enabling mismatch detection in Step 2) should be visible here.

---

### Step 4 — Subscriptions / MRR

**What to open:** Subscriptions / MRR Dashboard

**What it shows:**
- MRR tracking and recurring revenue visibility
- Churn-related metrics and lifecycle state management
- Subscription data structured to feed the broader analytics surface

**What to look for:**
Subscription analytics requires thinking about recurring state, not just point-in-time events. Assess whether the MRR output is structurally sound and whether churn inputs are modelled to support real analysis, not just an active/inactive flag.

---

### Step 5 — Architecture and Design Decisions

**What to review:** The `docs/` folder, this guide, and the project summary

**What it shows:**
- Multi-app Django structure with clear domain ownership
- Read-oriented analytics and monitoring layers, separated from transactional write paths
- Explicit audit event writes (not model signals) for durability and independent queryability
- PaymentIntent pattern chosen for state-model alignment, not just Stripe compliance
- Role-based access scoped to Admin, Analyst, and Ops personas

**What to look for:**
The README documents the directory structure. The more meaningful signal is in the *why* behind the choices: why PaymentIntents over a simpler payment model, why explicit audit writes rather than model signals, why the monitoring layer is a separate app. Those decisions are documented in the project summary and covered in depth in the private technical walkthrough.

---

### Step 6 — Private Technical Walkthrough *(on request)*

**What it covers:**
- Full source code access
- Architecture walkthrough with design rationale
- Service layer structure and analytics decoupling
- Monitoring check implementation and extensibility design
- Technical discussion and Q&A

**Who this is for:** Mentors, hiring managers conducting technical assessments, and serious recruiters who need to verify implementation depth beyond what a public showcase provides.

📩 [Request private review access](mailto:aminulislamkhan.tech@gmail.com)

---

## What This Project Is Designed to Prove

| Capability | Where It's Visible |
|---|---|
| Transactional data modelling for reporting | Schema design, order/payment/subscription structure |
| KPI dashboard design and business metric output | Analytics Dashboard |
| Payment lifecycle visibility and state tracking | Order Detail, Payments Layer |
| Operational monitoring and data quality awareness | Monitoring Dashboard |
| Audit trail design and durability | Order Detail audit log, Audit app |
| Subscription and recurring revenue context | Subscriptions / MRR dashboard |
| Role-based access and controlled review workflows | Admin / Analyst / Ops scoping |
| Read-oriented analytics architecture | App separation, service layer design |

---

## What This Project Is Not Claiming

It is worth being direct about scope.

- PureLaka is a **portfolio project**, not a production system. It is built to demonstrate capability and judgment, not to handle live traffic.
- The Stripe integration is **Stripe-ready** — it follows PaymentIntent patterns faithfully — but is not connected to a live Stripe account in the public showcase. Mock mode is used for local development and review.
- The full source code, including service layer implementation and monitoring check design, is available in the **private technical review**. The public showcase repo contains the architecture, documentation, and screenshots necessary to assess the project's scope and design quality.

---

## Role and Industry Fit

**Best role fit**

Analytics Engineer · Data Analyst · BI / Reporting Analyst · Data Engineer (Junior / Integration) · Python / Django data-product roles

**Best industry fit**

E-commerce · Retail Analytics · Subscription Commerce · Revenue / Operations Reporting · Business-facing SaaS

---

## Portfolio Context

PureLaka is the transactional data layer of a three-project portfolio:

| Project | Data Category | Core Focus |
|---|---|---|
| **CineScope Analytics** | Event / activity data | User behaviour, event pipelines, activity analytics |
| **DataBridge Market API** | External / API-driven data | Multi-source integration, API design, data serving |
| **PureLaka Commerce Platform** | Transactional business data | Orders, payments, subscriptions, KPI reporting |

The three projects cover different data categories by design — they are not variations on a theme. Together they demonstrate breadth across the main categories of data engineering work a professional is likely to encounter.

---

*For the full technical walkthrough or source access, reach out directly.*
*📩 [aminulislamkhan.tech@gmail.com](mailto:aminulislamkhan.tech@gmail.com)*
