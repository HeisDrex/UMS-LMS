# Backend API

Planned backend: NestJS, TypeScript, and Node.js LTS, initially using the Express adapter.

Introduce this application when approved R2 workflows require actual backend integration. The API is responsible for validation, business rules, authentication/session handling, tenant resolution, and server-side authorization.

The accepted API direction is REST documented with OpenAPI and an initial `/api/v1` prefix. Do not expose secrets or rely on client-side access checks.
