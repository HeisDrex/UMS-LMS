# R1 Visual Direction and Design System Proposal

**Status:** Draft — for Project Owner review  
**Release stage:** R1 — Interactive Prototype  
**Related documents:** `r1-prototype-backlog.md`; `r1-sitemap-and-screen-inventory.md`  
**Source basis:** UI/UX Design Specification v1.0, PRD v1.0, and accepted project decisions  
**Decision boundary:** This proposal establishes an initial visual direction for the fictional R1 demonstration. It does not approve the official product name, logo, brand identity, initial institution identity, or production white-label configuration.

## 1. Purpose

Define a coherent visual and interaction foundation for the R1 interactive prototype before implementation of role-specific screens.

The UI/UX Design Specification requires a professional, modern, easy-to-navigate educational technology experience; configurable institutional branding; role-specific workspaces; desktop, tablet and mobile support; reusable patterns; clear action feedback; and accessibility with WCAG 2.2 AA as the target.

The exact brand identity and initial institution identity remain open in the PRD. Therefore, this document proposes a neutral product interface foundation and a temporary fictional institution theme for demonstration only.

## 2. Proposed visual direction

### 2.1 Direction: Modern academic technology

The interface should feel:
- Professional and trustworthy, appropriate for institutional administration and academic records.
- Clear and calm, with restrained colour and predictable hierarchy.
- Contemporary without looking like a consumer social network or a generic analytics dashboard.
- Information-dense where necessary, but readable and carefully grouped.
- Consistent across student, lecturer, institutional administration and platform administration workspaces.

### 2.2 Visual principles

1. **Clarity over decoration:** prioritize hierarchy, labels, alignment, readable tables and clear actions.
2. **Neutral application surfaces:** use restrained backgrounds and surfaces so institutional brand colours can be applied without redesigning components.
3. **Colour with meaning:** use semantic tokens; never rely on colour alone to communicate status.
4. **Consistent interaction:** similar controls and actions should behave and look consistently.
5. **Data readability:** academic, examination and financial information must not use unnecessarily small text.
6. **Responsive by design:** define layouts for mobile and tablet rather than shrinking desktop screens.
7. **Configurable identity:** keep product-level UI structure separate from institution-specific brand configuration.

## 3. Proposed colour tokens

The values below are a starting proposal for the R1 fictional demonstration. They are not a final product brand decision. All component styles should consume semantic tokens rather than hard-coded colour values.

### 3.1 Core palette

| Token | Proposed value | Intended use |
|---|---|---|
| Primary | `#2457C5` | Main actions, selected navigation, key links |
| Primary Hover | `#1D46A3` | Hover state for primary actions |
| Primary Subtle | `#EAF0FF` | Selected backgrounds and low-emphasis primary highlights |
| Secondary | `#475569` | Supporting interface controls and secondary emphasis |
| Accent | `#0F8B8D` | Limited highlights, progress and selected informational emphasis |
| Background | `#F6F8FC` | Main application background |
| Surface | `#FFFFFF` | Cards, panels, menus and dialogs |
| Surface Muted | `#F1F5F9` | Secondary surface and table header background |
| Border | `#E2E8F0` | Dividers, outlines and input borders |
| Text Primary | `#172033` | Main headings and body content |
| Text Secondary | `#526079` | Supporting text and descriptions |
| Text Muted | `#64748B` | Metadata and low-emphasis content; verify contrast for each use |

### 3.2 Semantic status tokens

| Token | Proposed foreground | Proposed subtle background | Meaning |
|---|---|---|---|
| Success | `#166534` | `#DCFCE7` | Completed or successful state |
| Warning | `#92400E` | `#FEF3C7` | Pending, caution or attention required |
| Danger | `#B91C1C` | `#FEE2E2` | Error, failed or destructive action |
| Information | `#1D4ED8` | `#DBEAFE` | Informational message or neutral notice |

