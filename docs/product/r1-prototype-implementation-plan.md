# R1 Prototype Implementation Plan

**Status:** Draft — for Project Owner review  
**Release stage:** R1 — Interactive Prototype  
**Related approved artefacts:** R1 Prototype Backlog; R1 Sitemap and Screen Inventory; R1 Visual Direction and Design System; R1 Screen Specifications  
**Governance basis:** Master Development Instructions v2.1; accepted UL-ADR-0001 and applicable accepted technical decisions  
**Implementation boundary:** Frontend-focused interactive prototype using synthetic data. This plan does not authorize production services, real institutional data, or unapproved dependencies.

## 1. Purpose

This plan translates the approved R1 product, navigation, visual and screen specifications into a practical implementation sequence. It defines the work order, boundaries, dependencies, verification activities and owner review gates for the R1 interactive prototype.

R1 is a demonstrable prototype, not a production MVP. The objective is to let stakeholders explore the five approved journeys through coherent screens and simulated interactions.

## 2. Implementation principles

1. **Build the smallest coherent vertical journeys first.** Prioritize complete, demonstrable user journeys over disconnected collections of screens.
2. **Frontend-focused and local simulation.** Use the approved Next.js, React and TypeScript direction for the web experience. Use deterministic synthetic fixtures and local UI state to demonstrate interactions.
3. **No premature backend.** Do not add a production API, PostgreSQL database, ORM, worker, queue, object storage, live integrations or production infrastructure to R1.
4. **No real authentication.** Demo sign-in is a simulation using fictional demo credentials/accounts. It must not collect real passwords or be represented as secure authentication.
5. **Permission-aware experience.** The demo account's configured access determines its destination and visible navigation. UI checks demonstrate the intended experience only; they are not production authorization.
6. **Synthetic data only.** Names, identities, institutions, academic records, examination records, financial figures and operational metrics must be fictional.
7. **Reusable but not speculative.** Establish shared shell and primitives, then create domain components when real R1 screens need them.
8. **Accessible and responsive by design.** Incorporate the UI/UX specification's WCAG 2.2 AA target and desktop, tablet and mobile behaviours throughout implementation.
9. **Reviewable increments.** Work on the approved working branch or separately approved task branches. Keep changes small, tested and documented.
10. **Owner approval remains controlling.** Recommendations and this plan do not approve unresolved library, dependency, hosting or product-scope decisions.

## 3. Scope and non-goals

### 3.1 Included in R1

- Public institutional landing experience.
- Programme listing/detail and fictional applicant journey.
- Common login screen with simulated credential validation.
- Automatic routing to the demo account's authorized workspace.
- Authenticated application shell and role-appropriate navigation.
- Student, lecturer, institutional administration and platform administration journeys.
- Synthetic cross-screen data consistency.
- Simulated application, assignment, examination, grading, result-review and administrative status interactions where specified.
- Responsive layouts, interaction feedback and prototype validation.

### 3.2 Explicitly excluded

- Production authentication, account recovery delivery, email verification, MFA or SSO.
- Production authorization, tenant resolution or enforceable tenant isolation.
- Backend API, production database, migrations, background workers or queues.
- Real admissions, enrolment, academic, examination, finance or student-record processing.
- Real payments, payment verification, refunds or accounting.
- Live file storage, email, SMS, WhatsApp, push notifications, video or external integrations.
- Production subscriptions, monitoring, deployment management or infrastructure.
- Real institutional, applicant, student, staff or financial data.

Any proposed addition to these exclusions requires a separate scope decision and explicit Project Owner approval.

## 4. Application structure and technical boundaries

### 4.1 Approved technical direction

- Next.js with App Router.
- React.
- TypeScript.
- Feature-oriented frontend organization.
- Public pages separated from authenticated workspace layouts.
- Shared design system and application shell.
- Backend remains the owner of business rules and authorization in later releases; R1 only demonstrates the user-facing flows.

### 4.2 Decisions not made by this plan

The following remain open and must be evaluated before installation or adoption:

- Package manager and workspace tooling.
- CSS/styling implementation.
- UI component library, if any.
- Icon package.
- Charting package, if any.
- Form-validation library.
- Client state-management library, if needed.
- Animation library, if needed.
- Exact linting, formatting and test tool versions.

