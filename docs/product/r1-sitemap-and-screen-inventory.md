# R1 Sitemap and Screen Inventory

**Status:** Draft — for Project Owner review  
**Release stage:** R1 — Interactive Prototype  
**Related backlog:** `docs/product/r1-prototype-backlog.md`  
**Source basis:** PRD v1.0, UI/UX Design Specification v1.0, accepted project decisions, and approved R1 backlog  
**Scope note:** This document defines the information architecture and the screens needed to demonstrate the approved R1 journeys. It does not approve the full production product scope.

## 1. Information architecture principles

1. Keep the public institutional portal separate from authenticated workspaces.
2. Provide four principal authenticated environments: Student, Lecturer, Institutional Administration, and Platform Administration.
3. Use one shared application foundation and design system; vary navigation and page capabilities by the selected demonstration workspace.
4. Organize navigation around user tasks and business capabilities, not around the internal software architecture.
5. Keep primary journeys shallow: users should reach frequent tasks without navigating through excessive menu levels.
6. Use consistent page titles, active navigation states, breadcrumbs where useful, and contextual actions.
7. Design mobile as an intentional layout: collapsible navigation, stacked dashboard cards, mobile-friendly forms, and appropriate table adaptations.
8. Treat the R1 role-entry mechanism and all data-changing interactions as simulations. The interface must not imply production authentication, authorization, persistence, payments, or academic processing.

## 2. Global application map

```text
UMS/LMS
├── Public Institutional Portal
│   ├── Home
│   ├── About the Institution
│   ├── Programmes
│   │   └── Programme Details
│   ├── Admissions
│   │   ├── Admission Requirements
│   │   ├── How to Apply
│   │   └── Application Help / FAQs
│   ├── Tuition & Fees (informational)
│   ├── Contact
│   ├── Applicant Registration / Sign In
│   └── Existing User Sign In
│
├── Demonstration Access
│   ├── Demo Introduction / Notice
│   ├── Select Demo Workspace
│   └── Demo Profile Entry
│
└── Authenticated Application
    ├── Shared Application Shell
    │   ├── Workspace / Institution Context
    │   ├── Global Header
    │   ├── Search (visual/demo treatment only if included)
    │   ├── Notifications
    │   ├── Help
    │   └── Profile / Account Menu
    │
    ├── Student Workspace
    ├── Lecturer Workspace
    ├── Institutional Administration Workspace
    └── Platform Administration Workspace
```

The public portal represents an institution's public-facing experience. Demonstration Access is a prototype-only entry route, not a production authentication flow.

## 3. Public institutional portal

| ID | Screen / route concept | Purpose and principal content | R1 priority |
|---|---|---|---|
| PUB-01 | Home | Institutional identity, hero/introductory content, programme highlights, admissions call to action, announcements, contact/footer | Must |
| PUB-02 | About | Fictional institution overview, mission, learning model, key information | Could |
| PUB-03 | Programmes | Browse and search/filter sample programmes | Must |
| PUB-04 | Programme details | Programme description, duration, entry requirements, sample structure, apply action | Must |
| PUB-05 | Admissions information | Admission requirements, application steps, required documents, relevant dates (fictional) | Must |
| PUB-06 | Tuition and fees | Informational sample fee schedule and fee disclaimers | Should |
| PUB-07 | Contact | Fictional contact channels and enquiry information | Could |
| PUB-08 | Applicant registration / sign in | Prototype registration entry and applicant access route | Must |
| PUB-09 | Application form | Applicant details, programme selection, qualification details, document placeholders, review and submit steps | Must |
| PUB-10 | Application confirmation / status | Simulated reference, submission confirmation, current status, next-step guidance | Must |
| PUB-11 | Applicant sign-in / status access | Demo route to an existing sample application | Should |

### Public portal navigation

- Home
- About
- Programmes
- Admissions
- Tuition & Fees
- Contact
- Apply
- Sign In

On small screens, collapse the primary navigation into a menu while keeping Apply and Sign In discoverable.

## 4. Demonstration access

