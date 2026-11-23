# Document Governance

## Authority and precedence
Resolve project conflicts in this order:
1. Applicable laws and regulatory obligations.
2. Project Owner directives and explicitly approved scope.
3. Accepted UL-ADRs, within their approved scope.
4. Reconciled requirements and supporting specifications.
5. Remaining drafts and unapproved documents.

A lower-level document cannot silently override a higher-level authority. Conflicts at the same level, or uncertainty about interpretation, must be referred to the Project Owner. AI tools and developers may recommend resolutions but may not independently approve them.

## Document status
- **Draft:** being prepared; not authoritative.
- **Under Review:** submitted for review; not yet approved.
- **Approved/Baselined:** explicitly approved by the Project Owner.
- **Superseded/Retired:** retained for traceability but no longer current.

Only the Project Owner approves foundational requirements and material scope changes.

## Changes
Material changes to approved documents require a revision/version, date, change summary, rationale, affected decisions, and explicit owner approval. Non-substantive spelling, formatting, or clarity edits are permitted only when meaning is unchanged.

Accepted UL-ADRs are authoritative within their scope. Affected specifications should be updated to reflect them. Reconciliation alone does not constitute approval.

## Responsibilities
The Project Owner owns project documents and final approvals. AI may research, draft, review, reconcile, and recommend when instructed. Developers maintain assigned documents within approved boundaries. Ownership, maintenance, and approval are distinct responsibilities.
