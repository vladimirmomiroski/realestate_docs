# Product Decisions

The product is a real estate discovery and intelligence platform for North Macedonia.

The MVP should combine:

- strong listing discovery
- personal and agency listing management
- map exploration
- price per square meter
- comparable listings
- practical AI features

AI is part of the first MVP and is one of the main reasons the product should feel different from a standard listings website.

---

## Product Principles

The platform should prioritize:

- speed
- usability
- clear information
- reliable data
- useful AI
- strong mobile experience

Visual design should be modern, but never at the expense of performance or simple workflows.

---

## Backend-First Decision

The backend was built first so the frontend can use real permissions, visibility rules, listing states, agency workflows, and database behavior.

The backend is complete through Chapter 9 and currently includes:

- authentication and users
- personal and agency listings
- translations and images
- search and filters
- publishing and visibility
- agency invitations and members
- agency logos
- platform-admin verification
- agency dashboards

Current verification:

```text
416/416 tests passing
```

---

## Discovery Decision

Public property discovery remains the core experience.

Users should be able to:

- search and filter listings
- sort results
- explore listings on a map
- open complete listing details
- see price per square meter
- compare similar properties
- contact the seller, agent, or agency

Chapter 10 should strengthen search, location behavior, comparable-listing discovery, and query performance.

---

## Listing Language Decision

Custom multilingual listing content is stored in the backend:

- title
- description
- address
- city
- municipality
- neighborhood

Fixed values such as property types, statuses, roles, and UI labels are localized by the frontend.

---

## Listing Management Decision

Visitors cannot create listings.

Authenticated users can create personal or agency-owned listings when permissions allow it.

New listings start as:

```text
Draft
```

Public users see only:

```text
Active listings
```

Eligible users can publish, unpublish, archive, and manage listing images.

The current three-listing limit is temporary and will be reviewed in Chapter 11.

---

## Agency Decision

Agencies are part of the MVP.

The platform supports:

- agency profiles
- agency logos
- agency-owned listings
- invitations
- Owner and Agent permissions
- member disabling
- role changes
- private agency dashboards
- platform-admin verification

Manager remains intentionally restricted until its real business role is defined.

---

## AI Decision

AI is part of the first MVP.

The product should include AI only where it gives clear practical value.

The first AI direction should focus on:

- property price analysis
- comparable-property reasoning
- listing quality assistance
- document understanding
- structured extraction from notes or voice input

AI should support user decisions, not pretend to provide guaranteed truth.

---

## AI Pricing Decision

AI pricing should not return one artificial exact number as if it were an official appraisal.

A stronger format is:

```text
Estimated price range
Confidence level
Comparable listings
Main factors affecting the estimate
```

AI pricing should depend on:

- reliable listing data
- normalized location data
- price per square meter
- comparable listings
- property type and size
- condition and features
- market history when enough data exists

The system should clearly present AI pricing as guidance, not a certified valuation.

---

## AI Readiness Decision

The next backend chapters should prepare the product for reliable AI implementation:

```text
Chapter 10 — Search and Discovery Phase 2
Chapter 11 — Data Integrity and Targeted Hardening
Chapter 12 — API Consistency, Observability, and Frontend Readiness
```

These chapters should improve:

- search quality
- location consistency
- comparable-listing discovery
- data reliability
- failure handling
- stable API contracts

Then frontend development begins.

After the frontend establishes real flows and data requirements, backend work will continue with the chapters needed for AI implementation.

A separate Python or AI service should be added only when the first real AI feature is implemented.

---

## Frontend Decision

The frontend should begin after Chapters 10–12.

Initial frontend priorities:

- homepage
- search and filters
- listing cards
- listing details
- authentication
- personal dashboard
- agency dashboard
- map exploration
- AI result presentation

The frontend should consume real backend contracts and should not duplicate backend business rules.

---

## Smart Feature Decision

Price per square meter remains the first non-AI intelligence feature.

Example:

```text
€95,000
71 m²
€1,338/m²
```

Comparable listings and AI price analysis should build on top of this structured data.

---

## Payments Decision

Payments and subscriptions are not part of the first MVP.

Possible later paid features include:

- agency plans
- promoted listings
- listing boosts
- premium analytics
- advanced AI tools

Payment rules should be designed only after the product model is clearer.

---

## Not Included Yet

These remain outside the current implementation:

- payments and subscriptions
- live chat
- mobile application
- advanced CRM
- advanced moderation
- heatmaps
- complex map drawing
- public agent profiles
- notification system
- invitation email delivery

They may be added after frontend development and real product feedback.

---

## Current Roadmap

```text
Chapter 10 — Search and Discovery Phase 2

Chapter 11 — Data Integrity and Targeted Hardening

Chapter 12 — API Consistency, Observability, and Frontend Readiness

Then begin frontend development

After frontend:
Return to the backend for the AI, authentication, background-processing,
and agency-workspace chapters required by the real product flows.
```

The exact order after frontend may change, but AI remains part of the first MVP.

---

## Product Decision Rule

This document contains only decisions that affect the overall product.

Detailed implementation rules belong in the frontend and backend repositories.

When a product decision changes:

1. Update this document.
2. Update the affected technical documentation.
3. Update tests when backend behavior changes.
4. Remove conflicting old decisions.
