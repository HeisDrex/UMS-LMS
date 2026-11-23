# R1 Screen Specifications

**Document status:** Approved by Project Owner  
**Release:** R1 Interactive Prototype  
**Related approved artefacts:** R1 Prototype Backlog; R1 Sitemap and Screen Inventory; R1 Visual Direction and Design System  
**Related design baseline:** R1 Visual Direction and Design System (approved)  
**Source specifications:** PRD v1.0; UI/UX Design Specification v1.0  
**Scope note:** These specifications describe six representative R1 screens. They do not authorize production authentication, backend workflows, real payments, or real institutional data.

---

## 1. Purpose and scope

This document translates the approved R1 visual direction and sitemap into implementable screen-level requirements for six representative screens:

1. Public institutional landing page.
2. Secure login and permission-based workspace routing.
3. Student dashboard.
4. Lecturer dashboard.
5. Institutional administration dashboard.
6. Platform administration dashboard.

The R1 prototype uses fictional institutional identity and synthetic data. Interactions demonstrate intended journeys; they must not be represented as production operations.

The six screens are representative entry points, not the complete screen inventory. The approved sitemap and backlog continue to define the wider R1 prototype scope.

## 2. Shared interface rules

### 2.1 Visual foundation

- Apply the approved R1 visual direction and semantic design tokens.
- Use a readable sans-serif typeface and a consistent heading hierarchy.
- Use consistent spacing, card, border, status, form, and feedback patterns.
- Treat the proposed EduVista identity and institutional content as fictional demonstration material only.
- Institutional branding must be treated as configurable; the R1 demo palette is not an approved commercial brand identity.

### 2.2 Authenticated application shell

On desktop, authenticated screens use:
- A left navigation sidebar containing only destinations authorized for the signed-in user.
- A top header containing institutional identity where applicable, current context, notifications, help/support access where included, and the account menu.
- A central content area with a clear page title, relevant contextual actions, and responsive content grids.
- Breadcrumbs on deeper pages where they help users understand location.

On smaller screens:
- The sidebar becomes a collapsible navigation drawer or suitable mobile navigation.
- Dashboard cards stack into a readable vertical layout.
- Tables use compact cards or controlled horizontal scrolling where appropriate.
- Important actions remain reachable and forms remain touch-friendly.
- The layout must be adapted for mobile, not merely scaled down.

### 2.3 Permission and data rules

- Navigation and actions are role-aware and permission-aware.
- Hiding a link is not authorization: protected routes and actions must be checked by the application/server in a production implementation.
- The prototype must visibly distinguish simulated actions from real operations.
- Do not expose another institution's records or another user's private records in a workspace.
- Use synthetic names, identifiers, academic records, financial figures, and operational metrics only.

### 2.4 Shared interaction and feedback states

Major interactive elements should support appropriate:
- Default, hover, focus, active, and disabled states.
- Loading and processing states where an operation is simulated.
- Success confirmation.
- Validation and permission-denied feedback.
- Empty, not-found, and failure states where relevant.
- Confirmation dialogues for consequential actions.

Use text and iconography as well as colour to communicate status. Target WCAG 2.2 AA, including keyboard access, visible focus, accessible labels, contrast, logical headings, and screen-reader-compatible controls.

---

## 3. Screen 1 — Public Institutional Landing Page

### 3.1 Purpose

Introduce the fictional institution, help prospective students discover relevant information, and provide clear entry points to programme information, application and login.

### 3.2 Primary users

- Prospective students and their supporters.
- Applicants returning to continue or track an application.
- Existing students or staff navigating to login.
- General visitors seeking institutional information.

### 3.3 Page structure

1. **Public header**
   - Institution logo and name.
   - Primary navigation: Home, Programmes, About, Resources, Contact (exact links may be adjusted to fit the prototype).
   - Primary actions: Apply Now and Login.
   - Mobile navigation control.

2. **Hero section**
   - Clear institutional value proposition.
   - Short supporting description.
   - Primary call to action to explore programmes or begin an application.
   - Secondary action to learn more about the institution.
   - Relevant, appropriately licensed or generated illustrative image.

3. **Institution highlights**
   - A small set of fictional demonstration statistics or institutional highlights.
   - Clearly treated as illustrative sample content, not factual claims about a real institution.

