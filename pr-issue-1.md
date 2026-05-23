# Pull Request: Docs - Add Comprehensive Contributing Guidelines and Development Workflow (#1)

## Description
This pull request addresses the lack of standard onboarding and contributing documentation for new developers. It introduces a comprehensive and highly detailed `CONTRIBUTING.md` guide to standardise open-source collaboration on **GitVerse Next.js**.

## Related Issue
Closes #1 (Missing standard contributing documentation `CONTRIBUTING.md`)

## Changes Made
- **[NEW] `CONTRIBUTING.md`**:
  - Outlined the repository Code of Conduct.
  - Defined strict branch naming conventions (`feature/`, `bugfix/`, `refactor/`, `docs/`, `chore/`).
  - Documented complete step-by-step local setup instructions (installing package dependencies, configuring `.env.local` and `.env` files, initializing the Neon/PostgreSQL database via Prisma CLI `prisma:generate` and `prisma:migrate`, and launching the development server).
  - Provided comprehensive instructions on **Conventional Commits** formatting to maintain clean, readable history logs.
  - Established pre-submission checklists (checking code style with `npm run format`, verifying syntax via `npm run lint`, and type checking via `npm run typecheck`).

## Verification and Testing
- **Readability & Formatting**: Verified that `CONTRIBUTING.md` is rendered elegantly with markdown styling, tables, code snippets, and premium callout blocks.
- **Git Compliance**: Checked branch log history to confirm the commit uses proper Conventional Commit structure.
