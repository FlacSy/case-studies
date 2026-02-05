# Case Study: Domain Isolation & Shared Layer Architecture

> Clean domain boundaries with a lightweight shared layer for safe reuse.

| Problem | Solution | Impact |
|---|---|---|
| Multiple services and teams producing tangled dependencies and leaked business logic. | Enforce domain boundaries; shared layer limited to infra, utils and schemas; canonical domain layout. | Clear separations, safer reuse, easier maintenance and scaling. |

Key points:

- Domains depend on shared, but not on each other
- Shared layer contains infra and schemas only — no business logic
- Canonical layout: api, services, repositories, models, subdomains

---

## Problem
The backend consists of multiple services (`admin` and `labour`) and needed:
- clear boundaries between domains
- reusable infrastructure without leaking business logic
- scalable architecture for growth

## Solution
- Each service is a bounded context
- Canonical domain structure:

```
domain/
└── <domain_name>/
├── api/
├── services/
├── repositories/
├── models/
├── subdomains/
└── dependencies.py
```

- **Shared layer**:
  - `shared/utils` — logging, exceptions, pagination
  - `shared/schemas` — ORM models
  - `shared/database/repositories` — base CRUD without business logic

### Rules
- Domains can depend on shared, but not on each other
- Subdomains for logically close extensions
- Shared layer never contains business logic or use cases

## Impact
- Clear, verifiable domain boundaries
- Prevents hidden dependencies
- Easier to maintain and scale

## Lessons Learned
- Strict dependency rules enforce architectural discipline
- Subdomains allow flexible domain evolution without breaking other contexts
- Shared layer provides reusable infrastructure safely

