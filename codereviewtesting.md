# CODE REVIEW AND TESTING
## Mandatory verification, defect hunting, regression prevention and release-quality standards

**Priority:** Mandatory  
**Applies to:** Every code change, bug fix, refactor, feature, integration, audit and release candidate.  
**Primary outcome:** Evidence that the implementation behaves correctly, preserves existing behavior, handles failure safely and is maintainable.

---

## 0. Verification contract

Do not treat implementation as proof of correctness.

A successful build does not prove the feature works. A passing unit test does not prove the full user journey works. A visually correct screenshot does not prove the buttons function. A successful API response does not prove authorization is correct. A code review does not prove that runtime behavior has been tested.

Verification must combine appropriate inspection and execution:

- Requirements and acceptance-criteria review.
- Source-code inspection.
- Static analysis and type checks.
- Unit tests.
- Integration tests.
- End-to-end tests.
- Security and authorization checks.
- Regression checks.
- Responsive and accessibility checks for user interfaces.
- Build and deployment checks where relevant.

Use the levels that apply to the risk and scope. Do not run irrelevant or destructive checks merely to claim more coverage.

**Never claim a test, audit, browser check or security check was completed unless it was actually performed and its result was observed.**

## 0.1 Required reading

Read this entire file before reviewing or testing. If it cannot fit in one context window, read it sequentially until complete. Do not skim or infer its contents from the title.

Apply the Clean Code Engineering and Software Architecture skills alongside this skill. For interfaces, also apply Visual Design Judgment and Product Critic & Benchmarking where relevant.

---

# 1. Establish the scope and baseline

Before reviewing changes, understand what is being verified.

## 1.1 Establish scope

Identify:

- The requested change and its acceptance conditions.
- The changed files and related files.
- The affected user journeys and system workflows.
- The relevant APIs, data models and external integrations.
- Existing behavior that must remain unchanged.
- The risk and impact if the feature fails.
- The project checks available in the repository.

For an ordinary change, review every changed line and trace the relevant surrounding behavior. Do not limit review to the visible diff if a changed function affects callers, shared state, database logic, permissions or external contracts.

For a full-project audit, build a complete inventory of first-party source, configuration, tests, migrations and deployment files in scope. Inspect all relevant first-party files. Exclude dependency directories, generated output, caches, binaries and vendor code unless the task specifically concerns them. State any exclusions.

## 1.2 Establish baseline

Before changing code, where practical:

- Inspect repository status and protect unrelated working-tree changes.
- Identify the package manager and project scripts.
- Run or inspect the current test suite, build, lint and type checks.
- Record pre-existing failures separately.
- Identify flaky or environment-dependent tests.
- Confirm required environment variables and test services.

Do not attribute a pre-existing failure to your change. Do not ignore it either. Record it clearly and determine whether it affects verification.

Do not overwrite user changes or reset the repository to make checks pass.

---

# 2. Review the requirement, not just the code

Translate the request into observable expected behavior.

For every acceptance condition, identify:

- The code responsible for it.
- The test or observation that verifies it.
- The expected success result.
- Relevant failure and edge conditions.

Check for missing requirements, misunderstood user intent, incomplete workflows and features that work only on the happy path.

Review the complete journey. For example, an order flow may involve authentication, address selection, price calculation, inventory, payment, order persistence, notification and order status. Testing only the submit button is insufficient.

Do not invent acceptance criteria that conflict with the user. Identify assumptions separately.

---

# 3. Static code review

Inspect code for correctness, maintainability and risk before relying on runtime tests.

## 3.1 Correctness and logic

Look for:

- Incorrect conditions and operators.
- Off-by-one errors.
- Incorrect default values.
- Missing branches.
- Invalid assumptions about input shape.
- Incorrect sorting, filtering or aggregation.
- State updated in the wrong order.
- Stale or duplicated state.
- Incorrect date, time-zone, currency or unit handling.
- Precision and rounding errors.
- Broken pagination.
- Inconsistent status transitions.
- Incorrect null and empty-value handling.
- Logic that differs between client and server.

Trace the complete path from input to side effect and final output.

## 3.2 Error handling

Look for:

- Swallowed exceptions.
- Unhandled promise rejections.
- Incorrect success responses after a failed operation.
- Unclear error translation.
- Exposed internal details.
- Missing cleanup after partial failure.
- Retry loops without a bound.
- Retrying permanent errors.
- Duplicate side effects caused by retries.