4. **Featured programmes**
   - Programme title, short description, qualification/level where available, and link to programme details.
   - Clear route to the full programme listing.

5. **Admissions information**
   - Brief application guidance and admission requirement entry point.
   - Application call to action.

6. **Public footer**
   - Contact information, useful links, policy links/placeholders, and institutional identity.

### 3.4 Main actions

- Open programme listing or programme details.
- Start applicant registration/application journey.
- Open the common login screen.
- Navigate to institutional information and contact details.

### 3.5 Behaviour and states

- Navigation links lead to the corresponding R1 prototype pages or clearly labelled placeholder destinations.
- Apply Now begins the prospective-student journey; it must not imply that an application has been submitted until the prototype explicitly demonstrates that step.
- Login opens Screen 2.
- Provide responsive navigation and visible focus states.
- If a destination is not implemented in the current prototype increment, show a clear not-yet-available or planned state rather than a broken link.

### 3.6 Responsive considerations

- Desktop: full navigation and wide hero composition.
- Tablet/mobile: collapsible navigation, stacked hero content, appropriately cropped image, stacked programme cards and highlights.
- Preserve legible text and reachable calls to action at narrow widths.

---

## 4. Screen 2 — Secure Login and Permission-Based Workspace Routing

### 4.1 Purpose

Provide one common sign-in entry point. After successful authentication, the application directs the user to the workspace permitted by the user's verified identity, active institutional membership and permissions.

**There must be no public workspace selector, role picker, or list of Student, Lecturer, Institutional Administration, and Platform Administration entry options on this screen.**

### 4.2 Primary users

Any registered applicant, student, lecturer, institutional user, or authorized platform operator who has been directed to the relevant institutional or platform login entry point.

### 4.3 Page structure

1. **Institution identity**
   - Correct institution logo and name for an institutional login context.
   - Platform identity for the separately authorized platform-operator login context, where applicable.
   - The R1 demo may use the fictional EduVista identity.

2. **Login form**
   - Email address or username.
   - Password.
   - Show/hide password control.
   - Remember-session option only where appropriate to the prototype.
   - Sign In action.
   - Forgot Password link.
   - Support contact or help entry point.

3. **Security/support note**
   - Concise reassurance or support guidance.
   - Do not claim production-grade encryption or security certification in a simulated prototype.

### 4.4 Authentication and routing behaviour

1. User submits credentials.
2. The prototype validates the input and simulates authentication against its fictional demo accounts.
3. On simulated success, it resolves the account's permitted destination using the account's role, active membership and context.
4. It redirects directly to the authorized workspace dashboard.
5. On failure, it displays a generic, useful sign-in error without revealing whether a particular username exists.
6. A suspended, inactive, or unauthorized account receives an appropriate access-denied or account-status message without access to a workspace.

### 4.5 Multiple authorized memberships

If a user legitimately has more than one active institutional membership, any context selection must occur only after authentication and must show only institutions/workspaces that the authenticated account is authorized to access. It must not become a public role/workspace chooser. Where the account has a configured default context, route directly to it.

A user must not gain access merely by changing a URL, manipulating an identifier, or selecting a hidden route.

### 4.6 Main actions

- Submit sign-in form.
- Toggle password visibility.
- Open password recovery flow.
- Open support/help destination.
- Sign out where a signed-in state is being demonstrated.

### 4.7 R1 prototype boundary

- Authentication and redirects are simulated with synthetic accounts.
- Do not collect or store real passwords.
- Do not present the R1 role simulation as a production identity, session, or authorization system.
- No real SSO, MFA, email verification, or password recovery delivery is implied unless separately included in the approved prototype scope.

### 4.8 Responsive and accessibility requirements

- Keep the form usable on mobile and desktop.
- Use persistent labels, appropriate input types, keyboard-operable controls, visible focus, and accessible validation messages.
- Ensure errors are associated with the relevant fields.

---

## 5. Screen 3 — Student Dashboard

### 5.1 Purpose

Give a student a prioritized overview of current academic activity, learning, upcoming deadlines, announcements and financial status.

### 5.2 Primary users

Authenticated students with an active student membership and the required permissions.

### 5.3 Authenticated shell navigation

