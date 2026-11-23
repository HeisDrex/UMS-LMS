# Security Baseline

## Foundational principles
- Enforce tenant isolation and authorization on the server.
- Deny access by default.
- Treat all client input, including institution or tenant identifiers, as untrusted.
- Apply least privilege and separation of duties.
- Protect credentials, secrets, personal data, academic records, and financial information.
- Log security-sensitive actions without recording secrets or unnecessary personal data.

## Tenant isolation
Institution boundaries apply consistently across APIs, database access, files, background jobs, notifications, reports, exports, caches, and integrations. Tenant context must be resolved and validated server-side. Cross-institution access is prohibited unless a narrow, explicitly authorized, auditable exception exists.

## Data handling
- Do not commit secrets, credentials, private keys, or production configuration.
- Do not put real student or institutional data in source control, screenshots, fixtures, or early demos.
- Use fictional synthetic data for development, testing, and early demonstrations.
- Real institutional/student data may be introduced only after the necessary institutional, legal, privacy, and security approvals and safeguards.
- Keep sensitive storage private and access-controlled.

## Verification
Test both authorized and unauthorized paths, including cross-tenant access attempts. Security checks must cover APIs and non-HTTP execution paths such as workers and exports. Report risks rather than silently weakening controls to make a feature work.
