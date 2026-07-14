# MVP Vision

## Product Vision

Build a modern real estate discovery and management platform for North Macedonia.

The platform should help buyers and renters find suitable properties quickly, understand listing value more clearly, and compare options through structured data such as price per square meter.

It should also give private sellers, agents, and agencies a practical way to create, publish, and manage listings.

The long-term goal is broader than a basic listings website, but the MVP should remain focused on useful discovery, reliable listing data, and clear workflows.

## Market

Initial market:

```text
North Macedonia
```

The platform should support the whole country, while Skopje will likely contain the largest number of listings and may be the default map starting location.

## Product Principles

The product should prioritize:

```text
speed
clarity
usability
accurate information
simple workflows
strong search
mobile-friendly design
```

Visual design should be modern and recognizable, but never at the expense of performance or ease of use.

## Primary Users

### Buyer or Renter

A person looking for a property to buy or rent.

They need:

- fast search and filtering
- clear listing information
- map exploration
- price per square meter
- useful comparison information
- simple contact options

### Private Seller

A registered user who wants to create and manage personal property listings.

They need:

- draft listing creation
- image management
- publishing controls
- personal listing dashboard
- profile and contact information

### Agent or Agency

A professional or company managing multiple listings and team members.

They need:

- agency profile
- agency-owned listings
- member invitations
- Owner and Agent permissions
- listing management
- logo and branding
- private agency dashboard
- basic agency summary information

### Platform Administrator

A trusted platform user responsible for basic agency verification.

They need:

- agency approval
- agency rejection
- agency disabling

Advanced moderation tools are not part of the current MVP.

## Core Product Experience

The MVP should support four connected experiences:

```text
public property discovery
personal listing management
agency listing management
basic platform administration
```

## 1. Public Property Discovery

Visitors should be able to browse listings without creating an account.

### Search and Filters

Users should be able to search and filter by useful property criteria, including:

- city
- municipality
- neighborhood
- listing type: sale or rent
- property type: apartment or house
- price range
- property size
- rooms
- heating type
- furnishing status
- property condition
- basement
- elevator
- apartment type
- house type
- yard size

Search should remain fast and understandable.

Chapter 10 will deepen search behavior, sorting, location handling, and query performance.

### Listing Results

Search results should show compact listing cards with:

- primary image
- title
- price
- size
- price per square meter
- location
- property type
- sale or rent
- important property details

### Map Exploration

The frontend MVP should include a map view.

Users should be able to:

- zoom in and out
- move around the map
- see listing markers
- open a marker preview
- open the full listing page

The backend already stores latitude and longitude. More advanced map search behavior can be added only when the frontend proves it is needed.

### Listing Details

A listing page should show:

- images
- translated title
- translated description
- price
- currency
- area
- price per square meter
- city
- municipality
- neighborhood
- address or approximate location
- map location
- property type
- sale or rent
- rooms
- bathrooms
- apartment or house-specific details
- heating
- furnishing
- condition
- parking
- basement
- balcony information
- seller or agency contact details

Only Active listings should be publicly visible.

Draft and Archived listings should remain private.

## 2. Personal Listing Management

Authenticated users should be able to create and manage personal listings.

### Listing Lifecycle

New listings start as:

```text
Draft
```

An eligible user can:

- create a Draft listing
- upload and order images
- choose a primary image
- publish a listing
- unpublish a listing
- archive a listing
- view their own listings

Public visibility is controlled by listing status:

```text
Draft    -> private
Active   -> public
Archived -> private
```

### User Status

Current rules:

```text
PendingVerification users can prepare Draft listings.
Active users can publish personal listings.
Disabled users cannot create listings or change listing status.
```

### Listing Limit

The current backend rule limits creation to three listings per `CreatedByUserId`.

Agency listings currently count against the individual creator as well.

This rule is not considered a final long-term product decision and will be reviewed during Chapter 11.

## 3. Agency Management

Agencies are part of the expanded MVP.

### Agency Profile

An agency can have:

- name
- slug
- description
- contact information
- address
- city
- municipality
- logo
- verification status

New agencies begin as:

```text
PendingVerification
```

### Agency Roles

Current agency roles:

```text
Owner
Manager
Agent
```

Current MVP behavior:

```text
Owner -> agency administration
Agent -> agency listing work
Manager -> intentionally restricted until its real product role is defined
```

### Agency Invitations

Active agency Owners can:

- create invitations
- invite Owner or Agent roles
- list invitations
- cancel invitations

Invited users can accept through a secure invitation token.

Email delivery is not part of the current MVP. It will be added later with notifications or background jobs.

### Agency Member Management

Active Owners can:

- disable another member
- promote an Agent to Owner
- demote an Owner to Agent when another Active Owner remains
- recover an existing Manager by changing the role to Owner or Agent

An agency must not lose its final Active Owner through normal role changes.

### Agency-Owned Listings

