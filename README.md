# Real Estate Platform Documentation

This repository contains the shared product documentation for the Real Estate Platform.

The platform is being built as separate frontend and backend applications:

* Frontend: Next.js
* Backend: C# ASP.NET Core
* Database: PostgreSQL

## Purpose

This documentation exists to keep the whole project focused and consistent.

It defines:

* MVP vision
* product direction
* important decisions
* roadmap
* AI working context
* handoff notes between AI sessions

## Project Structure

The code repositories are separate from this documentation repository.

Recommended local workspace:

```txt
realestate_project/
  realestate-docs/
  realestate-frontend/
  realestate-backend/
```

The parent `realestate_project` folder should not be a Git repository.

Each child folder has its own Git repository.

## Main Product Direction

The app is a real estate discovery platform for North Macedonia.

Users should be able to find properties through:

* search and filters
* map exploration
* listing details pages
* basic comparison/value information

The first smart comparison feature is price per square meter.

## Current MVP Focus

The MVP focuses on:

* listing creation
* listing search/filtering
* listing details
* map-based discovery
* basic comparison
* seller upload flow later

Payments, subscriptions, advanced AI, and CRM tools are future features.
