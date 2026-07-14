# Real Estate Platform Documentation

This repository contains the shared product documentation for the Real Estate Platform.

The frontend and backend are maintained in separate repositories:

```text
realestate_project/
  realestate-docs/
  realestate-frontend/
  realestate-backend/
```

Each child folder is an independent Git repository. The parent `realestate_project` folder is only a local workspace container.

## Documentation

### `01-mvp-vision.md`

Defines the product vision and MVP direction.

It contains:

- the problem the platform is solving
- target users
- core product experience
- MVP scope
- important user flows
- features included in the MVP
- features intentionally postponed
- long-term product direction

### `02-product-decisions.md`

Tracks important product decisions that affect the overall platform.

Each decision should describe:

- what was decided
- why it was chosen
- alternatives considered
- consequences for the product
- whether the decision is final or may be revisited

## Documentation Boundaries

This repository should remain small and product-focused.

Detailed technical documentation belongs in the relevant code repository:

```text
Backend architecture, business rules, implementation chapters, and risks
-> realestate-backend/docs

Frontend architecture, design system, implementation decisions, and frontend context
-> realestate-frontend/docs
```

New product documents should be added only when a genuinely separate area becomes large enough to require its own file.
