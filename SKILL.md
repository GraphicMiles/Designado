# CLEAN CODE ENGINEERING
## Mandatory standards for readable, modular, reusable, secure and efficient implementation

**Priority:** Mandatory  
**Applies to:** All source code written, modified, refactored, generated or reviewed by the agent.  
**Primary outcome:** Code that another competent developer can understand, safely change, test and operate without needing the original author to explain it.

---

## 0. Operating contract

Do not equate code that runs with code that is good. A task is not complete merely because a page renders, an endpoint responds, a test passes once, or a compiler accepts the implementation.

Every implementation must be:

1. Correct for the requested behavior.
2. Understandable to a developer who did not write it.
3. Organized around clear responsibilities.
4. Reusable where reuse is genuinely beneficial.
5. Secure by construction and safe failure.
6. Efficient enough for its expected workload and devices.
7. Testable without excessive setup or hidden state.
8. Consistent with the existing project and its conventions.
9. Maintainable without unnecessary complexity.
10. Honest about what has and has not been verified.

### 0.1 Required reading and instruction retention

Read this entire file before implementation. Do not skim it, read only its first section, or treat it as a prompt summary. If context or file-size limits prevent reading it in one pass, read it sequentially in complete sections until the whole file has been read. Do not claim full compliance unless that happened.

Before coding, convert the requirements relevant to the task into a short internal checklist. Keep the checklist active throughout implementation and use it during final verification.

### 0.2 Decision precedence

Resolve instructions in this order:

1. Platform, system, safety and legal requirements.
2. The user's explicit instructions for this task.
3. The project's established architecture, conventions and documented constraints, provided they are not defective or contrary to an explicit request.
4. This skill's standards.
5. Language, framework and ecosystem conventions.
6. Personal preference, only where no higher-priority rule resolves the decision.

Do not invent requirements, technologies, abstractions or dependencies because they are fashionable. Do not interpret an unspecified detail as permission to choose the most elaborate option.

### 0.3 Inspect before changing

Before editing an existing project:

- Identify the language, framework, runtime and package manager from actual project files.
- Read the relevant package manifests, scripts, configuration and existing instructions.
- Locate the actual entry points and the files responsible for the requested behavior.
- Trace the relevant data flow, state ownership, API boundaries and dependencies.
- Inspect nearby code to understand conventions and existing abstractions.
- Identify tests, build commands, lint rules, type checks and deployment assumptions.
- Check the working tree and do not overwrite unrelated user changes.

Do not assume a framework, directory structure, database, deployment platform or package version. Verify it from the repository.

For a new project, establish requirements and constraints before selecting a stack. See the Software Architecture skill for system-level decisions.

---

## 1. Understand the required behavior before coding

Translate the request into observable behavior before choosing an implementation.

Record:

- The user's intended outcome.
- The primary user journey or system workflow.
- Inputs and their valid shapes.
- Outputs and their expected shapes.
- State changes and persistence requirements.
- Authentication and authorization rules.
- Error, empty, loading, offline and retry states where relevant.
- Performance and device constraints.
- Existing behavior that must not regress.
- Acceptance conditions that can be tested.

Identify edge cases, not just the happy path. Consider missing, malformed, duplicated, stale, unauthorized and out-of-order input. Consider slow networks, repeated submissions, refreshes, interrupted requests and partial failures where applicable.

Do not build a feature from its label alone. Understand the complete behavior it is expected to provide.

If an ambiguity blocks a safe or correct implementation, ask one focused question. Otherwise, use the simplest assumption consistent with the project and make the assumption explicit in the implementation notes. Do not ask the user to decide ordinary engineering details that can be resolved safely from the codebase and requirements.

---

## 2. Readability is a correctness requirement

Code must communicate its intent through its structure and names.

### 2.1 Naming

Use descriptive, domain-appropriate names for:

- Variables and constants.
- Functions and methods.
- Components and modules.
- Types, interfaces and schemas.
- Database fields and API properties.
- Events, states and actions.
- Test cases and fixtures.

Names must explain purpose, not merely implementation mechanics.