Status usage rules:
- Pair status colour with text and, where useful, an icon.
- Do not use success green for ordinary primary actions.
- Distinguish pending, processing, submitted, approved, rejected and failed states with explicit labels.
- Ensure foreground/background contrast is checked for every rendered combination, including hover, disabled and focus states.
- Do not communicate grade, payment or examination status by colour alone.

### 3.3 Institution branding boundary

The UI/UX specification lists institution name, logo, primary, secondary and accent colours, login branding, favicon, email templates, public portal branding and domain/subdomain as configurable branding elements.

For R1:
- Use a temporary fictional institution identity and clearly synthetic logo/wordmark treatment.
- Keep institutional brand values in a separate theme configuration layer.
- Map institutional primary, secondary and accent values to semantic tokens.
- Preserve accessible contrast and readable neutral surfaces when a theme changes.
- Do not hard-code the proposed blue palette throughout individual components.
- Do not treat the temporary demonstration theme as the official UMS/LMS brand.

## 4. Typography proposal

The source specification requires a highly readable sans-serif typeface and a clear hierarchy. It does not select a font family.

**Proposal:** use Inter as the initial R1 interface font, with a system sans-serif fallback. This is a provisional implementation choice and can be revisited before or during implementation if availability, licensing, rendering or performance considerations require it.

### 4.1 Type scale

| Token | Proposed size / line height | Use |
|---|---|---|
| Display | 32 / 40 px | Public landing-page hero only |
| Page Title | 28 / 36 px | Main page heading on desktop |
| Section Title | 20 / 28 px | Major page sections |
| Card Title | 16 / 24 px | Card and panel headings |
| Body | 14 / 22 px | Standard interface content |
| Body Large | 16 / 24 px | Important descriptions and instructions |
| Label | 13 / 18 px | Form labels and control labels |
| Metadata | 12 / 16 px | Secondary timestamps and compact metadata |

Typography rules:
- Use weight 600 for page and section headings; 500–600 for card headings and labels; 400 for body content.
- Avoid long passages in all-caps.
- Use tabular numerals for aligned financial amounts, scores, dates and counts where appropriate.
- Do not reduce examination instructions, form labels, table values or financial details below a comfortably readable size to fit content.
- On small screens, scale page headings carefully while preserving clear hierarchy.

## 5. Spacing, sizing and shape

Use a consistent 4 px base spacing unit.

| Token | Value |
|---|---:|
| space-1 | 4 px |
| space-2 | 8 px |
| space-3 | 12 px |
| space-4 | 16 px |
| space-5 | 20 px |
| space-6 | 24 px |
| space-8 | 32 px |
| space-10 | 40 px |
| space-12 | 48 px |
| space-16 | 64 px |

Proposed shape and sizing:
- Small control radius: 6 px.
- Standard input/button radius: 8 px.
- Card/panel radius: 12 px.
- Large modal radius: 14 px.
- Standard control height: 40 px; compact controls may use 32 px where appropriate.
- Primary touch targets should aim for at least 44 × 44 px on touch interfaces.
- Use subtle borders as the default separation method; reserve shadows for floating menus, dialogs and elevated overlays.
- Avoid excessive rounded-pill styling for ordinary cards and buttons.

## 6. Layout and responsive rules

The UI/UX specification calls for a desktop left sidebar, top header, central content area, contextual actions and optional supporting panels. On mobile, the sidebar becomes a collapsible drawer or suitable mobile navigation, dashboard cards stack vertically, forms remain mobile-friendly and tables adapt.

The following breakpoints are proposed starting values, not source-mandated values:

| Breakpoint token | Width | Layout intent |
|---|---:|---|
| Mobile | below 640 px | Single-column content; drawer navigation |
| Tablet | 640–1023 px | Compact/collapsible sidebar; adaptive two-column layouts |
| Desktop | 1024–1279 px | Full application shell with flexible content |
| Wide | 1280 px and above | Full sidebar and wider content grid with a readable max content width |

### 6.1 Authenticated desktop shell