Prefer the smallest maintained dependency set that satisfies the approved requirements. Do not add a library merely because it appears in an earlier draft. Present material dependency choices with rationale, trade-offs, licensing/maintenance considerations and recommendation for owner approval.

### 4.3 Proposed frontend organization

This is an implementation proposal, not a mandated exact tree. Final conventions should be confirmed during project initialization.

```text
apps/
  web/
    src/
      app/
        (public)/
        (auth)/
        (student)/
        (lecturer)/
        (institution-admin)/
        (platform-admin)/
      components/
        ui/
        navigation/
        layout/
      features/
        admissions/
        academics/
        learning/
        assessments/
        examinations/
        results/
        finance/
        institution-management/
        platform-management/
      data/
        fixtures/
      lib/
        demo-auth/
        demo-routing/
        demo-state/
        utilities/
      styles/
      types/
```

Keep route groups and feature folders aligned with actual implemented journeys. Do not create empty folders for every future product module.

## 5. Demo access and workspace routing

### 5.1 Common login entry

There must be one common login experience for the relevant institution/platform context. Do not display a public workspace selector, role picker, or list of Student, Lecturer, Institutional Administration and Platform Administration choices.

### 5.2 Simulated sign-in

- Provide fictional demo accounts with clearly documented demo credentials for stakeholder testing.
- The user enters credentials on the common login form.
- The prototype matches the submitted demo account against a local, non-production fixture.
- Never store or log the entered password.
- On a valid demo account, route to that account's configured default authorized workspace.
- On invalid input, show a generic sign-in error.
- On inactive/suspended demo account, show an appropriate access/status message without entering a workspace.

### 5.3 Multiple authorized contexts

If a fictional demo account is configured with multiple active institutional memberships or authorized contexts, any context selection occurs only after sign-in and lists only those contexts assigned to that account. A single-context account goes directly to its workspace.

### 5.4 Security boundary

This is a demonstration of the intended user journey, not real authentication or access enforcement. Direct URL access may be simulated with client-side route handling for demonstration consistency, but the documentation and UI must not claim this is secure. Production routes and APIs must later enforce authorization server-side and apply tenant isolation.

## 6. Synthetic data and state model

- Maintain a small, deterministic fictional dataset in typed fixture files.
- Use stable fictional IDs to connect records across dashboards and detail pages.
- Keep the same student, lecturer, course, applicant, programme, result and finance records consistent wherever they appear.
- Separate read-only seed fixtures from temporary interactive prototype state.
- Use local component or feature state for simulated changes such as application status, assignment submission, grading draft, result approval state and notification read state.
- Do not persist sensitive or credential-like information in browser storage.
- A page refresh may reset simulated changes unless a later owner-approved requirement justifies safe demo-state persistence.
- Clearly label sample balances, payment statuses, examination outcomes and platform health indicators as illustrative or simulated.
- Keep all dates and times internally consistent with the fictional institution's configured context.

## 7. Implementation sequence and work packages

The sequence follows the approved R1.1–R1.8 backlog. Some documentation and design preparation can proceed alongside implementation, but dependent screens must not bypass the shared foundation.

### R1.1 — Product structure and design foundations

**Objective:** Establish the route skeleton, theme, shared shell and reusable interface primitives.

Tasks:
1. Confirm project initialization conventions and obtain owner approval for unresolved foundational dependencies.
2. Initialize the Next.js App Router and TypeScript web application in the monorepo.
3. Establish semantic design tokens and the fictional institution theme.
4. Implement typography, spacing, surface, border and status conventions.
5. Implement shared buttons, form fields, cards, status badges, dialogs, alerts, loading, empty and error states.
6. Implement public layout and authenticated application shell.
7. Implement responsive sidebar/drawer, header, page header and contextual navigation.
8. Verify keyboard operation, visible focus, accessible labels and basic responsive layouts.

Exit criteria:
- App builds and runs locally.
- Shared shell and core primitives are reusable.
- Public and authenticated route groups are separated.
- Responsive navigation works at agreed viewport sizes.
- No unapproved dependency is introduced.