Prefer `calculateInvoiceTotal` over `calc`, `isEligibleForRenewal` over `flag`, and `customerAccount` over `data` when those names reflect the actual meaning.

Avoid:

- Cryptic abbreviations.
- Single-letter names outside short, conventional scopes such as a simple index.
- Misleading names.
- Generic names such as `data`, `value`, `thing`, `manager` or `utils` when a domain-specific name is possible.
- Names that claim stronger guarantees than the implementation provides.
- Boolean names that are difficult to read as a true/false statement.

Do not rename established public APIs or database fields casually. Check their consumers and migration impact first.

### 2.2 Function size and responsibility

A function should perform one coherent task at a level of abstraction that can be understood from its name and body.

Split a function when it contains distinct responsibilities, deeply nested branches, repeated logic, unrelated side effects or multiple independently testable decisions.

Do not split every two lines into a helper. Excessive fragmentation makes code harder to follow. A helper is justified when it gives a meaningful name to a concept, isolates a responsibility, removes genuine duplication or creates a useful test boundary.

Keep related operations close together. Avoid code that forces readers to jump through many files to understand a simple operation.

### 2.3 Control flow

Prefer straightforward control flow.

- Use guard clauses for invalid or exceptional conditions when they improve clarity.
- Avoid deeply nested conditionals.
- Avoid clever one-liners that obscure behavior.
- Avoid boolean expressions with ambiguous precedence.
- Make state transitions explicit.
- Handle all meaningful branches.
- Avoid fall-through behavior unless it is intentional and clear.

Do not hide important work inside obscure callbacks, chained expressions or implicit conversions.

### 2.4 Types and contracts

Use the language's type system effectively.

- Model domain concepts explicitly.
- Prefer precise types over broad escape hatches.
- Validate untrusted runtime data even when static types exist.
- Make nullable and optional values explicit.
- Avoid `any`, unchecked casts, broad suppression directives and unsafe non-null assertions unless a documented, verified boundary requires them.
- Keep public function inputs and outputs clear.
- Make impossible states difficult to represent where practical.

Static types do not validate data received from users, external APIs, storage, browser messages or network requests. Validate those inputs at runtime.

Do not over-engineer type definitions for trivial values. Use the narrowest useful contract.

---

## 3. Modularity and separation of concerns

Organize code around responsibilities and domain concepts, not arbitrary file counts.

A module should have:

- A clear purpose.
- A small and understandable public interface.
- Explicit dependencies.
- A coherent set of related behaviors.
- Minimal hidden state.
- A reason to change that is distinct from unrelated modules.

### 3.1 Separate concerns

Keep distinct responsibilities separate where that separation improves clarity and testability. Common examples include:

- Presentation and business rules.
- HTTP transport and domain logic.
- Persistence and application workflows.
- Input parsing and trusted internal data.
- Configuration and application behavior.
- External service adapters and core logic.
- State management and view rendering.

Do not force a particular folder structure onto every project. Follow the existing structure when it is sound. Choose boundaries that reflect the project's actual domain and dependencies.

### 3.2 Avoid god modules and god components

Do not let one file, component, service or class own unrelated responsibilities.

Warning signs include:

- A component that fetches data, validates business rules, manages unrelated state, formats complex domain data and renders an entire page.
- A service that handles unrelated business domains.
- A utility module that becomes a dumping ground.
- A class with many unrelated methods.
- A central file that imports most of the application.

Split responsibilities around meaningful boundaries, not arbitrary line counts.

### 3.3 Avoid premature abstraction

Do not create an abstraction merely because two small pieces of code look similar.

Before extracting a shared abstraction, determine whether the behavior and future change reasons are genuinely the same.

Prefer a small amount of clear duplication over a generic abstraction with many flags, callbacks or configuration branches.

Abstract when:

- The same stable rule is repeated in multiple places.
- Multiple callers share a real domain concept.
- A complex operation benefits from a named boundary.
- External dependencies need isolation.
- A stable contract makes testing or maintenance materially easier.

Do not build speculative plugin systems, factories, registries, base classes or generic frameworks for hypothetical future requirements.

### 3.4 Avoid circular and hidden dependencies

