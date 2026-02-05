# Case Study: User → Person + SubUser Decomposition

![User → Person + SubUser decomposition](user_decomposition.png)

| Problem | Solution | Impact |
|---|---|---|
| User model mixed global identity and tenant context, causing duplication and role confusion. | Introduce Person (global) and SubUser (tenant-scoped); move tenant roles to SubUser; include both ids in JWT. | Clear separation of concerns, SaaS readiness, and simpler analytics across tenants. |

Key points:

- Person = global identity; SubUser = tenant/user within company
- JWT carries person_id + sub_user_id + company_id
- Tenant-scoped roles prevent cross-company conflicts

---

## Problem
The existing User model combined platform identity and company-specific context, leading to:
- duplicate users across companies
- difficulty managing roles and permissions
- challenges in analytics and SaaS scalability
- no clear separation of responsibility between platform admins and company admins

## Solution
- Introduce **Person** (global entity) and **SubUser** (company-scoped)
- Move roles and permissions to SubUser
- Define global platform roles for Person: `user`, `admin`, `moderator`
- Auth flow:
  1. Authenticate Person (email + password + 2FA)
  2. Authorize SubUser in selected company
  3. JWT includes `person_id`, `sub_user_id`, `company_id`, `person_roles`, `sub_user_roles`

## Impact
- Clear separation of platform and tenant responsibilities
- Multi-tenant architecture ready for SaaS
- Simplified analytics: track user across companies
- Foundation for ecosystem and enterprise integrations

## Lessons Learned
- Decoupling identity from business context reduces complexity
- Tenant-scoped roles prevent conflicts
- Early SaaS-oriented architecture simplifies future scaling

