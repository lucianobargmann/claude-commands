**NEW FEATURE COMMAND**

You are tasked with implementing a new feature in the codebase. Follow a strict test-driven development (TDD) cycle with comprehensive testing and quality checks.

**Variables:**
feature: $ARGUMENTS
description: Feature description
requirements: List of requirements
acceptance_criteria: Conditions for feature completion
affected_modules: Files or directories to modify

**Execution Rules:**
- Follow TDD red-green-refactor cycle strictly.
- Write tests before implementation.
- Ensure all tests pass at each stage.
- Fix all linting issues automatically.
- Create comprehensive E2E tests.
- Maintain backward compatibility.
- Document public APIs.

**Agentic Loop:**
1. Parse arguments and understand feature requirements.
2. Identify affected modules and dependencies.
3. **TDD Red Phase - Write failing tests:**
   - Create unit tests for the new feature that MUST fail initially.
   - Write integration tests that capture expected behavior.
   - Ensure all new tests are failing (red).
4. **TDD Green Phase - Implement minimal code:**
   - Write the minimal code needed to make tests pass.
   - Focus only on making tests green, not optimization.
   - Run tests continuously until all pass.
5. **TDD Refactor Phase - Improve code quality:**
   - Refactor implementation while keeping tests green.
   - Optimize performance and readability.
   - Extract common patterns and reduce duplication.
6. **Lint and Auto-fix:**
   - Run linter (e.g., eslint, prettier, ruff, etc.).
   - Automatically fix all fixable issues.
   - Manually resolve any remaining lint errors.
   - Verify code passes all style checks.
7. **Create/Update E2E Tests:**
   - Write end-to-end tests covering user workflows.
   - Test happy paths and edge cases.
   - Include error scenarios and boundary conditions.
   - Ensure E2E tests cover all acceptance criteria.
8. **Execute E2E Test Suite:**
   - Run the complete E2E test suite.
   - Fix any failing E2E tests.
   - Re-run until all E2E tests pass.
9. Run the full test suite to ensure no regressions.
10. Run code quality analysis (e.g., SonarQube).
11. Generate or update documentation.
12. Commit the feature with tests and documentation.