The student navigation may include:
- Dashboard.
- My Courses.
- Course Registration.
- Assignments.
- Examinations.
- Results.
- Finance/Payments.
- Announcements or Messages.
- Profile and Settings.

Only destinations included in the approved R1 prototype increment and authorized for the user should be active. Navigation labels may be grouped where needed for clarity.

### 5.4 Dashboard content hierarchy

1. **Welcome and academic context**
   - Student display name.
   - Student number or identifier (synthetic).
   - Programme.
   - Current academic session and term.

2. **Academic summary**
   - Registered course count.
   - Outstanding assignments.
   - Upcoming examinations or classes.
   - Learning progress.
   - Academic standing only where the sample data supports it.

3. **Priority activity**
   - Upcoming assignment deadlines.
   - Scheduled live classes.
   - Examination dates.
   - Important academic dates.
   - Clear due dates and status labels.

4. **My Courses preview**
   - Course code and title.
   - Lecturer or course context where appropriate.
   - Progress indicator.
   - Link to the course workspace.

5. **Announcements and notifications**
   - Relevant university, faculty/department, and course notices.
   - Unread/read state where demonstrated.

6. **Financial summary**
   - Outstanding balance.
   - Recent payment status.
   - Available receipt entry point.
   - Payment state must be labelled as simulated in R1.

### 5.5 Main actions

- Open a registered course.
- Open an assignment or its submission flow.
- View an upcoming class or examination detail.
- Open published results.
- View finance information or a sample receipt.
- Open announcements and notifications.
- Open profile/settings.

### 5.6 Behaviour and states

- Prioritize urgent and relevant items instead of maximizing the number of dashboard statistics.
- Only published results are represented as official student results in the product model.
- The R1 prototype must use fictional results and financial records.
- A successful simulated assignment submission must show an explicit confirmation and updated sample status.
- Payment status must not be presented as verified real payment activity.
- Provide empty states when a student has no upcoming activities or no registered courses in the synthetic scenario.

### 5.7 Responsive considerations

- Stack summary cards and activity panels vertically on mobile.
- Keep deadlines, result labels and financial status readable.
- Make course and activity cards easy to tap.
- Avoid requiring a wide desktop table for routine student tasks.

---

## 6. Screen 4 — Lecturer Dashboard

### 6.1 Purpose

Give lecturers a focused overview of teaching responsibilities, assigned courses, scheduled classes, student submissions, grading work and result preparation.

### 6.2 Primary users

Authenticated lecturers with active institutional membership and permissions for the relevant courses and teaching tasks.

### 6.3 Authenticated shell navigation

The lecturer navigation may include:
- Dashboard.
- My Courses.
- Course Materials.
- Assignments/Assessments.
- Submissions and Grading.
- Examinations (where authorized).
- Results.
- Students or Class Lists.
- Messages/Announcements.
- Profile and Settings.

Only authorized modules and actions should be visible and accessible.

### 6.4 Dashboard content hierarchy

1. **Welcome and teaching context**
   - Lecturer display name.
   - Current academic session/term.
   - Department or faculty context where appropriate.

2. **Teaching summary**
   - Assigned courses.
   - Pending grading count.
   - Upcoming classes.
   - Results awaiting submission or action.

3. **Upcoming teaching schedule**
   - Class/course.
   - Date and time with time zone where relevant.
   - Delivery mode or location where available.
   - Status and permitted join/open action.

4. **Pending work**
   - Assignment submissions awaiting review.
   - Grading status.
   - Results preparation/submission status.
   - Priority and due-date indicators.

5. **Course overview**
   - Assigned course list.
   - Enrolment count where authorized.
   - Recent course activity or announcements.

6. **Quick actions**
   - Open a course.
   - Create an assignment.
   - Upload or organize course material.
   - Review submissions.
   - Prepare results where permitted.

### 6.5 Main actions

- Open an assigned course.
- Create or edit an assignment in the simulated course workflow.
- Upload/select sample learning material.
- Review a student submission.
- Save a draft grade and feedback.
- Finalize grading where the simulated permissions allow.
- Prepare and submit results for approval.
- View approval status.

### 6.6 Behaviour and states

