# Development Workflow

## Branching and integration
- Keep the primary branch stable and protected.
- Work on isolated, short-lived branches with descriptive names.
- Do not commit directly to the primary branch.
- Do not force-push or rewrite shared history.
- Submit changes for review with purpose, affected areas, and verification evidence.
- The Project Owner retains final merge authority.
- AI-generated changes receive the same review and verification as other changes.

## Change workflow
1. Confirm the task is within approved scope.
2. Identify affected requirements, decisions, and security boundaries.
3. Make the smallest coherent change on a working branch.
4. Run relevant checks and tests.
5. Review the diff for correctness, secrets, tenant isolation, and unintended changes.
6. Record verification evidence and unresolved risks.
7. Request owner review before integration.

## High-risk changes
Authentication, authorization, tenant isolation, finance, academic calculations, results, examinations, and sensitive data handling require heightened scrutiny and targeted negative tests.

No destructive repository operation or scope expansion is authorized by this workflow alone.