Keep dependency direction understandable. Avoid circular imports, global mutable state and modules that reach into unrelated modules' internals.

Pass dependencies explicitly when that improves clarity, testing or lifecycle control. Do not introduce dependency injection frameworks for a small project that does not need them.

---

## 4. Reuse without sacrificing clarity

Reusable code is not code that has been made generic at all costs.

A reusable component or function must have a clear contract and predictable behavior.

### 4.1 Reuse criteria

Before extracting reusable logic, ask:

- Is the behavior genuinely shared?
- Are the callers likely to evolve together?
- Is the abstraction simpler than the duplication?
- Are its inputs and outputs understandable?
- Can it be tested independently?
- Does it avoid exposing irrelevant implementation details?

### 4.2 Component design

For UI components:

- Give each component a clear role.
- Keep props purposeful and typed.
- Avoid components with dozens of loosely related boolean props.
- Avoid hidden side effects during rendering.
- Keep visual presentation separate from data orchestration when that improves reuse.
- Provide accessible semantics and keyboard behavior.
- Make loading, disabled, error and empty states explicit when applicable.
- Avoid making a reusable component depend on a specific page's private state.

Do not create a component for every wrapper or text node. Component boundaries should improve comprehension or reuse.

### 4.3 Configuration over duplication, but not over-configuration

Use configuration for stable variations in behavior or presentation. Keep configuration small and typed.

Do not build large configuration objects that effectively create a second programming language inside the application.

---

## 5. Error handling and failure behavior

Errors are part of the design of a system. Do not treat them as an afterthought.

### 5.1 Handle errors at the correct boundary

- Validate input at system boundaries.
- Convert low-level failures into meaningful domain or application errors where appropriate.
- Preserve useful diagnostic context.
- Present safe, actionable messages to users.
- Keep internal stack traces and secrets out of user-facing responses.
- Avoid catching an error merely to ignore it.
- Do not return fake success values after failure.
- Do not swallow promise rejections or asynchronous errors.

Catch an error only when the code can recover, add useful context, translate it, or handle it at the appropriate boundary. Otherwise, let it propagate to a boundary that can handle it correctly.

### 5.2 Do not use exceptions for ordinary control flow

Use explicit result types, validation outcomes or normal branching for expected conditions. Reserve exceptions for exceptional failures.

### 5.3 Retries

Retry only operations that are safe to retry or protected by idempotency.

- Use bounded retries and backoff for transient failures.
- Respect `Retry-After` and provider guidance where applicable.
- Do not retry validation, authorization or other permanent failures blindly.
- Prevent duplicate payments, orders, messages or writes.
- Do not retry indefinitely.
- Make retry behavior observable and testable.

### 5.4 Partial failure

Consider what happens when a multi-step operation succeeds partly and then fails. Use transactions, compensating actions, resumable workflows or explicit partial states as appropriate.

Do not report an entire workflow as successful when only one step succeeded.

---

## 6. Security by default

Security is part of implementation quality. Do not postpone it until after features are complete.

### 6.1 Trust boundaries

Treat all external input as untrusted, including:

- Form fields and URL parameters.
- Request bodies and headers.
- Uploaded files.
- External API responses.
- Browser storage and client state.
- Webhooks and callback payloads.
- Queue messages and scheduled jobs.
- Data loaded from databases if its integrity is not guaranteed.

Validate shape, type, size, allowed values and business constraints at the boundary.

### 6.2 Authentication and authorization

Authentication answers who the caller is. Authorization answers what that caller may do. Implement both explicitly.

- Enforce authorization on the server or trusted backend, not only in the UI.
- Check ownership and tenant boundaries for every protected resource.
- Deny by default when permission is uncertain.
- Do not trust user IDs, roles, prices or ownership claims supplied by the client.
- Revalidate access for sensitive operations.
- Avoid leaking whether protected records exist when that would expose information.

### 6.3 Injection and output encoding

Use parameterized database queries and safe framework APIs. Do not build SQL, shell commands, HTML or queries through unsafe string concatenation.

Encode output appropriately for its context. Avoid unsafe HTML injection. Sanitize rich text using a reputable, maintained sanitizer with a restrictive policy when rich HTML is genuinely required.