| ID | Screen / route concept | Purpose and principal content | R1 priority |
|---|---|---|---|
| DEM-01 | Demo notice | Explain that this is a fictional, non-production demonstration using synthetic data | Must |
| DEM-02 | Workspace selection | Show Student, Lecturer, Institutional Administrator, and Platform Operator demo entries | Must |
| DEM-03 | Demo profile selection | Show a small set of fictional named demo profiles where useful | Should |

The interface must label the role-entry mechanism as demonstration-only. It must not be presented as secure login, identity verification, or proof of authorization.

## 5. Shared authenticated application shell

| ID | Shared element / screen | Purpose and expected behaviour |
|---|---|---|
| SHELL-01 | Application header | Institution/workspace identity, page context, notifications, help, profile/account menu |
| SHELL-02 | Primary navigation | Workspace-specific navigation with clear active state |
| SHELL-03 | Breadcrumbs | Show location on deeper pages where useful |
| SHELL-04 | Notification centre | Sample categorized notifications and read/unread presentation; no real delivery |
| SHELL-05 | Profile / account menu | Demo profile summary and simulated account actions |
| SHELL-06 | Global search presentation | Optional R1 visual treatment; results must be synthetic and limited to the selected demo workspace |
| SHELL-07 | Shared feedback patterns | Loading, empty, success, validation error, permission-denied, not-found, and processing states |

## 6. Student workspace

### Student navigation

- Overview
- My Courses
- Course Registration
- Assignments
- Examinations
- Results
- Fees & Payments
- Announcements
- My Profile

### Student screen inventory

| ID | Screen / route concept | Purpose and principal content | R1 priority |
|---|---|---|---|
| STU-01 | Dashboard / Overview | Welcome and student identity; programme/session; registered courses; outstanding assignments; upcoming examinations; learning progress; announcements; financial summary; upcoming activities | Must |
| STU-02 | My Courses | Registered course list with code, title, lecturer, term, and progress | Must |
| STU-03 | Course workspace | Course overview, lecturer, modules, announcements, assignments, quizzes, recorded lectures, live-class schedule, discussion entry, progress | Must |
| STU-04 | Learning material view | Read or view a sample resource; show module/topic context and completion presentation | Must |
| STU-05 | Course registration | Available and registered sample courses, credit units, prerequisites, deadlines, registration status, simulated confirmation | Should |
| STU-06 | Assignment list | Upcoming, submitted, overdue, and graded sample assignments | Must |
| STU-07 | Assignment details / submission | Instructions, resources, score, due date, submission status, simulated submission and confirmation | Must |
| STU-08 | Examination list / details | Sample schedule, duration, availability, instructions, permitted attempts, rules | Must |
| STU-09 | Examination attempt | Sample questions, navigation, progress, countdown presentation, save indicator, confirmation before simulated submission | Must |
| STU-10 | Examination submission confirmation | Clear simulated attempt-submitted state; no claim of a real exam record | Must |
| STU-11 | Results | Fictional published results, course scores/grades, session/term, GPA/CGPA only where clearly illustrative | Must |
| STU-12 | Fees & Payments | Sample fee breakdown, invoices, outstanding balance, transaction status, payment history, receipts as sample records | Must |
| STU-13 | Announcements | Institution, faculty/department, and course sample announcements | Should |
| STU-14 | Student profile | Personal/contact details, programme and admission summary, student identifier; official academic fields read-only | Should |

### Student journey links

- Dashboard → My Courses → Course workspace → Learning material.
- Dashboard / Course workspace → Assignment details → Simulated submission confirmation.
- Dashboard → Examinations → Examination details → Attempt → Submission confirmation.
- Dashboard → Results.
- Dashboard → Fees & Payments.

## 7. Lecturer workspace

### Lecturer navigation

- Overview
- My Courses
- Learning Materials
- Assignments
- Submissions & Grading
- Results
- Announcements

### Lecturer screen inventory