### R1.2 — Public institutional experience and applicant journey

**Objective:** Demonstrate discovery through a fictional application outcome.

Tasks:
1. Build public landing page.
2. Build programme listing and detail pages.
3. Build admissions information and application instructions.
4. Build fictional applicant registration/application steps and validation.
5. Demonstrate review, simulated submission and application status.
6. Connect existing-applicant and general login entry points to the common login experience.

Exit criteria:
- Visitor can navigate from landing page through programme information into the sample application.
- Validation and simulated submission feedback work.
- No real application is transmitted or stored.

### R1.3 — Common demo login and workspace routing

**Objective:** Provide controlled entry into the four distinct authenticated workspaces.

Tasks:
1. Build the common login page using the correct fictional institution/platform context.
2. Define synthetic demo-account fixtures and permitted default destinations.
3. Implement local simulated credential matching without retaining passwords.
4. Route successful demo accounts directly to their authorized workspace.
5. Implement post-login context selection only for demo accounts explicitly configured with multiple authorized contexts.
6. Implement invalid, inactive and unauthorized demo-account feedback.
7. Implement sign-out and return-to-login behaviour for the prototype.
8. Apply the shared authenticated shell and account menu.

Exit criteria:
- No public workspace selector or role picker exists.
- A valid demo account enters only its configured destination.
- Multiple-context selection, if demonstrated, appears only after sign-in and is restricted to configured contexts.
- Invalid/inactive accounts do not enter a workspace.
- Demo-only limitations are visible and documented.

### R1.4 — Student learning journey

**Objective:** Demonstrate the core student experience.

Tasks:
1. Build student dashboard.
2. Build course list and course workspace.
3. Build sample learning material views.
4. Build assignment detail and simulated submission.
5. Build sample examination instructions/question flow and simulated submission.
6. Build fictional published results view.
7. Build read-only fictional finance view and sample receipt presentation.
8. Connect announcements, activities and notifications.

Exit criteria:
- Student can complete the principal dashboard → course → material → assignment/examination → results/finance walkthrough.
- Synthetic data remains consistent.
- Simulated actions show explicit status feedback.

### R1.5 — Lecturer teaching journey

**Objective:** Demonstrate course delivery and assessment workflows.

Tasks:
1. Build lecturer dashboard and schedule.
2. Build assigned course views.
3. Demonstrate sample learning material management.
4. Demonstrate assignment creation/editing.
5. Build submission list and submission detail.
6. Demonstrate draft grading and feedback.
7. Demonstrate result preparation and submission for approval.

Exit criteria:
- Lecturer sees only assigned sample courses and relevant sample submissions.
- Grading and result states are distinguishable.
- Lecturer submission does not imply authority to publish official results.

### R1.6 — Institutional administration journey

**Objective:** Demonstrate institution-level oversight and administration.

Tasks:
1. Build institutional dashboard.
2. Build admissions queue and sample application review.
3. Build student/staff directory and fictional profile views.
4. Build academic structure, programme and course views.
5. Demonstrate lecturer assignment where included.
6. Build result review/approval flow.
7. Build read-only finance overview and sample reports.

Exit criteria:
- Administrator can inspect sample institutional records and complete the principal review journey.
- Permission-specific navigation is represented.
- Platform administration functions are absent from this workspace.
- Financial information remains illustrative; no real transaction occurs.

### R1.7 — Platform administration journey

**Objective:** Demonstrate platform-level operations distinctly from institutional operations.

Tasks:
1. Build platform overview with illustrative metrics.
2. Build institution list and detail views.
3. Demonstrate fictional institution status/configuration presentation.
4. Present integration, deployment or health information only where included in the approved R1 screen scope and clearly labelled illustrative.

Exit criteria:
- Platform operator has a distinct workspace and sample institution overview.
- No real institution, subscription, deployment or provider configuration is changed.
- Platform access is not exposed through institutional navigation.

### R1.8 — Integration, responsive behaviour and prototype validation

**Objective:** Connect the journeys and validate the prototype as a coherent demonstrable product.

