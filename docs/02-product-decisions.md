# Product Decisions

The product is a real estate discovery platform for North Macedonia.

The first version should focus on helping users:

* search listings
* filter listings
* compare basic listing value
* open listing details
* understand price per square meter

The first version should not become a full CRM, AI platform, or marketplace with payments.

---

## MVP priority

The MVP priority is:

1. Public listing discovery
2. Search and filters
3. Listing details
4. Price per square meter
5. Map exploration
6. Basic similar listings

Advanced seller tools, AI tools, subscriptions, and analytics come later.

---

## Backend-first decision

The backend foundation was built first to avoid frontend mock data becoming disconnected from real behavior.

Backend foundation includes:

* Clean Architecture
* PostgreSQL
* EF Core
* listing domain model
* translations
* listing create/read endpoints
* filtering and pagination
* auditing fields
* integration tests
* CORS for frontend

Frontend work should now use the real backend API instead of fake long-term mock data.

---

## Listing language decision

Fixed app labels such as property type, listing type, and status are translated in the frontend.

Examples:

* Apartment / Стан
* House / Куќа
* Sale / Продажба
* Rent / Изнајмување

Custom listing text is stored in the backend using listing translations.

Examples:

* title
* description
* city
* neighborhood
* address line

This allows each listing to have Macedonian and English text.

---

## First property types

The first supported property types are:

* Apartment
* House

Other types such as land, office, retail, warehouse, and garage are intentionally delayed.

Reason: keep MVP simple and avoid overbuilding the domain model too early.

---

## First smart feature

The first smart feature is price per square meter.

Example:

```txt
€95,000
71m²
€1,338/m²
```

This gives users immediate value without requiring AI in the first MVP.

---

## AI feature decision

AI is not part of the first MVP core.

AI features may come later, such as:

* document analyzer
* listing text helper
* average price assistant
* agent notes helper
* voice note to structured listing data
* comparison assistant

The MVP should first prove that listings, search, filters, and listing details work well.

---

## Seller upload decision

Visitors cannot upload listings.

Only registered sellers, agents, or agencies should be able to create listings later.

Initial seller model idea:

* registered sellers can create listing drafts
* sellers can publish up to 3 listings for free
* publishing may require admin approval
* payments and subscriptions come later

Auth and seller dashboards are not part of the immediate frontend start unless needed.

---

## Frontend decision

The frontend should start after the backend foundation is stable.

Frontend should first build:

* homepage
* listing search page
* listing cards
* filters UI
* listing details page
* API connection to backend

Map view can come after the first listing/search UI works.

---

## What not to build yet

Do not build these in the MVP foundation phase:

* payment system
* subscriptions
* chat
* mobile app
* advanced CRM
* analytics dashboard
* AI price estimation
* saved searches
* favorites
* heatmaps
* complex map drawing
* advanced recommendation engine

---

## Current phase

Current phase:

```txt
Backend foundation complete.
Frontend MVP planning and setup next.
```

Backend should not continue expanding unless the frontend needs a backend change.