| ID | Screen / route concept | Purpose and principal content | R1 priority |
|---|---|---|---|
| LEC-01 | Dashboard / Overview | Assigned courses, current session, upcoming classes, pending grading, results awaiting submission, announcements, permitted student activity summary | Must |
| LEC-02 | Assigned courses | Course list with course code/title, programme, term, enrolment count, status | Must |
| LEC-03 | Course workspace / management | Course details, modules, materials, assignments, students, discussions, schedule | Must |
| LEC-04 | Learning material editor | Sample title, description, content type, module, display order, publication status, preview | Should |
| LEC-05 | Assignment management | Assignment list and sample create/edit view, instructions, deadline, resources, scoring criteria | Must |
| LEC-06 | Submission list | Fictional submissions, student, submitted date, status, grading state | Must |
| LEC-07 | Submission review / grading | Submission preview, score, feedback, rubric presentation where useful, save/finalize demonstration | Must |
| LEC-08 | Result preparation | Course, registered students, assessment components, sample totals/grades, missing-result and validation warnings | Should |
| LEC-09 | Result submission status | Demonstrate submitted / pending review / returned states; no real approval operation | Must |
| LEC-10 | Class schedule | Upcoming sample classes, dates, times, and time-zone labels | Could |

### Lecturer journey links

- Dashboard → Assigned courses → Course workspace → Learning materials.
- Course workspace → Assignment management → Submission list → Submission review.
- Course workspace / Dashboard → Result preparation → Result submission status.

## 8. Institutional administration workspace

### Institutional administration navigation

- Overview
- Admissions
- Students
- Academic Structure
- Courses
- Staff & Lecturers
- Examinations
- Results
- Finance
- Announcements
- Institution Settings

R1 should keep this navigation focused. Some items may lead to concise overview screens or clearly marked preview states rather than complete management modules.

### Institutional administration screen inventory

| ID | Screen / route concept | Purpose and principal content | R1 priority |
|---|---|---|---|
| ADM-01 | Dashboard / Overview | Applicants, enrolled students, programmes, courses, lecturers, admissions queue, academic operations, results awaiting approval, finance summaries, activity/alerts | Must |
| ADM-02 | Admissions list | Fictional applications, programme, submitted date, status, filters | Must |
| ADM-03 | Applicant detail / review | Applicant summary, programme, sample document placeholders, review notes, status and decision presentation | Must |
| ADM-04 | Student directory | Fictional student list, search/filter, programme, department, enrolment status | Must |
| ADM-05 | Student profile | Student identity, admission, programme, status, academic and finance summaries with synthetic data | Should |
| ADM-06 | Academic structure | Sample faculties/schools, departments, programmes, hierarchy presentation | Must |
| ADM-07 | Programme / course catalogue | Sample programmes and courses, codes, credit units, prerequisites, term | Must |
| ADM-08 | Course detail / assignment | Course information and sample lecturer assignment presentation | Should |
| ADM-09 | Staff and lecturer directory | Sample staff list, role, department, assigned courses | Could |
| ADM-10 | Examination overview | Sample examination schedule and status | Could |
| ADM-11 | Results review queue | Sample course results awaiting review, submitted/returned/approved status | Must |
| ADM-12 | Result review detail | Sample result sheet, validation warnings, approval-stage presentation, simulated decision | Must |
| ADM-13 | Finance overview | Sample invoiced totals, verified-payment labels, outstanding balances, pending manual verification | Must |
| ADM-14 | Fee / transaction detail | Read-only fictional fee and transaction record | Could |
| ADM-15 | Announcements | Sample institutional announcements and status | Could |
| ADM-16 | Institution settings overview | Grouped settings categories: general, branding, academic, admissions, fees, exams, notifications, integrations, security, retention | Could |

### Institutional administrator journey links

- Dashboard → Admissions → Applicant detail.
- Dashboard → Students → Student profile.
- Dashboard → Academic Structure → Programme / Course catalogue → Course detail.
- Dashboard → Results review queue → Result review detail.
- Dashboard → Finance overview → Sample transaction detail.

Any approval, status change, or configuration interaction in R1 must be explicitly simulated and must not be represented as a real institutional operation.

## 9. Platform administration workspace

### Platform administration navigation

- Overview
- Institutions
- Subscriptions (overview only if included)
- System Health (illustrative only)

### Platform administration screen inventory