- Course access is limited to courses assigned to the lecturer.
- Learning content should distinguish draft, scheduled and published states.
- Grading should distinguish draft/saved/finalized states.
- Result submission must clearly indicate that submission is for approval; it must not imply the lecturer can publish official results unless separately authorized.
- Consequential actions use confirmation and visible feedback.
- All records are synthetic in R1.

### 6.7 Responsive considerations

- Prioritize the next teaching activity and pending grading work.
- Stack course and summary cards on mobile.
- Grading and content-editing screens must remain usable on smaller screens; complex tables may switch to compact cards or controlled horizontal scrolling.

---

## 7. Screen 5 — Institutional Administration Dashboard

### 7.1 Purpose

Provide authorized institutional administrators with an overview of institutional operations and entry points into admissions, student/staff management, academic configuration, results approval, finance and reporting.

### 7.2 Primary users

Institutional administrators and other institutional staff with explicitly granted administrative permissions. The dashboard is not a universal administrator role with unrestricted access.

### 7.3 Authenticated shell navigation

The institutional navigation may include:
- Dashboard.
- Admissions.
- Students.
- Staff/Lecturers.
- Academic Structure.
- Programmes and Courses.
- Course Registration.
- Examinations.
- Results and Approvals.
- Finance.
- Reports.
- Institutional Settings.

The exact menu is permission-filtered. For example, a finance officer should not automatically receive examination or privileged user-management permissions.

### 7.4 Dashboard content hierarchy

1. **Institution identity and operational context**
   - Institution name and logo.
   - Current academic session/term.
   - Signed-in administrator and relevant institutional context.

2. **Institutional overview**
   - Student totals.
   - Staff totals.
   - Programme/course totals.
   - Other approved high-level operational indicators.

3. **Admissions activity**
   - Applications by status.
   - Pending document/review tasks.
   - Recent application activity.
   - Link to admissions queue.

4. **Academic operations**
   - Registration activity.
   - Course/programme administration reminders.
   - Examination scheduling or monitoring indicators where included.
   - Results awaiting review/approval.

5. **Finance overview**
   - Fee/payment summary.
   - Pending verification or reconciliation items where permitted.
   - Outstanding balances or period summaries using synthetic figures.

6. **Key activities and reports**
   - Recent institutional activity.
   - Operational notices.
   - Quick links to authorized reports.

### 7.5 Main actions

- Open and review admission applications.
- Open the student or staff directory.
- Manage programmes, courses and academic configuration where authorized.
- Open examination administration where authorized.
- Review submitted results and approval queues.
- Open finance workflows where authorized.
- View institutional reports.
- Open institutional settings.

### 7.6 Behaviour and states

- Dashboard metrics must be derived from the fictional dataset used by the prototype and remain internally consistent.
- Role-specific permissions must affect both navigation and action availability.
- Result approval and publication must be represented as separate workflow stages.
- Financial verification, adjustment, refund, account suspension, privileged role assignment and policy changes require explicit confirmation in the prototype.
- Sensitive administrative actions must show clear consequence descriptions and audit-oriented feedback.
- Platform administration functions must not appear in this workspace.

### 7.7 Responsive considerations

- Desktop may use denser operational summaries and tables.
- On mobile, prioritize pending tasks and key alerts; use compact record cards or controlled horizontal scrolling for tables.
- Complex configuration should remain readable and operable on smaller screens.

---

## 8. Screen 6 — Platform Administration Dashboard

### 8.1 Purpose

Give authorized product operators an operational view of the platform and controlled access to institution management, subscriptions, deployments, integrations, system health and support operations.

### 8.2 Primary users

Authorized platform administrators/operators only. This workspace is distinct from institutional administration.

### 8.3 Authenticated shell navigation

The platform navigation may include:
- Dashboard.
- Institutions.
- Subscriptions.
- Deployments.
- Integrations.
- System Health/Monitoring.
- Background Jobs.
- Audit Logs.
- Support.
- Platform Settings.

Only platform-level permissions should expose these destinations.

### 8.4 Dashboard content hierarchy

1. **Platform overview**
   - Total institutions.
   - Active/suspended institution counts.
   - Total platform users or usage summary where appropriate.
   - Subscription status overview.

2. **Operational health**
   - Application/service health.
   - Database, queue and storage status.
   - Integration health.
   - Background job status.
   - Backup status or system alerts where represented by the synthetic dataset.