### 6.4 Secrets and configuration

- Never commit API keys, passwords, private tokens, certificates or production credentials.
- Read secrets from the approved secret-management mechanism or environment configuration.
- Provide safe example environment files containing placeholders only.
- Do not print secrets in logs, errors or test output.
- Rotate and revoke exposed credentials when discovered; report the exposure.
- Do not put server secrets in frontend bundles or public environment variables.

### 6.5 Data protection

Collect and retain only data the product needs. Avoid logging sensitive personal data. Apply access controls, retention and deletion rules appropriate to the product. Do not expose sensitive records in URLs, analytics events or client logs unnecessarily.

### 6.6 Files and uploads

Validate file size, type and content where appropriate. Do not trust file extensions alone. Generate safe storage names. Prevent path traversal. Store uploads outside executable paths where possible. Apply authorization to file access and use malware scanning where the threat model and platform support it.

### 6.7 Dependencies

Use established, maintained dependencies. Check whether a dependency is already present before adding another. Review package provenance and permissions when risk warrants it. Do not add a large dependency for a small helper. Avoid abandoned or unnecessary packages. Keep dependency versions controlled and review security advisories through available project tooling.

### 6.8 Security limitations

Do not claim that code is secure merely because these practices were considered. Record the checks actually performed and any remaining threat or configuration risks.

---

## 7. Performance and resource efficiency

Optimize for measured or reasonably evidenced bottlenecks, not guesswork.

### 7.1 First principles

- Avoid unnecessary work.
- Avoid unnecessary network requests.
- Avoid redundant database queries.
- Avoid repeated expensive calculations.
- Avoid oversized payloads and assets.
- Avoid loading large dependencies for minor features.
- Avoid memory leaks and unbounded collections.
- Avoid blocking the main thread with expensive work.
- Respect mobile devices and slow networks.

### 7.2 Frontend performance

Where applicable:

- Split code by meaningful route or feature boundaries.
- Load noncritical assets lazily.
- Optimize image dimensions, formats and delivery.
- Avoid layout shifts by reserving appropriate space.
- Avoid unnecessary rerenders and state duplication.
- Keep event listeners and subscriptions under control.
- Virtualize genuinely large collections when measurements justify it.
- Avoid premature memoization that makes code harder to maintain.
- Avoid large client-side packages when native or existing project capabilities suffice.

### 7.3 Backend performance

Where applicable:

- Select only required database fields.
- Use indexes that match real query patterns.
- Avoid N+1 queries.
- Bound pagination and request sizes.
- Set timeouts on external calls.
- Apply caching only with clear invalidation and correctness rules.
- Limit concurrency when providers or resources require it.
- Avoid unbounded background work.

### 7.4 Measure honestly

Use profiling, browser tools, logs, query plans, benchmarks or performance audits when available and relevant. Record the conditions of measurement. Do not invent Lighthouse scores, timing results, memory measurements or throughput claims.

Do not make code more complex for an optimization that has not been shown to matter, unless it prevents a well-understood risk or resource failure.

---

## 8. State, concurrency and asynchronous code

Asynchronous behavior creates subtle defects. Make ownership and ordering explicit.

- Define who owns each piece of state.
- Avoid multiple competing sources of truth.
- Guard against stale responses overwriting newer state.
- Cancel or ignore obsolete requests when appropriate.
- Prevent duplicate submissions for operations that must occur once.
- Use transactions or atomic operations for read-modify-write behavior.
- Use locks, version checks, unique constraints or idempotency keys where concurrency requires them.
- Handle timeouts and cancellation deliberately.
- Clean up subscriptions, listeners and timers when their lifecycle ends.
- Consider out-of-order events, retries, duplicate delivery and process restarts.

Do not assume requests complete in the order they were initiated. Do not assume a disabled button alone provides backend protection against duplicate operations.

For money, inventory, bookings, quotas, messaging and other consequential state, establish the consistency guarantees and concurrency strategy explicitly.

---

## 9. Comments and documentation inside code

Comments must add information that the code itself cannot communicate clearly. They are not decoration and must not be used to narrate obvious operations.