- Sidebar width proposal: 256 px expanded; approximately 76 px collapsed if a collapsed mode is used.
- Header height proposal: 64 px.
- Main content padding proposal: 24–32 px on desktop.
- Keep page content within a readable maximum width; wide tables and data-heavy screens may use more width.
- Keep the active workspace and institution identity visible.
- Use contextual actions near the page title or relevant content.

### 6.2 Tablet and mobile

- Tablet: use a collapsible sidebar or drawer; preserve page title and primary actions.
- Mobile: use a drawer or compact navigation pattern; do not compress the full desktop sidebar into a narrow column.
- Stack dashboard cards and major sections vertically.
- Use full-width form controls where appropriate.
- Adapt wide tables into compact record cards or controlled horizontal scrolling.
- Keep examination question content, progress and submission controls easy to reach.
- Do not obscure important actions behind hover-only interactions.

## 7. Navigation design

### 7.1 Shared shell

The shared authenticated shell should contain:
- Workspace/institution identity.
- Primary workspace navigation.
- Page title and optional breadcrumbs.
- Contextual page actions.
- Notifications.
- Help/support entry.
- User profile/account menu.

### 7.2 Navigation treatment

- Active navigation item: clear background and text/icon emphasis, plus a non-colour-only state indicator where practical.
- Inactive items: readable neutral text with consistent hover and focus treatment.
- Group related modules under concise section labels where needed.
- Avoid excessive nested navigation; aim for no more than two visible navigation levels.
- Use consistent icon style and size; icons supplement text labels rather than replace labels for primary navigation.
- Show only the navigation appropriate to the selected R1 demo workspace. This is presentation behaviour, not authorization.

### 7.3 Icon proposal

Use one consistent outline icon family throughout the application. Use icons for navigation, actions and status where they improve recognition. Avoid mixing emoji, filled icons and unrelated icon families. Every icon-only button must have an accessible name and an adequate touch target.

The exact icon package remains an implementation dependency decision and is not selected by this document.

## 8. Component design standards

The UI/UX specification proposes reusable foundation, navigation, data display, form, feedback and domain components. R1 should implement the shared primitives first, then add domain-specific components when the workflows require them.

### 8.1 Foundation and navigation components

- Design tokens and theme mapping.
- Typography styles.
- Sidebar and navigation item.
- Application header.
- Breadcrumbs.
- Tabs.
- Navigation drawer.
- Page header and contextual action group.

### 8.2 Data display components

- Card and statistic card.
- Data table with search/filter/sort/pagination presentation as appropriate.
- Status badge.
- Profile summary.
- Timeline/activity list.
- Progress indicator.
- Chart container only where the R1 dashboard requires a meaningful chart.

### 8.3 Form components

- Text input and textarea.
- Select and searchable select where needed.
- Checkbox and radio group.
- Date input/picker where needed.
- File-upload placeholder for prototype flows; no live file storage in R1.
- Field label, required indicator, help text and validation message.
- Form action group.

Form behaviour:
- Every field has a visible label.
- Required fields are identified in text or through an accessible association.
- Validation is shown near the relevant field.
- Error messages explain how to correct the problem.
- Loading, disabled, success and error states are defined.
- Unsaved-change warnings appear only where they prevent meaningful data loss.

### 8.4 Feedback components

- Inline alert.
- Toast notification.
- Confirmation dialog.
- Loading indicator/skeleton.
- Empty state.
- Error state.
- Permission-denied presentation.
- Not-found presentation.
- Processing and simulated-success states.

For consequential-looking actions—such as submitting an examination, submitting results or changing an applicant status—show a confirmation that explains the simulated action. Clearly label the result as a demonstration state.

### 8.5 R1 domain components

Build these only when their corresponding workflow is implemented:
- Application status tracker.
- Student profile card.
- Course card.
- Learning material item.
- Assignment summary.
- Submission/grading summary.
- Examination timer/progress panel.
- Result summary.
- Payment/fee status panel.
- Academic structure item.

Do not create a large speculative component library before the screens establish real reuse needs.

## 9. Tables, forms and dashboard conventions

### 9.1 Tables

