# PureLaka Commerce Platform — Demo Walkthrough

This walkthrough is the recommended sequence for demonstrating PureLaka to a recruiter, hiring manager, or mentor — in a live screen-share, a recorded walkthrough, or a self-guided review session.

**The core principle:** lead with reporting and operational surfaces. Use commerce pages as supporting context, not as the opening.

---

## Before You Begin

**The framing to open with:**

> "PureLaka is structured as a transactional data product rather than a storefront demo. The commerce workflow — orders, payments, subscriptions — is the data source. The dashboards, monitoring surface, and reporting outputs are the point. I'll start there."

That single framing sentence does most of the positioning work before a single screen has been shown.

---

## Step 1 — Analytics Dashboard

**Open:** Analytics Dashboard

### What to show
- KPI cards and how they are derived from transactional data
- Plotly chart outputs: revenue trends, order volume, payment success rates
- Date-range filter controls and snapshot window selection
- CSV export availability for analyst handoff

### What this proves
- Business-facing KPI thinking — not just data storage, but data delivery
- Reporting orientation: the system is designed to answer business questions, not just record transactions
- Visual output quality and dashboard structure appropriate for a non-technical stakeholder

### Why it comes first
This is the clearest proof that PureLaka is an analytics and reporting product. A reviewer who sees this first understands the project's ambition immediately — a reviewer who sees the catalogue first may never fully reframe their interpretation.

### What to say
> "This is the primary business-facing output of the project. The KPIs are derived from the order, payment, and subscription data — not hardcoded. The date filters let you scope to any reporting window, and the CSV export means an analyst can pull this into Excel or a BI tool without any additional tooling."

---

## Step 2 — Monitoring Dashboard

**Open:** Monitoring Dashboard

### What to show
- Issue counts and check status indicators
- Payment/order mismatch detection results
- Invalid order-state and negative stock checks
- Run-on-demand check controls

### What this proves
- Operational maturity: the system doesn't just report data, it questions whether the data is correct
- Data quality awareness as a first-class concern, not an afterthought
- Production-minded design: mismatch detection and operational checks reflect how real analytics teams maintain data trust

### Why it matters
Most portfolio projects report what the data says. Very few ask whether the data should be trusted. The monitoring layer signals that the builder understands what happens when transactional systems go wrong — and that makes the whole system more credible.

### What to say
> "This is the monitoring surface. It runs operational checks on the underlying data — payment and order state mismatches, invalid lifecycle transitions, stock integrity. These are the kinds of checks a data or ops team would need to run regularly in a production environment. The checks are designed as discrete units so new ones can be added without touching existing logic."

---

## Step 3 — Orders List

**Open:** Orders List

### What to show
- Search and filter controls
- Order state visibility across the full lifecycle
- Staff-facing reporting layout
- Export-ready structure

### What this proves
- Transactional workflow understanding at the business process level
- Order-state lifecycle thinking: not just "orders exist" but "orders move through states that matter operationally"
- Practical reporting built around real business entities

### Why it matters
This moves the demo from abstract dashboard outputs into concrete business workflow handling — showing that the reporting layer sits on top of a properly structured transactional core.

### What to say
> "The orders list is the staff-facing reporting view. It's filterable by state, searchable by customer or reference, and export-ready. The order state — pending, confirmed, fulfilled, canceled — feeds directly into the KPI reporting and the monitoring checks we looked at earlier."

---

## Step 4 — Order Detail

**Open:** Any individual order

### What to show
- Payment state and PaymentIntent context
- Refund workflow visibility and state tracking
- Order summary and line items
- Audit log entries: timestamped, action-attributed, covering key transitions

### What this proves
- Lifecycle depth: the system tracks what happened, when, and why — not just the current state
- Payment and refund awareness at the transaction level
- Audit trail design that would be useful in a real operational or compliance context

### Why it matters
This is where the payment, refund, and audit layers come together in a single view — demonstrating transaction-level credibility, not just aggregate dashboard outputs.

### What to say
> "The order detail view brings together payment state, refund context, and the audit log in one place. The audit entries are written as explicit records at each key action — not derived from model signals — so the trail is reliable even if the schema changes. This is also where payment/order mismatches become visible at the individual transaction level."

---

## Step 5 — Subscriptions / MRR

**Open:** Subscriptions / MRR Dashboard

### What to show
- Active vs inactive subscription states
- MRR tracking and recurring revenue visibility
- Churn-related metrics and lifecycle state handling
- Connection to the broader KPI surface

### What this proves
- Subscription commerce relevance: recurring revenue requires different analytical thinking than one-time orders
- MRR as a structured output, not a derived label
- Churn inputs modelled in a way that supports real analysis

### Why it matters
Subscription analytics is a distinct domain from order analytics. Including it shows the reporting layer handles recurring-state data — not just point-in-time events — and that the project covers the full scope of modern commerce intelligence.

### What to say
> "The subscriptions view covers MRR and subscription lifecycle state. Recurring revenue data requires different modelling from order data — you're tracking state over time, not just events. The MRR output here feeds into the analytics dashboard and is structured to support churn analysis, not just active/inactive counts."

---

## Step 6 — Checkout and Product Catalogue *(supporting context)*

**Open:** Products Catalogue, then Secure Checkout

### What to show
- Product catalogue with variants and categories
- Secure checkout flow
- Stripe-ready payment integration (mock mode in local/showcase environment)

### What this proves
- The reporting and monitoring layers sit on top of a complete, realistic commerce context
- The project includes genuine operational and user-facing workflows, not synthetic data fixtures

### Why these come last
These pages are real and well-built, but they are not the strongest proof of analytical value. They confirm that the dashboards and monitoring surfaces are reporting on a credible transactional foundation — supporting the story, not leading it.

### What to say
> "The checkout and catalogue pages are here to show that the analytics and monitoring surfaces are reporting on a complete commerce system — real product variants, real cart and checkout flows, real payment lifecycle. The reporting layer isn't sitting on top of seed data; it's sitting on top of a working commerce workflow."

---

## Short Demo — Five Minutes or Less

If time is limited, use this sequence and stay at two to three minutes per surface:

| Order | Surface | Time |
|---|---|---|
| **1** | Analytics Dashboard | ~2 min |
| **2** | Monitoring Dashboard | ~1.5 min |
| **3** | Order Detail | ~1 min |
| **4** | Subscriptions / MRR | ~1 min |

Skip the Orders List and the catalogue. The dashboard, monitoring surface, and order detail carry the full argument on their own.

---

## The Message to Leave With

By the end of the demo, the reviewer should have formed this understanding without being told it directly:

> *PureLaka is a transactional data product. The commerce workflow is the source layer. The dashboards, monitoring surface, audit trail, and reporting outputs are the deliverable. The builder understands both sides — how transactional data is structured, and how it needs to be presented to be useful to a business.*

If that understanding has landed, the demo has succeeded.

---

## After the Demo

For deeper technical discussion — source code, architecture walkthrough, service layer design, monitoring implementation — a private review is available on request.

📩 [Request private review access](mailto:aminulislamkhan.tech@gmail.com)
