# Case Studies: Proova Backend Architecture

This repository contains real-world backend architecture decisions, written as RFCs and ADRs.  
All code examples are redacted or simplified for confidentiality.

## Included Case Studies

Below is a quick visual index of the case studies. Click a card to open the full write-up.

| Case | Summary |
|---:|:---|
| [User → Person + SubUser Decomposition](01_user_decomposition/README.md)<br>![User → Person + SubUser decomposition](01_user_decomposition/user_decomposition.png) | Multi-tenant identity management and SaaS readiness — decoupling global identity from tenant-scoped roles. |
| [WebSocket Event Delivery System](02_ws_event_delivery/README.md)<br>![WebSocket Event Delivery architecture](02_ws_event_delivery/ws_event_delivery.png) | Transactional outbox → queue → WS gateway pipeline with deduplication, retries and topic-based subscriptions. |
| [Domain Isolation & Shared Layer Architecture](03_domain_shared_layer/README.md) | Architectural rules for bounded contexts, shared utilities and safe reusable infrastructure. |
| [Temporary File Upload Handling](04_temp_file_upload/README.md)<br>![Temporary file upload flow](04_temp_file_upload/temp_file_upload.png) | Multi-step uploads with temporary storage and Redis metadata, safe finalization to permanent storage. |

## Purpose

Each case demonstrates:
- the problem and constraints
- the chosen solution and architecture
- the impact and lessons learned

This repository is intended to showcase engineering thinking, system design, and architectural decisions.

