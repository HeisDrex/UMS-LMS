# UL-ADR Decision Register

This register indexes decisions accepted by the Project Owner in project discussions. Formal individual ADR documents are to be recorded progressively. This register does not claim that those full records have already been created.

| ID | Decision area | Accepted direction |
|---|---|---|
| UL-ADR-0001 | Delivery stages | R1 interactive prototype through R5 commercial GA; readiness-based progression |
| UL-ADR-0002 | Governance | Defined document precedence, owner authority, and approval controls |
| UL-ADR-0003 | Requirements | PRD as primary product-requirements source; traceable, testable requirements |
| UL-ADR-0004 | Architecture | Modular monolith with bounded business modules |
| UL-ADR-0005 | Deployment models | Shared SaaS and dedicated deployments from one core product |
| UL-ADR-0006 | Tenant isolation | Strict server-enforced, default-deny institution isolation |
| UL-ADR-0007 | Identity and membership | One shared-SaaS identity may hold multiple institution-scoped memberships |
| UL-ADR-0008 | Tenant resolution | Institution subdomains primary; verified custom domains supported |
| UL-ADR-0009 | Language/runtime | TypeScript and Node.js LTS |
| UL-ADR-0010 | Database | PostgreSQL |
| UL-ADR-0011 | Data access | Prisma ORM and controlled versioned migrations |
| UL-ADR-0012 | Backend | NestJS with initial Express adapter |
| UL-ADR-0013 | Frontend framework | Next.js, React, TypeScript, App Router, hybrid rendering |
| UL-ADR-0014 | API | REST, OpenAPI, initial version prefix /api/v1 |
| UL-ADR-0015 | Authentication | Centralized credentials and secure server-managed sessions; privileged platform-admin MFA |
| UL-ADR-0016 | Authorization | Hybrid RBAC and ABAC; default-deny and server-side enforcement |
| UL-ADR-0017 | Audit | Structured, append-only audit records for sensitive and critical actions |
| UL-ADR-0018 | Background processing | Durable queue-based asynchronous and scheduled processing |
| UL-ADR-0019 | Files | Private object storage with PostgreSQL metadata and authorized access |
| UL-ADR-0020 | Integrations | Provider-independent adapters and standardized internal contracts |
| UL-ADR-0021 | Academic policy | Configurable institution-scoped academic rules and versioned grading policy |
| UL-ADR-0022 | Finance | Configurable institution-scoped fees, billing, ledger, and controlled adjustments |
| UL-ADR-0023 | Exams/results | Controlled, auditable examination and results lifecycle |
| UL-ADR-0024 | Repository | Monorepo organized into applications, packages, docs, infrastructure, and scripts |
| UL-ADR-0025 | Branching/review | Protected primary branch, isolated branches, review, owner-controlled merge |
| UL-ADR-0026 | Dependencies | Reproducible, controlled dependencies and tooling |
| UL-ADR-0027 | Testing | Risk-based testing with emphasis on security and critical business rules |
| UL-ADR-0028 | CI | Automated quality gates required before integration |
| UL-ADR-0029 | Frontend organization | Feature-oriented frontend with shared design system and controlled API client |
| UL-ADR-0030 | Environments/data | Separate environments; synthetic data by default; real data gated by approvals |
| UL-ADR-0031 | Hosting/residency | Cloud-first, region-aware approach; no provider or region selected |
| UL-ADR-0032 | Operations | Central observability, protected backups, tested recovery, defined RPO/RTO |
| UL-ADR-0033 | Providers | Risk-based third-party assessment and explicit owner approval |

Provider, hosting region, package manager, UI library, CSS approach, state/form libraries, queue technology, storage vendor, CI platform, and other expressly open choices must not be treated as selected by this register.