Tasks:
1. Connect cross-workspace and within-workspace navigation where authorized.
2. Remove dead-end links from principal journeys or label planned destinations clearly.
3. Validate desktop, tablet and mobile layouts.
4. Test forms, validation, dialogs, loading, empty, error, success and denied-access states.
5. Conduct keyboard and accessibility checks against the UI/UX target.
6. Run each of the five approved journeys from beginning to end.
7. Record defects, usability observations, limitations and deferred work.
8. Prepare a demonstration guide and R1 acceptance evidence.

Exit criteria:
- Five principal journeys are demonstrable.
- No critical navigation dead ends remain.
- Responsive behaviour is reviewed.
- Prototype-only actions and synthetic data are clearly identified.
- Known limitations and test evidence are recorded for owner review.

## 8. Verification and quality gates

Each work package should be reviewed before the next dependent package is treated as complete.

Minimum checks:
- TypeScript type checking.
- Linting and formatting checks after tooling is approved.
- Production build.
- Component and feature-level checks for important interactions.
- Browser walkthrough of affected routes.
- Responsive checks at mobile, tablet and desktop widths.
- Keyboard navigation and visible focus checks.
- Positive and negative demo-account routing checks.
- Cross-journey synthetic data consistency checks.
- Regression walkthrough of previously accepted journeys.

Security-sensitive prototype boundaries to verify:
- No real credentials or personal records are used.
- No password is persisted or logged.
- No UI claim suggests production authentication, authorization, tenant isolation or payment processing.
- No unapproved external service or production data source is connected.

Specific testing libraries and automated test coverage targets remain subject to technical evaluation and owner approval under the dependency/tooling policy.

## 9. GitHub workflow and review gates

- Continue development away from `main`; do not commit directly to `main`.
- Use the approved project working branch for planning artefacts and isolated task branches for implementation when appropriate.
- Keep commits focused and descriptive.
- Relate changes to an R1 work package and its acceptance criteria.
- Include test/build evidence and screenshots where useful.
- Review generated code for correctness, maintainability, accessibility and scope compliance.
- Do not merge, create a pull request, force-push, rewrite history or perform destructive Git operations without explicit Project Owner approval.
- The Project Owner retains final integration/merge authority.

## 10. Owner review and approval gates

| Gate | Review evidence | Owner decision |
|---|---|---|
| G0 — Implementation readiness | This plan, open dependency decisions, project setup proposal | Approve implementation plan and any proposed dependency choices |
| G1 — Foundation | Running app, route skeleton, theme, shared shell, responsive/accessibility evidence | Accept R1.1 foundation |
| G2 — Public and access journeys | Public/applicant flow, common login, demo-account routing behaviour | Accept R1.2–R1.3 |
| G3 — Student journey | Student dashboard and complete sample learning path | Accept R1.4 |
| G4 — Lecturer journey | Teaching, grading and result-submission demonstration | Accept R1.5 |
| G5 — Institutional operations | Admissions, records, academic and finance overview | Accept R1.6 |
| G6 — Platform operations | Distinct platform workspace and institution overview | Accept R1.7 |
| G7 — R1 validation | Five journey walkthroughs, responsive/accessibility checks, defect/limitation log | Accept or request revisions to R1 |

Approval of this plan alone does not approve unresolved dependencies, production capabilities, new product scope or merging to `main`.

## 11. Open implementation decisions

The following should be brought to the Project Owner as focused recommendations before implementation needs them:

1. Package manager and monorepo workspace tooling.
2. Styling approach and whether to use a component library.
3. Icon family/package.
4. Form validation approach.
5. Test tooling appropriate to the R1 frontend prototype.
6. Exact fictional institution identity and demo-account fixture details, if not already supplied.

Do not block the entire plan on speculative future tools. Resolve each decision when its implementation dependency is reached, with rationale and approval where required.

## 12. R1 completion standard

R1 is ready for Project Owner acceptance when all five journeys can be demonstrated coherently, the common login routes synthetic accounts without a public workspace selector, the four authenticated workspaces remain distinct, responsive and accessibility checks have been performed, all data/actions are clearly synthetic or simulated, and known limitations are documented.

R1 acceptance does not establish production readiness, security certification, pilot authorization or commercial GA readiness.
