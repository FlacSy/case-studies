# Case Studies: Proova Backend Architecture

This repository contains real-world backend architecture decisions, written as RFCs and ADRs.  
All code examples are redacted or simplified for confidentiality.

## Included Case Studies

1. [User → Person + SubUser Decomposition](01_user_decomposition/README.md) — Multi-tenant identity management and SaaS readiness.
2. [WebSocket Event Delivery System](02_ws_event_delivery/README.md) — Transactional outbox + queue + WS Gateway, with deduplication and retries.
3. [Domain Isolation & Shared Layer Architecture](03_domain_shared_layer/README.md) — Safe separation of bounded contexts and reusable infrastructure.
4. [Temporary File Upload Handling](04_temp_file_upload/README.md) — Multi-step form uploads with temporary storage and Redis metadata.

## Purpose

Each case demonstrates:
- the problem and constraints
- the chosen solution and architecture
- the impact and lessons learned

This repository is intended to showcase engineering thinking, system design, and architectural decisions.

