# Repository Structure

## Intended monorepo layout
```text
.
├── apps/
│   ├── web/       # Next.js web application
│   ├── api/       # NestJS REST API (introduced when R2 requires it)
│   └── worker/    # Background processing (introduced when required)
├── packages/
│   ├── ui/        # Shared interface components
│   ├── shared/    # Shared types and utilities
│   └── config/    # Shared configuration
├── docs/
│   ├── decisions/
│   ├── development/
│   ├── governance/
│   ├── product/
│   └── security/
├── infrastructure/
└── scripts/
```

This is the approved organizational direction, not a requirement to create every application or package immediately.

## Implementation boundary
R1 focuses on the web prototype. Add backend, worker, persistence, and infrastructure implementation when approved R2 workflows require them. Avoid empty scaffolding and premature abstractions.

## Organization principles
- Group business logic by capability and keep module boundaries explicit.
- Keep shared packages focused; avoid circular dependencies.
- Keep database schema and migrations version-controlled when introduced.
- Keep secrets and environment-specific credentials outside version control.
- Add tests alongside the behavior they verify.
- Update this document when the implemented structure materially changes, following document governance.
