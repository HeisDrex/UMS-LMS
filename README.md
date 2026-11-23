# UMS-LMS

University Management System and Learning Management System.

## Project status
The project is being developed through readiness-based stages. There is no imposed calendar deadline. The current authorized focus is the R1 interactive prototype.

## Delivery stages
- **R1 — Interactive Prototype:** clickable interface, navigation, and validated user journeys.
- **R2 — Working Software Demo:** progressively functional workflows, first with fictional simulated data and then selected frontend/backend integrations.
- **R3 — Controlled Pilot:** supervised deployment, initially using simulated data. Real institutional or student data requires the necessary institutional, legal, privacy, and security approvals.
- **R4 — Production MVP:** production-ready release meeting approved functional, security, privacy, testing, and operational requirements.
- **R5 — Commercial GA:** repeatable onboarding, support, SaaS operations, and approved dedicated-deployment processes.

Progression is based on documented readiness and acceptance criteria, not merely elapsed time. A successful demo is not production readiness; a successful pilot is not commercial GA.

## Architecture direction
The accepted architectural direction is a modular monolith with bounded business modules:
- Web application: Next.js, React, TypeScript, App Router.
- Backend API: NestJS, TypeScript, Node.js LTS.
- Persistence: PostgreSQL with Prisma.
- API contract: REST documented with OpenAPI.
- Background processing: a separately organized worker responsibility.

These are architectural decisions, not a selection of hosting, cloud, payment, email, queue, storage, or other external providers. Unresolved tooling choices must remain open until reviewed and approved.

## Repository layout
See [Repository Structure](docs/development/repository-structure.md).

## Governance
The Project Owner retains final authority over scope, approvals, and merges. See [Document Governance](docs/governance/document-governance.md) and the [Decision Register](docs/decisions/decision-register.md).

## Security baseline
Tenant isolation and server-side authorization are foundational. Do not commit secrets or real student/institutional data. Early prototype and demo datasets must be fictional and synthetic. See [Security Baseline](docs/security/security-baseline.md).

## Current implementation boundary
R1 prioritizes the web prototype. Do not scaffold a complete backend, worker, or database implementation before the relevant R2 workflows require them and their scope is approved.