Active Owner and Agent members can:

- create agency-owned Draft listings
- view agency dashboard listings
- publish agency listings when the agency is Active
- unpublish or archive agency listings when allowed

Private agency management remains available even when the agency is PendingVerification, Disabled, or Rejected.

### Agency Dashboard

The agency dashboard should provide:

- private agency listings
- status filtering
- total listing count
- Draft listing count
- Active listing count
- Archived listing count
- total member count
- Active member count
- actionable Pending invitation count

Advanced analytics are not part of the current MVP.

## 4. Basic Platform Administration

The MVP includes only a small agency-verification workflow.

An Active platform Admin can:

- approve an agency
- reject an agency
- disable an agency

Platform Admin is separate from agency Owner.

Changing agency status does not automatically archive or unpublish existing listings.

Advanced moderation, verification documents, notes, reports, and audit interfaces are postponed.

## Multilingual Content

User-created public listing content is stored through listing translations.

Translated listing fields include:

- title
- description
- address
- city
- municipality
- neighborhood

Fixed application labels such as statuses, roles, property types, and button text should be localized by the frontend.

Agency profile translations are not part of the current MVP and can be added later if real frontend needs justify them.

## Smart and Comparison Features

### Price Per Square Meter

The first smart comparison feature is:

```text
Price per square meter
```

Example:

```text
Apartment
71 m²
€95,000
€1,338/m²
```

This gives immediate value without requiring AI.

### Similar Listings

The frontend MVP may show similar listings based on:

- same city
- same municipality or neighborhood
- same property type
- similar price
- similar size
- same listing type

The exact matching logic belongs to the Search and Discovery chapter.

### Future Intelligence

Later versions may include:

- comparable-property analysis
- area price averages
- price-change history
- estimated property value
- document analysis
- personalized recommendations
- AI-assisted listing creation

These are not required for the first frontend launch.

## Current Implementation State

The backend is complete through Chapter 9.

Implemented backend areas include:

```text
authentication and users
user profile and avatar
personal listings
agency-owned listings
listing translations
listing images
search and filtering
publishing and visibility
agencies and members
agency invitations
member management
agency logo management
platform-admin agency verification
agency dashboard listings
agency dashboard summary
```

Current backend verification:

```text
416/416 tests passing
```

The next backend chapters are:

```text
Chapter 10 — Search and Discovery Phase 2
Chapter 11 — Data Integrity and Targeted Hardening
Chapter 12 — API Consistency, Observability, and Frontend Readiness
```

Frontend development begins after those chapters.

## MVP Includes

### Public Experience

- homepage
- listing search
- filters
- sorting
- listing cards
- listing details
- map exploration
- property markers
- price per square meter
- basic comparison or similar listings
- seller or agency contact information

### Registered User Experience

- register
- login
- personal profile
- avatar
- create Draft listing
- listing image management
- personal listing dashboard
- publish
- unpublish
- archive

### Agency Experience

- create agency
- public agency profile
- agency logo
- agency-owned listings
- invitations
- token acceptance
- member disabling
- role changes
- private listing dashboard
- basic dashboard summary

### Administration

- approve agency
- reject agency
- disable agency

## Not Part of the Current MVP

Do not add these before they are justified by the product:

- payments
- subscriptions
- agency plans
- listing boosts
- live chat
- mobile application
- advanced CRM
- client notes
- advanced analytics dashboards
- heatmaps
- complex polygon map drawing
- full recommendation engine
- AI price estimation
- automated valuation
- refresh tokens
- password reset
- email verification
- invitation email delivery
- notification system
- public agent profiles
- agency activity feed
- listing assignment workflows
- verification documents
- full moderation system

Some of these may be added after frontend development reveals real priorities.

## MVP Success Criteria

The MVP is successful when:

### Discovery

- users can find listings through search and filters
- users can browse listings on a map
- public users see only Active listings
- listing details are complete and understandable
- price per square meter is clearly visible
- similar listings or basic comparisons are useful

### Sellers

- registered users can create and manage Draft listings
- users can upload and organize listing images
- eligible users can publish, unpublish, and archive listings
- personal listings are manageable through a dashboard

### Agencies

- agencies can create and manage agency-owned listings
- Owners can invite and manage members
- Agents can perform listing work
- agency branding and public profiles are usable
- agency verification works
- the dashboard provides useful basic counts

### Quality

- frontend and backend contracts are consistent
- important authorization rules are tested
- search remains fast enough for realistic usage
- the platform works well on desktop and mobile
- the product is simple enough for real users to understand without instructions

## Long-Term Direction

The long-term platform may expand into:

- stronger property intelligence
- market analytics
- saved searches
- favorites
- notifications
- agent workspaces
- agency collaboration
- listing assignment
- document analysis
- AI-assisted workflows
- subscription plans
- paid visibility tools
- CRM features

These features should be introduced only when the core listing, discovery, and management experience is stable.