3. **Institution activity**
   - Recent institution lifecycle events.
   - Institution onboarding or configuration status.
   - Usage indicators.

4. **Subscription and deployment overview**
   - Plan/status summaries.
   - Renewal or usage indicators where available.
   - Deployment status.

5. **Support and system actions**
   - Open support tickets.
   - Review alerts.
   - View operational logs.
   - Open approved provider/integration management.

### 8.5 Main actions

- View institution list and institution details.
- Review subscription status.
- View deployment/operational metadata.
- Inspect integration health.
- Review system alerts and background-job status.
- Open audit logs.
- Review support activity.
- Open platform settings.

### 8.6 Behaviour and states

- Platform access does not imply unrestricted access to institutional academic or personal records.
- Any support access to institutional resources must be explicitly authorized, reason-recorded, time-limited and auditable in the product model.
- Operational monitoring should remain separate from institution-owned academic records.
- Institution activation/suspension and subscription changes require appropriate authorization and confirmation.
- The R1 dashboard uses synthetic operational metrics; it is not connected to real infrastructure.

### 8.7 Responsive considerations

- Prioritize critical service alerts and institution status.
- Use compact summary cards and readable monitoring panels.
- Dense operational tables should provide a mobile-friendly alternative.
- High-impact actions must remain clearly labelled and require confirmation.

---

## 9. Cross-screen navigation and routing rules

1. Public visitors can reach the public landing page, programme information, applicant journey and common login.
2. Login does not display a list of workspaces or roles.
3. After successful authentication, the system resolves the user's permitted context and routes directly to the appropriate dashboard.
4. A user with multiple legitimate memberships may use a controlled, authenticated context switcher limited to memberships they are authorized to access. It is not a public workspace selector.
5. Direct URL access to another workspace or resource must be denied when the user lacks permission.
6. Sign-out returns the user to an appropriate public/login entry point and ends the prototype's simulated signed-in state.
7. The platform administration environment remains separate from institutional administration.
8. Cross-workspace navigation must not expose unauthorized workspace names, data or actions to a user who is not entitled to them.

## 10. R1 prototype interaction boundaries

The six screens should be connected into coherent, explorable journeys using synthetic data. R1 may simulate:
- Login success/failure and destination routing.
- Dashboard navigation and sample record opening.
- Application journey entry points.
- Course and learning-material navigation.
- Assignment submission and lecturer grading states.
- Result submission/approval demonstrations.
- Institutional administrative review actions.
- Platform operational views.

R1 must not:
- Process real payments.
- Use real student or institutional records.
- Claim to provide production authentication or authorization.
- Claim that simulated administrative actions changed real institutional records.
- Connect to live infrastructure or external providers unless separately approved.

Every simulated action must provide clear feedback and avoid implying that a real-world transaction or official academic decision occurred.

## 11. Design acceptance checklist

The six-screen design package is ready for owner acceptance when:

- [ ] All six screens follow the approved visual direction.
- [ ] The public landing page clearly separates public information from authenticated tools.
- [ ] The login screen contains no public workspace or role selector.
- [ ] Successful login routes to the correct authorized workspace in the prototype.
- [ ] The four authenticated environments are visually and functionally distinct while sharing a common design system.
- [ ] Navigation and actions are permission-aware.
- [ ] Platform administration is distinct from institutional administration.
- [ ] The principal content hierarchy and actions are specified for each screen.
- [ ] Loading, empty, error, success and permission-denied states are considered.
- [ ] Desktop, tablet and mobile behaviour is specified.
- [ ] WCAG 2.2 AA is used as the accessibility target.
- [ ] All demonstration data and simulated actions are clearly identified as fictional/non-production.
- [ ] No screen silently expands the approved R1 scope.

## 12. Open design details

The following remain implementation/design choices unless separately approved:
- Exact institution name, logo and official brand identity.
- Exact copy, imagery and fictional sample figures.
- Exact icon package and UI component library.
- Exact charting and form libraries.
- Exact detailed sidebar labels where role permissions require tailoring.
- Detailed page designs beyond these six representative screens.

**Approval note:** This document is a draft for Project Owner review. Approval confirms the screen-level design specification for R1; it does not authorize production implementation, dependency selection, or scope expansion.
