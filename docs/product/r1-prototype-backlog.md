# R1 Interactive Prototype Backlog

**Status:** Approved by Project Owner  
**Release stage:** R1 — Interactive Prototype  
**Related decision:** UL-ADR-0001  
**Source basis:** Product Requirements Document (PRD), UI/UX Design Specification, and accepted project governance decisions

## 1. Purpose and scope

This backlog translates the initial demonstration and design priorities in the source documents into an ordered, reviewable R1 work plan.

R1 is an interactive prototype. The PRD calls the initial demonstration "Release 0: Interactive Demonstration". For project planning, that demonstration is treated as the first demonstrable outcome within the accepted R1 stage; it is not the production MVP.

The prototype should let stakeholders explore principal user journeys through realistic fictional institutional data. It is not a production implementation of authentication, admissions, learning management, examinations, results, finance, or multi-tenant security.

## 2. R1 guardrails

- Use a fictional university identity, fictional sample students and staff, and synthetic programmes, departments, courses, academic records, and financial records.
- Do not use real student, staff, applicant, institutional, or financial records.
- Do not process real payments or connect a live payment gateway.
- Simulate interactions locally in the prototype; clearly distinguish simulated states from completed server operations.
- A prototype login or role selector is a demonstration mechanism, not secure authentication.
- UI navigation and hidden controls are not authorization controls. Backend authorization and tenant isolation remain mandatory for later functional releases.
- Do not introduce a full backend, database, worker, external integrations, or production infrastructure merely to make R1 appear more complete.
- Keep advanced settings and secondary screens behind the principal workflows until those workflows have been validated.

## 3. Target demonstration roles and journeys

| Journey | Principal experience | R1 demonstration outcome |
|---|---|---|
| Prospective applicant | Public portal → programmes → application registration → application status | A visitor can explore programmes and complete a fictional application flow |
| Student | Student dashboard → courses → course workspace → materials → assignment → examination → results → finance | A student can explore an end-to-end academic experience with sample records |
| Lecturer | Lecturer dashboard → assigned course → materials/assignment → submission review → grading → result submission | A lecturer can demonstrate course delivery and academic assessment |
| Institutional administrator | Administration dashboard → admissions → student directory → academic structure/courses → result approval → finance overview | An administrator can explore key institutional operations |
| Platform operator | Platform overview → institution management | An operator can inspect a fictional platform-level overview and institution record |

These journeys are representative R1 paths, not a commitment to implement every production capability in the source documents.

## 4. Ordered work packages

### R1.1 — Product structure and design foundations

**Objective:** Establish the common interface foundation before building role-specific screens.

Tasks:
- R1.1.1 Create the product sitemap and route inventory for public and authenticated experiences.
- R1.1.2 Define the fictional institution identity and sample content conventions.
- R1.1.3 Define semantic design tokens for colour, typography, spacing, surfaces, borders, and status.
- R1.1.4 Define the shared authenticated application shell: sidebar, header, page title, contextual actions, and content area.
- R1.1.5 Define reusable cards, tables, badges, tabs, forms, dialogs, alerts, empty states, and feedback patterns.
- R1.1.6 Specify desktop, tablet, and mobile navigation/layout behaviour.
- R1.1.7 Apply accessibility practices during component design, using WCAG 2.2 AA as the UI specification's target.

Acceptance:
- The route/sitemap and role navigation are documented.
- Shared components have consistent states and visual behaviour.
- Desktop and mobile patterns are defined.
- Keyboard focus, labels, contrast, and status communication are considered from the start.

### R1.2 — Public institutional experience and applicant journey

**Objective:** Demonstrate how a prospective student discovers a programme and begins an application.

Tasks:
- R1.2.1 Build the fictional institution landing page.
- R1.2.2 Build a programme listing and programme detail view.
- R1.2.3 Present admission requirements and application instructions using sample content.
- R1.2.4 Build a fictional applicant registration/application form.
- R1.2.5 Show application review/submission feedback and a sample application status.
- R1.2.6 Provide applicant and existing-user login entry points.