| ID | Screen / route concept | Purpose and principal content | R1 priority |
|---|---|---|---|
| PLT-01 | Platform dashboard | Fictional total/active/suspended institutions, platform user count, sample subscription summary, illustrative infrastructure/storage/integration/job status, alerts | Must |
| PLT-02 | Institution directory | Fictional institution list, deployment label, status, created date, usage summary | Must |
| PLT-03 | Institution detail | Institution profile, branding preview, domain/deployment metadata, status and sample usage | Must |
| PLT-04 | Subscription overview | Sample plan/status/renewal and usage labels; no billing operation | Could |
| PLT-05 | System health overview | Clearly illustrative service/queue/storage/integration status; no real monitoring connection | Could |

Platform operator screens must not suggest that platform-level access grants unrestricted access to institution-owned academic, personal, or financial records. Support access is not part of the R1 demonstration unless separately scoped.

## 10. Cross-workspace interaction and navigation rules

- Selecting a demo workspace opens its matching dashboard.
- The workspace identity remains visible in the authenticated shell.
- Only the selected workspace's navigation is displayed.
- Links to records remain within the selected fictional institution and demo dataset.
- The profile menu may offer a return-to-demo-workspace action; it must not imply a production institution-switching or identity-membership flow.
- Notifications open relevant sample screens where a destination exists.
- Destructive or consequential-looking demo actions require a confirmation step and a clear simulation notice.
- Back, cancel, save, submit, and return actions must behave predictably; avoid dead-end screens.
- Breadcrumbs are used where they improve orientation, not mechanically on every page.

## 11. Responsive behaviour

### Desktop
- Left sidebar, top application header, central content area, contextual page actions, and optional supporting panel where useful.
- Use responsive grids for dashboard cards and content sections.
- Tables may use full data-table presentation.

### Tablet
- Sidebar may collapse to an icon rail or drawer.
- Preserve access to primary actions and page context.
- Reduce multi-column layouts without hiding critical information.

### Mobile
- Use a navigation drawer or suitable mobile navigation pattern.
- Stack dashboard cards vertically.
- Use mobile-friendly form controls and action placement.
- Convert wide tables to compact cards or controlled horizontal scrolling where appropriate.
- Keep critical student activities usable: login/demo entry, course access, material viewing, assignment submission, examination participation, results, and finance review.
- Examination screens prioritize readable questions, touch targets, progress, and clear submission confirmation.

## 12. R1 screen implementation order

This is a dependency-aware design/build sequence, not a calendar commitment.

1. Shared foundations: design tokens, typography, spacing, shell, sidebar/header, buttons, cards, tables, forms, badges, dialogs, alerts, feedback states.
2. Public portal: home, programme list/detail, admissions information, application form, confirmation/status.
3. Demo access: notice, workspace selection, sample profiles.
4. Student workspace: dashboard, course list/workspace, materials, assignments, examination, results, finance.
5. Lecturer workspace: dashboard, courses, materials, assignments, submissions/grading, result submission.
6. Institutional administration: dashboard, admissions, student directory, academic structure/course views, results review, finance overview.
7. Platform administration: dashboard, institution directory/detail.
8. Journey integration, responsive refinement, accessibility review, and prototype walkthrough.

## 13. R1 screen inventory boundaries

- The Must/Should/Could labels prioritize the R1 screen inventory; they do not alter PRD-wide requirement priorities.
- A screen listed here may be simplified to a representative prototype state if its full production workflow is outside R1.
- A route or screen is not evidence that its underlying production capability exists.
- The detailed visual design, component specifications, exact copy, sample data values, and final route strings will be elaborated during screen design.
- This document does not choose a UI component library, CSS framework, icon package, state-management library, or form-validation package.
- Any material change to the approved R1 backlog requires separate Project Owner approval.

## 14. Review checklist

- [ ] Public portal and applicant journey are represented.
- [ ] Student workspace covers the approved student journey.
- [ ] Lecturer workspace covers the approved teaching journey.
- [ ] Institutional administration covers the approved operations journey.
- [ ] Platform administration is distinct from institutional administration.
- [ ] Shared shell and navigation are consistent across workspaces.
- [ ] Mobile behaviour is intentionally specified.
- [ ] Prototype-only actions and illustrative data are clearly identified.
- [ ] Screen priorities are consistent with the approved R1 backlog.
- [ ] No production capability or technical dependency is silently added.