## 3.3 Concurrency and race conditions

Actively investigate:

- Two requests updating the same record.
- Repeated form submissions.
- Double clicks and duplicate webhook delivery.
- Stale responses overwriting current state.
- Async operations completing out of order.
- Read-modify-write races.
- Missing database transactions or constraints.
- Duplicate job execution.
- Concurrent inventory, quota, payment or booking operations.
- Cleanup that happens before an async task finishes.
- Shared mutable state accessed by multiple tasks.

Do not assume the UI prevents duplicate operations. Verify protection at the trusted backend or storage boundary.

## 3.4 Security review

Review applicable risks, including:

- Missing or incorrect authorization.
- Cross-user or cross-tenant data exposure.
- Insecure direct object references.
- Trust in client-supplied role, price, owner or permission data.
- Injection vulnerabilities.
- Unsafe HTML rendering.
- Insecure file uploads or path handling.
- Exposed secrets or sensitive logs.
- Weak webhook verification.
- Replay and duplicate-event handling.
- Missing rate limits or abuse controls where required.
- Overly broad CORS or security configuration.
- Insecure session or token handling.
- Sensitive data retained or exposed unnecessarily.

Test permissions with users who should be denied, not only the owner or administrator who should succeed.

## 3.5 Architecture and maintainability review

Look for:

- Responsibilities mixed together.
- Unnecessary coupling.
- Circular dependencies.
- Duplicate business rules.
- Overly broad abstractions.
- Repeated logic that should be shared.
- Hidden global state.
- Unclear names and contracts.
- Excessive configuration flags.
- Dead code and unreachable branches.
- Unused dependencies.
- Fragile assumptions about execution order.

Do not demand refactoring simply because another pattern is fashionable. Recommend changes that reduce a demonstrated risk or maintenance cost.

## 3.6 Performance review

Look for:

- N+1 queries.
- Unbounded data reads.
- Missing pagination.
- Repeated expensive computations.
- Oversized bundles and assets.
- Unnecessary network requests.
- Missing request timeouts.
- Memory leaks and unbounded queues.
- Unnecessary rerenders.
- Blocking operations on critical threads.
- Excessive database writes.

Use measurements or query plans when possible. Label an unmeasured concern as a risk or hypothesis, not a confirmed performance defect.

---

# 4. Test strategy: choose the correct level

Testing should be layered. No single test category is enough.

## 4.1 Unit tests

Use unit tests for isolated business rules, calculations, validators, state transitions and pure functions.

Good unit tests:

- Verify meaningful input/output behavior.
- Cover normal, boundary and invalid cases.
- Are deterministic.
- Run quickly.
- Do not depend on real external services.
- Avoid asserting private implementation details unnecessarily.

Do not create trivial tests for every getter, wrapper or line merely to inflate coverage.

## 4.2 Integration tests

Use integration tests to verify interactions between real project components, such as:

- API handlers and application services.
- Services and database repositories.
- Authentication and authorization middleware.
- Data validation and persistence.
- Transactions and constraints.
- External provider adapters using controlled test doubles or provider sandboxes.
- Background jobs and queues.

Use realistic test infrastructure where appropriate. Do not mock the very boundary whose integration behavior the test is meant to verify.

## 4.3 End-to-end tests

Use end-to-end tests for important user journeys and cross-system behavior.

For web interfaces, use the project's existing browser automation tool. If Playwright is installed or available, prefer it for repeatable browser journeys. Do not introduce a second browser automation framework without a reason.

A meaningful E2E flow should verify the user's actual path, not merely that a page loads.

Examples include:

- Registration, login and logout.
- Password or account recovery where implemented.
- Creating, editing and deleting a resource.
- Searching, filtering and pagination.
- A complete checkout or booking flow.
- Permission denial for unauthorized users.
- Uploading and retrieving a file.
- Handling empty, loading, error and success states.

Use deterministic test data and isolated accounts. Clean up test data safely.

## 4.4 Contract tests

Where systems or modules communicate through stable contracts, verify request and response shapes, error behavior and compatibility.

Do not let internal refactoring silently break a public API or integration.

## 4.5 Visual and responsive checks

For UI changes, inspect rendered output at representative desktop and mobile viewport sizes.

Check:

- Visual hierarchy and alignment.
- Overflow and clipping.
- Image loading and crop.
- Typography and readability.
- Interactive states.
- Form usability.
- Navigation behavior.
- Empty and error states.
- Keyboard focus.