Acceptance:
- A visitor can move from the landing page to programme details and into a sample application.
- Required fields and validation feedback are demonstrated.
- Submission produces an explicit simulated confirmation/status.
- No real application is transmitted or stored by a production service.

### R1.3 — Demonstration access and role workspaces

**Objective:** Let a stakeholder enter and explore each role's workspace.

Tasks:
- R1.3.1 Build one common branded demonstration login screen; do not display a public workspace selector or role picker.
- R1.3.2 Provide fictional demo accounts and credentials for student, lecturer, institutional administrator, and platform operator journeys.
- R1.3.3 After simulated sign-in, route each demo account directly to its configured authorized workspace.
- R1.3.4 If a demo account has multiple configured authorized institutional contexts, show a restricted context selector only after sign-in.
- R1.3.5 Build the shared authenticated layout and account-specific navigation.
- R1.3.6 Provide profile, notification, and workspace-context presentation using sample data.

Acceptance:
- Each principal role has a distinct, navigable workspace.
- Users enter through the common login form; no public workspace selector or role picker is presented.
- Successful demo sign-in routes to the account's configured authorized workspace.
- Any multiple-context selector appears only after sign-in and contains only contexts assigned to that demo account.
- The interface clearly identifies the flow as a simulation and does not imply production authentication or authorization.

### R1.4 — Student learning journey

**Objective:** Demonstrate the student's core academic and learning experience.

Tasks:
- R1.4.1 Build the student dashboard with academic overview, registered courses, upcoming activities, assignments, examination schedule, results, financial status, announcements, and learning progress.
- R1.4.2 Build the course list.
- R1.4.3 Build a course workspace with sample modules and learning materials.
- R1.4.4 Demonstrate viewing or opening a sample learning resource.
- R1.4.5 Build an assignment detail and simulated submission flow.
- R1.4.6 Build a sample examination interface with clear instructions, question navigation, and simulated submission confirmation.
- R1.4.7 Build a results view using fictional published results.
- R1.4.8 Build a read-only finance view showing fictional obligations, balances, and payment history.

Acceptance:
- A student can navigate from the dashboard into a course, access sample material, submit a simulated assignment, explore an examination, and view sample results and finance records.
- Important actions show loading/processing, success, validation, or error feedback as appropriate.
- The examination and finance interfaces are demonstrative only; no real exam attempt or payment is processed.

### R1.5 — Lecturer teaching journey

**Objective:** Demonstrate course delivery and assessment from the lecturer's perspective.

Tasks:
- R1.5.1 Build the lecturer dashboard with assigned courses, schedules, pending submissions, and student progress summaries.
- R1.5.2 Build assigned course management views.
- R1.5.3 Demonstrate organizing/publishing sample learning materials.
- R1.5.4 Demonstrate creating or editing a sample assignment.
- R1.5.5 Build a submission list and submission detail view.
- R1.5.6 Demonstrate grading a fictional submission and providing feedback.
- R1.5.7 Demonstrate preparing and submitting sample results for approval.

Acceptance:
- A lecturer can navigate from an assigned course to its materials and assignment submissions.
- A fictional submission can be reviewed and assigned a sample mark/feedback.
- A result can be shown moving into a submitted/pending-approval state.
- No actual student assessment record is created.

### R1.6 — Institutional administration journey

**Objective:** Demonstrate essential institutional oversight and academic administration.

Tasks:
- R1.6.1 Build the institutional dashboard with sample admissions, student, academic, and finance summaries.
- R1.6.2 Build admissions management with sample applicant records and status changes.
- R1.6.3 Build a searchable student directory with fictional profiles.
- R1.6.4 Build academic structure views for faculties, departments, programmes, and courses.
- R1.6.5 Demonstrate course management and lecturer assignment using sample data.
- R1.6.6 Build a results review/approval screen showing the approval workflow.
- R1.6.7 Build a finance overview with sample fee and payment records.

Acceptance:
- An administrator can inspect sample applicants and students, explore academic structure and courses, and review a result awaiting approval.
- Consequential demonstration actions use confirmation and clear status feedback.
- Finance data is fictional and read-only; no payment verification, refund, or accounting transaction is performed.

### R1.7 — Platform administration journey