### 9.1 Absolute comment rules

- Never put emojis in code comments.
- Never put emoji reactions, decorative symbols or ASCII art in comments.
- Do not comment every function, line, variable or JSX element.
- Do not add comments that merely restate the code.
- Do not add generic comments such as `// This handles the data` or `// Set loading to true` when the code already says that.
- Do not add large explanatory comment blocks to compensate for confusing code. Improve the code first.
- Do not leave stale comments after changing behavior.
- Do not add TODO or FIXME comments without a specific reason and actionable context.

### 9.2 When comments are justified

Use a concise comment only when it explains something not obvious from the implementation, such as:

- Why a non-obvious business rule exists.
- A security invariant that must not be removed.
- A concurrency or ordering constraint.
- A workaround for a verified platform or dependency defect.
- A surprising algorithmic trade-off.
- A compatibility constraint and the condition under which it can be removed.

Prefer naming and structure over comments.

### 9.3 Documentation

Document public contracts, setup, configuration, architecture decisions and operational procedures where they are needed by maintainers or users of the code. Keep documentation accurate and proportional. Do not generate documentation files that merely repeat source code or create noise.

---

## 10. Dependencies, compatibility and change safety

Before adding a dependency, establish:

- Whether the capability already exists in the project.
- Whether the language or platform provides it natively.
- Whether the package is maintained and compatible.
- Its size, runtime and security implications.
- Whether it is necessary for the requested outcome.

Do not change package managers or major framework versions as an incidental part of a feature task.

Do not make broad upgrades without reviewing breaking changes and test coverage.

Preserve backwards compatibility when public APIs, stored data, URLs or integrations depend on it. When a breaking change is necessary, provide a migration plan and update all known consumers.

Do not destructively rewrite files or remove existing behavior without understanding its purpose.

---

## 11. Testing expectations while implementing

Write tests at the level of the behavior being added or changed.

- Test important business rules.
- Test boundary validation.
- Test permissions and ownership.
- Test error and empty states.
- Test important asynchronous and concurrent behavior.
- Test public API contracts.
- Add regression tests for fixed defects.

Tests must assert outcomes, not implementation details that make refactoring unnecessarily difficult.

Do not weaken, delete or skip a failing test merely to make the suite green. Investigate whether the test exposes a real defect, an outdated expectation or a test-environment issue.

The Code Review & Testing skill defines the full verification protocol.

---

## 12. Implementation completion gate

Before reporting completion, verify all applicable items:

- [ ] The requested behavior and acceptance conditions are understood.
- [ ] Relevant existing code and project conventions were inspected.
- [ ] Names communicate intent.
- [ ] Functions and modules have coherent responsibilities.
- [ ] Abstractions are justified, not speculative.
- [ ] Shared logic is reused appropriately without over-generalization.
- [ ] Inputs are validated at trust boundaries.
- [ ] Authentication and authorization are enforced correctly where required.
- [ ] Errors are handled without being silently swallowed.
- [ ] Secrets and sensitive information are protected.
- [ ] Async behavior, retries and concurrency are safe where relevant.
- [ ] Performance choices are reasonable and no unmeasured claims are made.
- [ ] Comments are sparse, useful and contain no emojis.
- [ ] No unnecessary dependencies or unrelated changes were introduced.
- [ ] Relevant tests were added or updated.
- [ ] Required checks were actually run.
- [ ] Remaining limitations are disclosed honestly.

A checkbox is not complete because the agent intended to do the work. It is complete only after the corresponding code or verification has been inspected.

---

## 13. Final standard

Write code for the next developer as carefully as for the current feature.

Prefer the simplest implementation that fully satisfies the real requirements, handles failure safely and can be maintained confidently.

Do not produce clever code to appear advanced. Do not produce abstractions to appear architectural. Do not produce comments to appear documented. Do not optimize by guessing. Do not hide uncertainty behind broad types or swallowed errors.

**Readable code is easier to verify. Modular code is easier to change. Secure code respects trust boundaries. Efficient code avoids waste without sacrificing clarity. Good code makes its intent understandable.**

This standard is mandatory for every implementation.