- Use clear column labels and consistent alignment.
- Align numbers and monetary values consistently.
- Provide search, filters, sorting and pagination only where useful for the sample dataset and screen.
- Use readable empty and loading states.
- Keep row actions visible and understandable.
- Use compact record cards or horizontal scrolling on mobile as appropriate.
- Do not imply bulk operations or export are functional if they are only visual placeholders.

### 9.2 Dashboard cards

- Each card should answer one clear question or summarize one meaningful area.
- Use concise labels, prominent values and supporting context.
- Avoid decorative charts without a clear purpose.
- Keep card density consistent within a dashboard.
- Provide direct links from summary cards to the relevant detail screen where that journey is supported.

### 9.3 Forms

- Group fields by topic and task sequence.
- Keep instructions near the fields they explain.
- Separate review from submission for longer applicant flows.
- Use clear cancel/back/continue/submit labels.
- Distinguish validation errors from simulated processing errors.
- Do not use placeholder text as the only field label.

## 10. Accessibility and interaction requirements

The UI/UX Design Specification sets WCAG 2.2 AA as the target. Accessibility must be considered during component development.

R1 design and review should include:
- Full keyboard navigation for interactive controls.
- Visible focus indicators with sufficient contrast.
- Accessible names and labels for controls.
- Logical heading hierarchy.
- Appropriate text/background contrast.
- Screen-reader-compatible form errors and status updates.
- Text alternatives for meaningful images.
- Captions or transcripts for learning media where media is represented.
- No status communication through colour alone.
- Touch-friendly targets and spacing.
- Dialog focus management and escape/cancel behaviour where appropriate.
- Reduced-motion consideration for non-essential animation.

This document defines design expectations; actual conformance must be verified during implementation and testing.

## 11. Prototype-specific visual and interaction rules

- Show a persistent or clearly discoverable notice that the environment is a non-production demonstration.
- Use only fictional names, institutions, student/staff identities, academic records and finance records.
- Use sample data consistently across linked screens.
- Use simulated confirmation for application submission, assignment submission, examination submission, grading, result submission and administrative status changes.
- Never label a simulated payment as a verified real payment.
- Never imply that the role selector authenticates or authorizes a person.
- Avoid live-looking system health indicators unless they are explicitly marked illustrative.
- Do not connect live email, SMS, payment, file storage, video or institutional services in R1.

## 12. Items intentionally not decided

This proposal does not select or approve:
- Official product name, logo or brand identity.
- Official initial institution name, crest or brand palette.
- Final font licensing/hosting approach.
- UI component library.
- CSS framework or styling implementation.
- Icon package.
- Charting package.
- State-management library.
- Form-validation library.
- Animation library.
- Final responsive breakpoints after usability validation.
- Production theming and white-label administration workflow.

These choices must be evaluated against the approved architecture, development instructions, dependency policy and actual implementation needs before adoption.

## 13. Review and acceptance checklist

- [ ] Visual direction is suitable for a professional higher-education platform.
- [ ] Proposed palette is approved for the fictional R1 demo only, or revised.
- [ ] Typography proposal is approved or revised.
- [ ] Spacing, shape and sizing conventions are approved or revised.
- [ ] Desktop, tablet and mobile layout proposals are accepted.
- [ ] Shared shell and navigation conventions are accepted.
- [ ] Component categories and implementation order are accepted.
- [ ] Accessibility expectations are retained.
- [ ] Prototype-only and simulated-action communication is clear.
- [ ] Official product and institution branding remain explicitly unresolved.

## 14. Implementation handoff

Once this proposal is approved, the next activity is to translate the accepted visual direction into:
1. A small token/theme specification for the frontend.
2. Shared shell and navigation component specifications.
3. Core component states and interaction behaviours.
4. A representative high-fidelity screen set: public landing page, demo entry, student dashboard, lecturer dashboard, institutional admin dashboard and platform overview.
5. A reviewed implementation-ready UI foundation before building the full R1 screen inventory.

No application code or dependency selection is authorized merely by the existence of this proposal.
