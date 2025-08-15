**FIX DEFECT COMMAND**

You are tasked with diagnosing and fixing a defect in the codebase. Follow a strict debugging and testing cycle until the defect is fully resolved and validated.

**Variables:**
bug: $ARGUMENTS
description: Description of the defect
steps_to_reproduce: Exact reproduction steps
expected_result: Correct behavior
actual_result: Current incorrect behavior
affected_modules: Suspected files or directories

**Execution Rules:**
- Isolate the defect before making changes.
- Create a regression test that fails with the current code and passes once fixed.
- Never break public APIs when fixing defects.
- Changes must be atomic: one defect fix per commit.

**Agentic Loop:**
1. Parse arguments and understand defect scope.
2. Reproduce bug locally.
3. Identify and inspect affected modules + dependencies.
4. **TDD Red Phase - Create failing regression test:**
   - Write a test that reproduces the defect.
   - Ensure test FAILS with current code (red).
   - Add additional test cases for edge conditions.
5. **TDD Green Phase - Implement minimal fix:**
   - Write the minimal code needed to fix the defect.
   - Focus only on making the regression test pass.
   - Ensure syntax and types are valid after every change.
   - Run the regression test until it passes (green).
6. **TDD Refactor Phase - Improve fix quality:**
   - Refactor the fix while keeping tests green.
   - Optimize without changing behavior.
   - Ensure code is clean and maintainable.
7. **Lint and Auto-fix:**
   - Run linter for affected files.
   - Automatically fix all fixable issues.
   - Manually resolve any remaining lint errors.
   - Verify code passes all style checks.
8. **Create/Update E2E Tests:**
   - Write or update E2E tests covering the fix.
   - Test the specific user workflow that was broken.
   - Include tests for related edge cases.
   - Ensure E2E tests fail without fix and pass with fix.
9. **Execute E2E Test Suite:**
   - Run the complete E2E test suite.
   - Verify no E2E tests are broken by the fix.
   - Re-run until all E2E tests pass.
10. Run the full test suite to ensure no regressions elsewhere.
11. Run code quality analysis (e.g., SonarQube).
12. Commit the fix with a message, regression test, and E2E tests.