For visual comparison, use screenshots or browser inspection when available. A source-code inspection is not a substitute for checking the rendered interface.

Apply the Visual Design Judgment and Product Critic skills where required.

## 4.6 Accessibility checks

Test semantic structure, labels, keyboard navigation, focus visibility, contrast and relevant assistive-technology behavior. Use automated accessibility checks as a supplement, not as proof that the interface is fully accessible.

---

# 5. Test case design

Do not test only the expected happy path.

For each important behavior, consider the relevant categories below.

## 5.1 Input boundaries

- Missing input.
- Empty input.
- Whitespace-only input.
- Malformed input.
- Wrong type.
- Extremely long input.
- Unsupported values.
- Duplicate values.
- Boundary numeric values.
- Invalid date or time.
- Unexpected Unicode or encoding.

## 5.2 User and permission boundaries

- Unauthenticated user.
- Authenticated user with correct permission.
- Authenticated user without permission.
- Different record owner.
- Different tenant or organization.
- Expired or revoked access.
- Forged client-supplied identity or role.

## 5.3 State and lifecycle

- Initial state.
- Loading state.
- Success state.
- Empty state.
- Error state.
- Retry state.
- Cancelled state.
- Stale state.
- Deleted or archived state.
- Invalid or unexpected transition.

## 5.4 Network and external dependencies

- Slow response.
- Timeout.
- Connection loss.
- Provider error.
- Rate limit.
- Malformed provider response.
- Duplicate callback or webhook.
- Out-of-order callback.
- Partial provider success.

## 5.5 Concurrency

- Double submission.
- Simultaneous edits.
- Simultaneous resource claims.
- Duplicate job execution.
- Stale update.
- Conflicting writes.

## 5.6 Persistence and recovery

- Refresh after a successful operation.
- Reopen the application.
- Resume an interrupted workflow.
- Verify persisted values.
- Verify cleanup and deletion.
- Verify rollback or compensation after partial failure.

Select cases relevant to the feature. Do not add meaningless combinations merely to inflate the test count.

---

# 6. Test quality rules

Tests are code and must follow the Clean Code skill.

- Use descriptive test names that state behavior.
- Keep each test focused on a meaningful outcome.
- Arrange, act and assert clearly.
- Avoid hidden dependencies between tests.
- Avoid shared mutable fixtures that make order matter.
- Use stable test data.
- Control time, randomness and external service responses where necessary.
- Assert both important results and relevant side effects.
- Verify that forbidden actions did not occur.
- Keep tests deterministic and maintainable.

Do not use arbitrary sleeps to wait for UI or network behavior when a proper condition-based wait is available.

Do not weaken assertions merely to make tests pass. Do not delete a regression test because it exposes a bug. Do not mark a skipped test as passed.

A retry that passes after a flaky failure does not erase the first failure. Investigate and record flakiness.

---

# 7. Regression prevention

Every bug fix should include a regression test at the lowest useful level, plus higher-level verification when the defect crosses boundaries.

Before merging a change, identify what existing behavior could be affected.

Review:

- Shared components and modules.
- Other callers of changed functions.
- Database migrations and stored records.
- API consumers.
- Authentication and authorization behavior.
- Responsive layouts.
- Related flows using the same state or provider.
- Background jobs and event handlers.

Do not assume a narrow diff has a narrow impact.

Do not refactor unrelated code during a bug fix unless necessary to safely resolve the defect. Keep changes scoped and explain justified expansion.

---

# 8. Full-project audit protocol

When asked to conduct a severe or comprehensive project audit, perform a systematic audit rather than a superficial scan.

## 8.1 Inventory

Create an inventory of first-party files and relevant configuration:

- Application source.
- UI components and routes.
- Backend handlers and services.
- Data models and migrations.
- Authentication and authorization.
- External integrations.
- Background jobs.
- Tests.
- Build and deployment configuration.
- Security configuration.

Exclude generated artifacts, dependencies, caches and vendor code unless they are specifically in scope. State exclusions.

## 8.2 Trace behavior

For every critical flow, trace:

1. Entry point.
2. Input validation.
3. Authentication.
4. Authorization.
5. Business rules.
6. State reads and writes.
7. External calls.
8. Error handling.
9. User-visible output or system side effect.
10. Tests and operational visibility.

## 8.3 Defect classification

Classify findings by severity:

