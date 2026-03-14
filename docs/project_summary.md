# PureLaka Commerce Platform — Project Summary

## What This Project Is

PureLaka is a commerce analytics and reporting product built on Python and Django. It takes raw transactional data — orders, payments, refunds, subscriptions, customer activity — and turns it into structured KPI dashboards, operational monitoring surfaces, and business-facing reporting outputs.

It is not a storefront demo. It is not a Stripe integration example. It is a **transactional data product**: a system designed for the full lifecycle from data capture through quality assurance to insight delivery, structured around the way analytics and operations teams actually work.

The central design question behind PureLaka is: once the transactions exist, how do you make them reliable, visible, and useful to the business? That question shapes every layer of the project.

---

## What It Is Designed to Show

PureLaka demonstrates capability across the core disciplines of transactional data product work:

- **Transactional data modelling** — Orders, payments, subscriptions, and customer activity are structured from the ground up for reporting, not retrofitted. The schema is designed to support reporting and analytical queries while preserving transactional clarity.

- **KPI dashboard design** — A Plotly-based analytics surface with date-range filters, snapshot windows, and CSV export. Designed to show how raw records become business metrics, not just how to render a chart.

- **Payment lifecycle visibility** — Stripe-ready PaymentIntent flow with refund handling, state tracking, and a webhook-aware layer that keeps local payment state aligned with Stripe's source of truth. The payment model is the foundation for mismatch detection in the monitoring layer.

- **Subscription and recurring revenue context** — MRR tracking, churn-related metrics, and subscription lifecycle state management, structured to feed both the subscriptions dashboard and the broader KPI surface.

- **Operational monitoring and data quality** — A dedicated monitoring surface with run-on-demand checks: payment/order mismatches, invalid state transitions, negative stock conditions. Designed so new checks can be added as discrete units — reflecting how operational data quality is managed in production environments.

- **Audit coverage** — Discrete audit event records written at key action points across the order and payment lifecycle. Implemented as explicit writes rather than model signals, making the trail durable and independently queryable.

- **Controlled review workflows** — Role-based access scoped to Admin, Analyst, and Ops personas. Each sees the surfaces relevant to their function. The project is structured to be reviewer-friendly at every level, from public showcase to private technical walkthrough.

---

## Core Business Surfaces

| Surface | Purpose |
|---|---|
| **Analytics Dashboard** | KPI reporting, Plotly chart outputs, date-range filters, CSV export |
| **Monitoring Dashboard** | Operational checks, mismatch detection, issue visibility, run-on-demand |
| **Orders — Reporting View** | Order-state reporting, search, filter, staff-facing review |
| **Order Detail** | Payment and refund context, audit log, PaymentIntent state |
| **Subscriptions / MRR** | MRR tracking, churn metrics, lifecycle state management |
| **Secure Checkout** | Stripe-ready payment flow, mock mode for local development |
| **Products Catalogue** | Variants, categories, wishlist — supporting commerce context |

---

## Technical Positioning

**Stack:** Python 3.12, Django 5.x, PostgreSQL (SQLite for local development), Stripe PaymentIntents API, Plotly, native CSV export.

**Architecture:** Multi-app Django structure with clear domain ownership. The analytics and monitoring layers are designed as read-oriented consumers of the transactional core — kept separate from write paths to avoid query contention and to allow the reporting layer to evolve independently.

**Payment design:** The PaymentIntent pattern was chosen deliberately. It maps cleanly to the order-payment state model and is the architectural decision that makes mismatch detection meaningful rather than cosmetic.

**Audit design:** Audit events are written as explicit records at key action points, not derived from model signals. This makes the trail durable across schema changes and queryable as a standalone reporting surface.

The overall goal is to show how raw transactional events can become reliable reporting surfaces and operational insight — with the workflow credibility, audit coverage, and structural clarity that a professional analytics or data engineering environment would expect.

---

## Role and Industry Fit

**Best role fit**

Analytics Engineer · Data Analyst · BI / Reporting Analyst · Data Engineer (Junior / Integration) · Python / Django data-product roles

**Best industry fit**

E-commerce · Retail Analytics · Subscription Commerce · Revenue / Operations Reporting · Business-facing SaaS

---

## Portfolio Context

PureLaka is one of three intentionally scoped portfolio projects, each covering a distinct category of data work:

| Project | Data Category | Core Focus |
|---|---|---|
| **CineScope Analytics** | Event / activity data | User behaviour, event pipelines, activity analytics |
| **DataBridge Market API** | External / API-driven data | Multi-source integration, API design, data serving |
| **PureLaka Commerce Platform** | Transactional business data | Orders, payments, subscriptions, KPI reporting |

The three projects are designed together to demonstrate breadth across event-oriented, external, and transactional data — each with its own architecture, proof structure, and role alignment. They are not variations on a theme; they are three different categories of data engineering problem, solved with the tools and patterns appropriate to each.

---

## Private Technical Review

A full technical walkthrough — including complete source code, architecture discussion, and design rationale — is available privately for the right conversations.

**Available to:** mentors · serious recruiters · hiring managers · technical interview discussions

If you would like access or would like to arrange a guided walkthrough, reach out directly.

📩 [Request private review access](mailto:aminulislamkhan.tech@gmail.com)
