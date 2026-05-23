# Pull Request: Feat - Implement Environment Variable Validation Script (#2)

## Description
This pull request introduces an automated environment configuration checker (`scripts/validate-env.ts`) and registers it as a standard package script. This provides developers with early feedback on their `.env.local` or `.env` parameters before starting up development servers or database migrations, preventing runtime crashes.

## Related Issue
Closes #2 (Lack of environment configuration validation script)

## Changes Made
- **[NEW] `scripts/validate-env.ts`**:
  - Implemented standard checks for essential environment variables (`DATABASE_URL`, `JWT_SECRET`, `GEMINI_API_KEY`, `NEXTAUTH_SECRET`, `NEXTAUTH_URL`).
  - Added PostgreSQL syntax validation for `DATABASE_URL` (checks for `postgresql://` or `postgres://` schemas).
  - Evaluates minimum length and strength check for `JWT_SECRET` keys (minimum of 8 characters).
  - Flags default placeholder credentials from templates.
  - Implemented robust credential masking (e.g. `post... [MASKED] ...blic` or `*** [MASKED] ***`) to prevent security and log leaks of sensitive passwords or access keys.
  - Prints visually styled, colorized logs (using terminal escape codes) for successful validations, warnings, and missing fields.
- **[MODIFY] `package.json`**:
  - Registered `"validate-env": "tsx scripts/validate-env.ts"` to the `scripts` collection.

## Verification and Testing
- **Local Runs**: 
  - Verified script successfully flags missing env configurations when files are absent (exits with code 1).
  - Verified script catches incorrect/placeholder configurations (exits with code 1).
  - Verified that valid configs successfully show checked indicators and prompt the developer that they are ready to run dev servers.
