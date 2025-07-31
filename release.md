**PREPARE PRODUCTION LAUNCH COMMAND**

You are tasked with finalizing this repository for a production release. Ensure the codebase meets all quality, testing, and deployment standards.

**Variables:**
version_tag: Use a terminal date command to get the version tag $date +"%Y%m%d%H%M%S"
release_notes: Summary of features and fixes for this release
qa_plan: Test suites and manual QA steps to run
env_checks: Environment variables, DB migrations, and configs to validate

**Execution Rules:**
- Run a complete lint + typecheck cycle and fix all errors.
- Run full unit, integration, and E2E test suites.
- Validate QA environment via Docker (spin up, run smoke tests).
- Run SonarQube analysis and pass all quality gates.
- Verify all environment variables and secrets required for production.
- Apply DB migrations and verify schema integrity.
- Generate final release notes from `release_notes`.

**Agentic Loop:**
1. Parse arguments and set `version_tag`.
2. Execute `npm run lint && npm run typecheck` and fix all issues.
3. Run full test suite (`npm run test && npm run test:e2e`) and fix any failing tests.
4. Execute `qa_plan` including Docker-based QA environment.
5. Validate all `env_checks`, ensuring production configs are present.
6. Run SonarQube scan; fix critical or blocker issues immediately.
7. Build production bundle (`npm run build`) and verify it starts cleanly.
8. Tag the release with `version_tag`.
9. Commit + push release with changelog.