- **P0 Critical:** Active or readily exploitable issue causing severe data compromise, irreversible loss, broad outage or similarly catastrophic impact. Follow incident or containment procedures.
- **P1 High:** Major security, data integrity, financial, authorization or core workflow defect. Must be fixed before release.
- **P2 Medium:** Significant functionality, reliability, performance or maintainability problem with a limited or recoverable impact.
- **P3 Low:** Minor defect, edge-case issue or localized improvement with a reasonable workaround.
- **P4 Informational:** Non-blocking suggestion or observation, not a confirmed defect.

Do not exaggerate severity. Explain impact, affected conditions and reproducibility.

For each confirmed defect, record:

- Location.
- Evidence.
- Reproduction steps.
- Root cause.
- Impact.
- Severity.
- Recommended fix.
- Regression test.

Separate confirmed defects from hypotheses and recommendations.

## 8.4 Fixing during an audit

When asked to fix findings, do not stop at reporting them.

Prioritize by severity and dependencies. Fix the root cause, add regression coverage, and re-run the relevant checks. Preserve unrelated changes. If a safe fix requires a decision or access not available, explain the blocker and leave the issue clearly open.

---

# 9. Required execution and evidence

Run the project's relevant checks using the commands and services actually available.

Typical checks may include:

- Formatter or format check.
- Linter.
- Type checker.
- Unit tests.
- Integration tests.
- E2E tests.
- Accessibility checks.
- Production build.
- Migration validation.
- Security scanning.
- Dependency audit.

Do not invent command names. Inspect package scripts and project documentation first.

For every check, record:

- The exact command or procedure.
- Whether it was run.
- Pass, fail, skipped or blocked.
- Relevant output or failure summary.
- Whether the failure is pre-existing or introduced by the change, if known.

Do not claim a complete test suite when only one test command was run.

If a tool, environment variable, browser, service or credential is unavailable, do not simulate success. State exactly what could not be verified and why.

---

# 10. Fix and re-verify loop

When a defect is found:

1. Reproduce it or establish the strongest available evidence.
2. Identify the root cause.
3. Check the surrounding flow and related call sites.
4. Choose the smallest safe fix that resolves the root cause.
5. Add or update regression tests.
6. Run the narrowest relevant tests first.
7. Run broader affected checks.
8. Inspect the diff for unintended changes.
9. Repeat until the defect is resolved or a real blocker is reached.

Do not patch symptoms while leaving the underlying defect intact.

Do not introduce a second bug to fix the first.

Do not continue making random edits after tests fail. Use the failure evidence to determine the next step.

If a fix does not improve the failing condition, reconsider the diagnosis and approach.

---

# 11. Release readiness gate

A change is ready only when all applicable conditions are satisfied:

- [ ] The implementation satisfies the acceptance conditions.
- [ ] Changed code and impacted call paths were reviewed.
- [ ] No known P0 or P1 issue remains in scope.
- [ ] Authorization and trust boundaries were checked.
- [ ] Relevant unit tests pass.
- [ ] Relevant integration tests pass.
- [ ] Critical E2E flows pass where available and applicable.
- [ ] Regression tests cover fixed defects.
- [ ] Static checks pass or their failures are explained.
- [ ] Production build succeeds where applicable.
- [ ] UI was inspected at relevant viewports where applicable.
- [ ] Accessibility and error states were considered.
- [ ] Migrations and deployment effects were reviewed.
- [ ] No secrets or unrelated files were exposed or modified.
- [ ] The diff contains no accidental changes.
- [ ] Verification limitations are documented honestly.

A release gate cannot pass by silently skipping an applicable failed check.

---

# 12. Review report format

Keep the report useful and evidence-based.

For a code review, present findings first, ordered by severity. Include file and line references where available. Distinguish confirmed defects, potential risks and suggestions.

For implementation verification, summarize:

- What changed.
- What behavior was tested.
- Commands and checks actually run.
- Results.
- Known failures or limitations.
- Remaining release blockers.

Do not produce a huge report full of generic advice when there are no corresponding findings. Do not hide a serious defect in a long list of low-value suggestions.

---

# 13. Final standard

A test suite is evidence, not decoration. A review is an investigation, not a compliment. A build is one signal, not a guarantee. A defect is not fixed until its root cause is addressed and its regression path is verified.

**Review what changed, trace what it affects, test what users actually do, challenge the failure cases, preserve existing behavior and report only what the evidence supports.**
