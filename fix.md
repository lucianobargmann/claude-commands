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
2. Reproduce bug locally
3. Identify and inspect affected modules + dependencies.
4. Create a regression test to capture the defect.
   - Ensure test FAILS before the fix.
5. Implement the fix:
   - Ensure syntax and types are valid after every change.
6. Run the regression test until it passes.
7. Run the full test suite to ensure no regressions elsewhere.
8. Run SonarQube analysis to ensure no quality violations.
9. Commit the fix with a message and the regression test.
