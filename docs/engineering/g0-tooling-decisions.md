# G0 Tooling Decisions and Compatibility Record

**Status:** Approved by Project Owner  
**Release stage:** R1 — Interactive Prototype  
**Decision date:** 2026-11-23  
**Related artefacts:** R1 Prototype Implementation Plan; R1 Visual Direction and Design System  
**Governance:** Project Owner approval recorded in the project conversation. This record captures the approved G0 tooling choices and supporting implementation conventions.

## 1. Purpose

This record closes the G0 tooling decisions required before initializing the R1 frontend application. It does not authorize production services, real institutional data, a production backend, or scope beyond the approved interactive prototype.

## 2. Owner-approved choices

| Area | Decision |
|---|---|
| Package manager | pnpm |
| UI component approach | shadcn/ui, customized using the approved R1 design tokens |
| Testing | Vitest and React Testing Library for unit/component tests; Playwright for end-to-end browser tests |
| Development operating system | Windows 11 |

## 3. Supporting implementation conventions

The following supporting tools are adopted as the implementation baseline for R1, subject to compatible stable releases being pinned in the repository at initialization:

- **Runtime:** Node.js 24 LTS.
- **Framework:** Next.js App Router, React and TypeScript, as already approved in the R1 implementation plan.
- **Styling:** Tailwind CSS v4.
- **Icons:** Lucide React.
- **Forms:** React Hook Form and Zod for complex or multi-step forms; use native browser validation for simple forms where sufficient.
- **Code quality:** ESLint and Prettier.
- **Component tests:** Vitest, React Testing Library and the required DOM/testing utilities.
- **Browser tests:** Playwright Test.

Do not add a global state-management or animation library unless an implemented R1 requirement demonstrates a concrete need. Use local React state and focused feature-level state by default.

## 4. Compatibility assessment and resolutions

### 4.1 Windows 11 and Playwright

Playwright's current system requirements include Windows 11, and its supported browser engines include Chromium, Firefox and WebKit. The selected development computer is therefore compatible with local Playwright execution. No WSL requirement or operating-system workaround is necessary for R1.

For continuous integration, use a Linux runner where practical. Keep local Windows 11 and CI Linux execution aligned through the same pinned Playwright version and lockfile. Install only the browser engines actually required by the test suite to avoid unnecessary downloads.

### 4.2 Node.js and pnpm

Node.js 24 is supported by current pnpm releases and by Playwright's documented supported Node.js lines. Keep Node.js 24 as the initial project baseline to minimize unnecessary environment changes. Pin the selected pnpm release in the root `package.json` using its `packageManager` field, and commit the single pnpm lockfile. CI must install using the committed lockfile rather than resolving unpinned dependency ranges.

Node.js 24 is in the Maintenance LTS phase as of this record. Reassess the runtime at a planned dependency-maintenance checkpoint; do not switch major versions mid-work-package without checking framework, test-runner and dependency compatibility.

### 4.3 Next.js, Tailwind CSS v4 and shadcn/ui

The official shadcn/ui Next.js setup supports the App Router and current Tailwind CSS v4 setup. Use the official Next.js installation path and configure the monorepo deliberately:

- The application lives in `apps/web`.
- Shared shadcn/ui component source may live in `packages/ui` if the workspace configuration supports it cleanly.
- Keep the approved R1 semantic design tokens as the source of truth for colours, typography, spacing, borders and status states.
- Treat shadcn/ui as owned component source code, not as a rigid pre-designed product theme. Review and customize each component to match the approved R1 design system.
- Keep client-side interactivity in appropriately scoped Client Components; do not turn whole route trees into Client Components unnecessarily.
- Avoid installing components that are not used by an approved R1 screen.

### 4.4 Vitest and Next.js Server Components

Use Vitest with React Testing Library for deterministic unit and component tests, especially utilities, validation, synchronous components and client-side interactions.

The current Next.js testing guidance notes that Vitest does not currently support asynchronous Server Components. Do not try to force those tests into Vitest. Verify asynchronous Server Component behaviour and complete user journeys with Playwright end-to-end tests instead.

### 4.5 Playwright execution strategy

- Run Playwright locally on Windows 11 during feature development and journey validation.
- Run the same end-to-end suite in CI on a Linux runner where practical.
- Start with Chromium for the primary R1 journey suite unless the approved screen requirements justify additional browser coverage.
- Keep browser binaries out of source control.
- Use stable test fixtures and synthetic data only.
- Do not make CI workflows trigger deployment or merge actions without separate approval.

## 5. Workspace and dependency rules

- Use pnpm workspaces and one root `pnpm-lock.yaml`.
- Pin the package manager version through the root `package.json` `packageManager` field.
- Keep dependencies at the narrowest workspace level that needs them.
- Avoid duplicate versions of shared framework/testing dependencies where possible.
- Review dependency purpose, maintenance status and licensing before adding material new packages.
- Do not add a production API, database, ORM, queue, worker, object storage or live integration as part of this tooling decision.
- Do not add empty future application workspaces. R1 initializes only the approved web application and packages that have an immediate implementation purpose.

## 6. G0 exit decision

The G0 tooling choices and compatibility concerns are resolved. The project may proceed to R1.1 project initialization on the approved working branch, subject to the existing repository safeguards and owner review gates.

This record does not authorize merging to `main`, creating a pull request, production deployment, real authentication, real data processing or any expansion of R1 scope.

## 7. Official compatibility references

- pnpm installation and Node.js compatibility: https://pnpm.io/installation
- Node.js release schedule: https://nodejs.org/en/about/previous-releases
- shadcn/ui Next.js installation: https://ui.shadcn.com/docs/installation/next
- Tailwind CSS with Next.js: https://tailwindcss.com/docs/installation/framework-guides/nextjs
- Next.js Vitest guide: https://nextjs.org/docs/app/guides/testing/vitest
- Playwright installation and system requirements: https://playwright.dev/docs/intro
- Playwright continuous integration: https://playwright.dev/docs/ci
