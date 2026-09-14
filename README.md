# Tradeido — Global Trade Platform

### Connect. Trade. Grow.

Tradeido is a B2B platform connecting importers/exporters with logistics service providers and manufacturers/factory owners, facilitating international trade through a secure, multi-role marketplace.

> This repository is a public overview of Tradeido. The production codebase is private, since Tradeido is a live platform handling real business and client data. This repo documents the architecture, tech stack, and product for anyone who wants to understand the engineering behind it.

**Web:** [tradeido.com](https://tradeido.com)
**iOS:** [App Store](https://apps.apple.com/gb/app/tradeido/id6757782056)
**Android:** [Google Play](https://play.google.com/store/apps/details?id=com.tradeido.app)

## Role

Co-Founder & Lead Developer — architected and built the platform end-to-end (idea → architecture → deployment).

## Who it's for

- **Importers/Exporters** — browse services and products, message providers directly
- **Service Providers** — list logistics services, manage inquiries
- **Manufacturers/Factory Owners** — list products, manage orders
- **Admins** — manage users, approve documents, monitor the platform

## Core Features

- Multi-role authentication across four distinct user types
- 7-day free trial (no credit card) for service providers and manufacturers
- Real-time chat between users
- Document management for business/compliance documents
- Stripe-integrated subscription billing
- Push notifications for real-time updates
- Offline support and multi-platform delivery (iOS, Android, Web, Desktop)

## Live Product

Tradeido is published under a registered business entity (Tradeido LLC, Sheridan, WY) and live on both major app stores:

| | iOS | Android |
|---|---|---|
| **Status** | Live | Live |
| **Downloads** | — | 1K+ |
| **Category** | Business | Business |
| **Size** | 75.8 MB | — |
| **Compatibility** | iOS 15.0+ | — |
| **Shipped versions** | 3 (v1.0 → v3.0) | Iterative releases |

### Product iteration

The app has gone through three shipped versions since its January 2026 launch, each adding real functionality based on usage:

- **v1.0 (Jan)** — initial launch: secure email + Google authentication, real-time push notifications for account status, core browse/chat/connect flow
- **v2.0 (Mar)** — smarter quick filters for finding suppliers and partners faster, more reliable direct contact links (email/phone/website) on profiles, a faster partner dashboard for approved accounts, stability fixes
- **v3.0 (Apr)** — improved notifications across payments, subscriptions, and chat, reorganized product categories, a refreshed subscription/trial experience, further performance improvements

## Architecture

Built on Clean Architecture, separating the app into three layers:

- **Presentation** — screens, widgets, state providers
- **Domain** — entities, repository interfaces, use cases
- **Data** — models, repository implementations, data sources

This separation keeps business logic independent of both the UI and the backend, making the app easier to test and evolve as the platform grows.

## Tech Stack

- **Frontend:** Flutter (Dart) — a single codebase across iOS, Android, Web, and Desktop
- **Backend:** Firebase — Firestore, Authentication, Storage
- **State Management:** Provider
- **Payments:** Stripe
- **Monitoring:** Firebase Analytics, Crashlytics, Performance Monitoring
- **Security:** Firestore security rules scoping access per user/owner, App Check, end-to-end encryption

## Engineering Notes

- Firestore security rules restrict writes to resource owners — a service provider can only write to services they own — while keeping browsing open with public read access
- CI/CD runs the automated test suite and builds on every push to the main branch
- The test suite spans unit, widget, and integration tests, with coverage tracked via lcov

---

Interested in the technical details behind a specific feature? Happy to walk through it — reach out via [LinkedIn](https://linkedin.com/in/rabas-ahmed).