**Objective:** Demonstrate the distinction between institution-level administration and platform-level operations.

Tasks:
- R1.7.1 Build a platform overview using fictional institution and usage summaries.
- R1.7.2 Build an institution list and institution detail view.
- R1.7.3 Present sample institution status and configuration information.

Acceptance:
- The platform operator can navigate platform-level views distinct from the institutional administrator workspace.
- No real institution, subscription, deployment, or provider configuration is changed.

### R1.8 — Integration, responsive behaviour, and prototype validation

**Objective:** Make the prototype coherent and demonstrable across devices and principal journeys.

Tasks:
- R1.8.1 Connect the role journeys through consistent navigation and contextual links.
- R1.8.2 Verify desktop, tablet, and mobile layouts.
- R1.8.3 Verify forms, tables, dialogs, loading, empty, error, success, and permission-denied presentation states where applicable.
- R1.8.4 Verify keyboard navigation, visible focus, accessible labels, contrast, and heading structure.
- R1.8.5 Run a role-by-role walkthrough and record usability issues.
- R1.8.6 Record known limitations, deferred items, and stakeholder feedback.

Acceptance:
- All five target journeys can be demonstrated without dead-end navigation in their principal paths.
- Critical student activities remain usable on mobile.
- Interface states communicate clearly what happened and whether an action was simulated.
- The prototype is labelled and documented as non-production.
- Findings are recorded for prioritization before R2.

## 5. Explicit R1 exclusions

Unless the Project Owner separately approves a scope change, R1 does not include:
- Production authentication, account recovery, email verification, or MFA.
- Real tenant resolution, tenant isolation enforcement, or production authorization.
- Production API, database, migrations, or background workers.
- Real admissions processing, enrolment, course registration, or academic record persistence.
- Live file uploads or private object storage.
- Live classes, video conferencing, or streaming infrastructure.
- A production examination engine, proctoring, or claims of cheating prevention.
- Real grading calculations or institution-approved GPA/CGPA rules.
- Payment gateway integration, real payment collection, reconciliation, refunds, or receipts.
- Real email, SMS, WhatsApp, or push notification delivery.
- Subscription billing, production monitoring, or deployment management.
- Full library, payroll, HR, native mobile apps, advanced analytics, or other deferred capabilities.

## 6. Cross-cutting interface requirements

- Role-aware and permission-aware navigation presentation.
- Configurable institution branding through semantic design tokens.
- Responsive layouts for desktop, laptop, tablet, and mobile.
- Consistent forms with labels, required indicators, inline validation, error messages, and success feedback.
- Consistent data tables with search/filter and appropriate empty/loading states; do not force wide tables into narrow mobile layouts.
- Confirmation for consequential actions.
- Clear loading, success, validation error, permission denied, not found, network failure, processing, and empty states.
- Accessibility considered during component implementation, with WCAG 2.2 AA as the design target.

## 7. R1 completion checklist

R1 can be proposed for acceptance when:
- [ ] The fictional institutional identity and sample dataset are consistent.
- [ ] Public/applicant journey is demonstrable.
- [ ] Student journey is demonstrable.
- [ ] Lecturer journey is demonstrable.
- [ ] Institutional administration journey is demonstrable.
- [ ] Platform operator journey is demonstrable.
- [ ] Role navigation is coherent and the demo-only access mechanism is clearly labelled.
- [ ] Responsive behaviour has been reviewed on desktop and mobile, with tablet coverage.
- [ ] Core forms, tables, dialogs, and feedback states are consistent.
- [ ] Accessibility review has been performed against the UI specification's target.
- [ ] No real personal data or real payment processing is present.
- [ ] Known limitations and feedback are documented.

R1 acceptance does not authorize production deployment or the use of real institutional/student data. Progression to R2 requires a separate readiness review.

## 8. Planning notes

This backlog is a draft implementation plan derived from the initial-design priorities and interactive-demonstration requirements in the source documents. It does not silently approve every broader PRD requirement or settle open technical choices. Task estimates and calendar dates are intentionally omitted until the work is decomposed against the actual R1 design and the developer's available capacity.
