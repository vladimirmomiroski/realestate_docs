# MVP Vision

## Product Idea

Build a real estate discovery platform for North Macedonia.

The platform helps users find properties through search, filters, and map exploration.

The goal is not just to show listings, but to help users understand property value better through clean information, price per square meter, and basic comparison tools.

## Primary User

A buyer or renter looking for property in North Macedonia.

## Secondary User

A registered seller, agent, or agency that wants to publish property listings.

## Main Discovery Paths

### 1. Search and Filter Path

The user can search and filter listings by:

* city
* area
* property type
* sale or rent
* price range
* size range
* rooms

After filtering, the app shows listings closest to the search criteria.

The user can open a specific listing and view full property details.

### 2. Map Exploration Path

The user can open a map view.

The map can start around Skopje as the default starting point, but the app must support all North Macedonia.

The user can:

* zoom in
* zoom out
* move around the map
* see property markers
* click a marker
* open the listing details page

## Listing Details Page

Each listing page should show:

* images
* title
* price
* size
* price per square meter
* city
* area
* address or approximate location
* map location
* property type
* sale or rent
* rooms
* bathrooms
* floor
* description
* contact information
* basic comparison section

## MVP Smart Feature

The first smart feature is price per square meter.

Example:

```txt
Apartment
71m²
€95,000
€1,338/m²
```

This helps users compare listings without needing AI in the first version.

## Basic Comparison MVP

The listing page can show similar listings based on:

* same city
* same area
* similar price
* similar size
* same property type

Advanced AI comparison is not part of the first MVP.

## Seller Upload Rule

Visitors cannot upload listings.

Only registered users with seller/agent access can create listings.

The MVP direction is:

* registered sellers can create listing drafts
* sellers can publish up to 3 listings for free
* publishing may require admin approval
* payment/subscription comes later

## MVP Includes

### Public Side

* homepage
* search/filter area
* listing results
* map view
* property markers
* listing details page
* price per square meter
* basic comparison section
* contact information

### Backend Side

* listing domain model
* PostgreSQL database
* listing API
* filtering API
* map listing data
* listing details API
* basic similar listings logic
* pagination
* validation

### Frontend Side

* homepage
* search/filter UI
* listings page
* map page
* listing cards
* map markers
* marker preview
* listing details page
* comparison section

## Not MVP

Do not build these yet:

* AI price estimation
* payment system
* subscriptions
* chat
* mobile app
* advanced CRM
* analytics dashboard
* saved searches
* favorites
* complex map drawing
* heatmaps
* advanced recommendation engine

## MVP Success Criteria

The MVP is successful when:

* listings can be created
* listings are saved in PostgreSQL
* listings appear in search results
* listings appear on the map
* users can filter listings
* users can open listing details
* users can see price per square meter
* users can see basic similar listings
