# SOFTWARE ARCHITECTURE
## Mandatory system design, technical decision and evolution standards

**Priority:** Mandatory  
**Applies to:** New applications, existing systems, major features, integrations, data models, infrastructure changes and architectural reviews.  
**Primary outcome:** An architecture that fits the product, constraints and expected evolution without unnecessary complexity or fragile coupling.

---

## 0. Architecture contract

Architecture is the arrangement of responsibilities, boundaries, data, dependencies and operational decisions that determine how a system behaves and evolves.

It is not a diagram exercise, a folder-naming exercise or an opportunity to introduce fashionable infrastructure.

The architecture must:

- Satisfy verified product requirements.
- Fit the team's actual skills and operating capacity.
- Fit the budget, hosting, device, network and deployment constraints.
- Make critical data flows and trust boundaries explicit.
- Keep responsibilities and dependencies understandable.
- Support testing, debugging, deployment and maintenance.
- Handle failure and growth at a proportionate level.
- Minimize unnecessary services, dependencies and operational burden.
- Preserve existing working behavior unless change is required.

**Do not design for imaginary scale. Do not under-design critical risks. Choose the smallest architecture that safely meets the real requirements and foreseeable product needs.**

## 0.1 Required reading

Read this entire skill before proposing or changing architecture. If it cannot be read in one context window, read it sequentially until complete. Do not treat headings or a summary as a substitute for the full document.

Also consult the Clean Code Engineering and Code Review & Testing skills. For user-facing products, consult the Visual Design Judgment and Product Critic & Benchmarking skills where they apply.

## 0.2 Decision precedence

Use this order:

1. System, platform, safety and legal requirements.
2. Explicit user requirements and constraints.
3. Verified product and operational requirements.
4. Existing architecture and contracts that must be preserved.
5. This skill's principles.
6. Ecosystem conventions and personal preference.

Never let personal preference or trend override a verified requirement.

---

# 1. Discover before designing

Do not propose an architecture from a one-sentence product description.

For an existing system, investigate the actual repository and deployment environment. For a new system, establish the necessary product and operational facts before selecting technologies.

## 1.1 Product discovery

Identify:

- The product's purpose and target users.
- Core user journeys and system workflows.
- The minimum viable scope and explicitly excluded scope.
- Critical business rules.
- Data the system creates, reads, changes and deletes.
- Roles, permissions and tenant boundaries.
- External services and integrations.
- Offline, low-network or mobile requirements.
- Consequences of incorrect, duplicated, delayed or lost operations.
- Availability, recovery and support expectations.

Distinguish confirmed requirements from assumptions and unanswered questions.

## 1.2 Operational discovery

Establish:

- Hosting and deployment target.
- Runtime, framework and language constraints.
- Database and storage requirements.
- Expected traffic and workload shape, if known.
- Budget and recurring cost constraints.
- Team size and operational experience.
- Monitoring, backup and recovery capabilities.
- CI/CD and release practices.
- Data location, privacy and regulatory obligations.
- Third-party rate limits and failure characteristics.

Do not invent traffic estimates or claim a system needs microservices without evidence.

## 1.3 Repository discovery

For existing projects, inspect:

- Repository structure and entry points.
- Package manifests and scripts.
- Current modules and dependency graph.
- Environment configuration.
- Database schema and migrations.
- API routes and external contracts.
- Authentication and authorization implementation.
- State management and data-fetching conventions.
- Tests and build pipeline.
- Deployment configuration and infrastructure files.
- Existing technical debt and known constraints.

Trace actual execution paths. Do not infer architecture solely from directory names.

## 1.4 Build an evidence-based requirement set

Separate findings into:

- **Confirmed:** directly supported by user requirements, repository behavior or authoritative configuration.
- **Assumed:** a provisional decision required to proceed.
- **Unknown:** cannot be established from available evidence.
- **Constraint:** a limit the design must respect.

Do not quietly convert assumptions into facts. Ask a focused question only when an unknown blocks a consequential decision. Otherwise choose a conservative, reversible assumption and record it.

---

# 2. Define the system before selecting technology

Create a concise system model before implementation.

## 2.1 Define boundaries

Identify:

- Users and external actors.
- The application or system boundary.
- External providers.
- Trusted and untrusted environments.
- Data owners and sources of truth.
- Critical workflows.
- Failure boundaries.

Make clear which component is responsible for each behavior.

## 2.2 Define responsibilities

For each major module or service, state:

- Its purpose.
- What it owns.
- What it does not own.
- What data it can change.
- What it exposes to other modules.
- What it depends on.
- How failure is handled.

No important business rule should exist in multiple conflicting places.

## 2.3 Define source of truth

For every important data category, identify its authoritative source.

Avoid multiple writable copies of the same critical fact without a clear synchronization model.

For example, determine whether account status, order status, pricing, inventory, subscription entitlements or permissions are authoritative in the backend, database, provider or another designated system.

Do not trust client-side state as the authoritative source for consequential decisions.

---

# 3. Choose architecture proportional to the problem

Architecture should emerge from requirements, not from a preferred diagram or technology list.

## 3.1 Start with the simplest viable structure

A modular monolith is a legitimate and often preferable starting point when one deployable application can satisfy the requirements.

Do not introduce microservices simply because the product may grow.

Do not introduce message brokers, event buses, service meshes, Kubernetes, distributed caches or complex orchestration without a concrete need and an owner capable of operating them.

A single application can still have strong internal module boundaries.

## 3.2 When separation is justified

Separate a component, process or service when there is a defensible reason, such as:

- Independent scaling requirements.
- A materially different security boundary.
- Different runtime or deployment requirements.
- Independent team ownership.
- Failure isolation needs.
- An integration or workload that must not block the primary application.
- A stable domain boundary that benefits from independent lifecycle.

Describe the benefit and new costs. Include network failures, observability, deployment coordination, data consistency, retries and operational overhead in the decision.

## 3.3 Avoid architecture theater

Do not add:

- Layers that only pass data unchanged.
- Interfaces with only one trivial implementation and no real boundary benefit.
- Generic repositories around every database query without a need.
- Factories for a fixed, simple object.
- Event sourcing for ordinary CRUD without a business or audit requirement.
- CQRS solely because it sounds scalable.
- Multiple databases without clear data ownership or workload reasons.
- A plugin framework for hypothetical future extensions.
- Complex configuration systems for a small number of known settings.

Abstraction is justified by a clear need, not by the number of patterns used.

---

# 4. Domain and module boundaries

Group code around business capabilities and concepts where practical.

A domain boundary should have high cohesion and controlled coupling.

Ask:

- Does this module own a distinct business capability?
- Are its rules and data related?
- Can its behavior be understood without knowing unrelated modules?
- Does another module depend on its public contract rather than its internal details?
- Is the dependency direction stable?

Keep cross-module communication explicit. Avoid circular dependencies and shared mutable internals.

Do not let a generic `utils`, `common` or `helpers` module become the home of unrelated business behavior.

Do not fragment a small product into dozens of tiny modules that make ordinary changes expensive.

## 4.1 Dependency direction

Keep high-level business rules independent of replaceable delivery and infrastructure details where this creates a meaningful benefit.

External services, databases and framework APIs should not spread through every module.

Use adapters or boundaries where they isolate meaningful external dependencies. Do not add an abstraction layer around every function.

## 4.2 Public contracts

Define clear contracts between modules and services:

- Request and response shapes.
- Error forms.
- Authorization expectations.
- Ownership of validation.
- Timeout and retry behavior.
- Consistency guarantees.
- Versioning and compatibility rules.

Do not expose private database structures as permanent public API contracts without considering future migrations.

---

# 5. Data architecture

Data design is central to system correctness.

## 5.1 Model real entities and relationships

Understand the domain before creating tables or documents.

Define:

- Entities and their identities.
- Relationships and cardinality.
- Ownership and tenant boundaries.
- Required and optional fields.
- Unique constraints.
- Referential integrity.
- Lifecycle and status transitions.
- Deletion and retention behavior.
- Audit requirements.
- Query patterns and indexes.

Avoid storing the same authoritative fact in several places without a synchronization strategy.

## 5.2 Data integrity

Use database constraints, transactions and atomic operations to enforce invariants where supported.

Do not rely solely on frontend validation or a preliminary read before a critical write.

For concurrent operations, consider unique constraints, optimistic concurrency, row-level locking, conditional writes or other platform-appropriate mechanisms.

Do not assume a sequence of separate requests is atomic.

## 5.3 Schema evolution

Design migrations as controlled changes.

- Preserve existing data unless deletion is explicitly required and authorized.
- Prefer backward-compatible expand-and-contract migrations for systems that must remain available during deployment.
- Provide rollback or recovery considerations.
- Update application code and all known consumers.
- Test migrations against representative data where practical.
- Document irreversible operations and required backups.

Do not silently change field meaning or reuse a column for a different concept.

## 5.4 Data access patterns

Design indexes and queries around real access patterns.

Avoid N+1 queries, unbounded list reads, broad over-fetching and unbounded scans.

Use pagination and predictable ordering for growing collections. Define consistency expectations for pagination and concurrent changes.

---

# 6. API and integration architecture

Treat APIs as explicit contracts, not incidental function calls.

## 6.1 API design

Define:

- Resource or operation semantics.
- Authentication and authorization.
- Input validation.
- Response shape.
- Error shape and status behavior.
- Pagination and filtering.
- Idempotency for consequential writes.
- Rate limiting and abuse controls where necessary.
- Versioning and compatibility expectations.

Use consistent naming and predictable behavior. Do not expose internal stack traces, database errors or secrets.

## 6.2 External providers

Treat external providers as unreliable dependencies.

Account for:

- Timeouts.
- Rate limits.
- Authentication expiry.
- Partial outages.
- Duplicate webhooks.
- Out-of-order events.
- Malformed responses.
- Schema changes.
- Provider-side retries.
- Reconciliation needs.

Keep provider-specific details behind a meaningful adapter when this prevents vendor behavior from contaminating core domain logic.

## 6.3 Webhooks and event delivery

Verify webhook authenticity using the provider's documented method. Validate payloads. Store event identifiers where needed to detect duplicates. Design handlers to be idempotent. Acknowledge events only according to the provider's delivery contract and the application's durability guarantees.

Do not assume exactly-once delivery. Most distributed delivery systems require idempotent handling of at-least-once delivery.

## 6.4 Asynchronous work

Use background jobs or queues when there is a real need for work to continue independently of a request, be retried, be scheduled or be processed at a different rate.

Define:

- Job ownership.
- Delivery semantics.
- Retry policy.
- Dead-letter or failure handling.
- Idempotency.
- Ordering requirements.
- Visibility and monitoring.
- Cancellation and expiration.

Do not introduce a queue for a small synchronous operation without a concrete benefit.

---

# 7. Security architecture and threat modeling

Security must be designed into boundaries, flows and data ownership.

## 7.1 Threat model

For consequential features, identify:

- Assets to protect.
- Actors and trust boundaries.
- Entry points.
- Sensitive data flows.
- Abuse cases.
- Likely threats.
- Existing mitigations.
- Residual risks.

Consider account takeover, privilege escalation, insecure direct object references, cross-tenant access, injection, file abuse, replay, brute force, data leakage, webhook spoofing and denial of service as relevant to the product.

Do not use a generic threat list as proof of a complete threat model. Evaluate which threats actually apply.

## 7.2 Authorization architecture

Enforce access control on the trusted server or backend. Make ownership and tenant scoping explicit in data access paths. Use deny-by-default behavior for protected operations.

Client-side route guards improve experience but are not security controls.

Avoid a design where every route separately reimplements inconsistent permission checks.

## 7.3 Secrets and sensitive data

Keep secrets out of source control, client bundles, logs and URLs. Use appropriate secret storage and rotation practices. Minimize personal-data collection and retention. Restrict access to sensitive records and audit access where the risk warrants it.

## 7.4 Secure defaults

Prefer secure configuration by default. Make debug endpoints, permissive CORS, development credentials, test bypasses and verbose errors unavailable in production.

Do not assume infrastructure defaults are safe; inspect actual deployed configuration where tools permit.

---

# 8. Reliability, consistency and failure design

For each critical workflow, identify what can fail and what state remains afterward.

## 8.1 Failure boundaries

Consider failure of:

- The client.
- The network.
- The application process.
- The database.
- A third-party provider.
- A queue or background worker.
- A deployment or migration.
- A storage service.

Define timeouts, retries, fallback behavior and user-visible status where appropriate.

## 8.2 Idempotency and duplicate prevention

For operations such as payment, order creation, booking, subscription changes and message sending, decide how duplicate requests are detected and handled.

Use idempotency keys, provider transaction references, unique constraints or another appropriate mechanism.

Do not rely on frontend button state to prevent duplicate backend operations.

## 8.3 Transactions and distributed workflows

Use database transactions for changes that must be atomic within one transactional boundary.

For multi-system workflows, define a durable state machine, outbox/inbox pattern, reconciliation process or compensating action where appropriate. Do not pretend a database transaction can atomically include an unrelated external provider.

Avoid distributed transactions unless the constraints genuinely require them and the team can operate them.

## 8.4 Backups and recovery

For important data, define backup frequency, retention, restore process and recovery objectives proportionate to business risk. A backup is not proven until restoration has been tested.

Do not claim recoverability because a cloud provider advertises backups.

---

# 9. State management and client architecture

For UI applications, decide deliberately:

- Which state is local to a component.
- Which state is shared across a route or feature.
- Which state is server-owned.
- Which state belongs in the URL.
- Which state must persist across reloads.
- Which state is ephemeral.

Avoid duplicate sources of truth. Do not copy server data into multiple stores without an invalidation and synchronization strategy.

Keep business rules out of presentation components when they need to be shared, tested or enforced on the server.

Do not introduce a global state library for state that local component state or the existing data-fetching layer can handle cleanly.

Model loading, success, empty, error, offline and stale states where they affect the user journey.

For mobile and low-network contexts, consider persistence, retry, synchronization, conflict handling and interrupted workflows explicitly.

---

# 10. Infrastructure and deployment architecture

Choose infrastructure that the project can afford, understand and operate.

For each service, identify:

- Why it exists.
- What data or workload it owns.
- Its cost model.
- Its operational responsibility.
- Its security configuration.
- Its availability and failure behavior.
- Its backup and recovery path.
- How it is monitored.
- How it can be replaced or migrated.

Avoid multiple providers for the same capability without a clear reason.

Separate development, test and production environments. Keep environment-specific secrets out of source. Make deployment configuration reproducible. Define health checks and safe startup/shutdown behavior where appropriate.

Do not claim production readiness without reviewing the real deployment and operational configuration.

---

# 11. Observability and operations

A system must provide enough evidence to understand failures.

Use appropriate:

- Structured logs.
- Request or correlation identifiers.
- Error reporting.
- Metrics.
- Traces where distributed flows justify them.
- Health checks.
- Audit events for sensitive actions.

Logs must not expose passwords, tokens or unnecessary sensitive data.

Monitor critical workflows, not just server availability. Define what operators should do when an alert fires.

Do not add a large observability platform without a clear need, but do not leave production failures impossible to diagnose.

---

# 12. Performance and capacity planning

Do not optimize for imaginary traffic or design around unsupported numerical assumptions.

Establish workload characteristics where possible:

- Read/write ratio.
- Payload sizes.
- Peak concurrency.
- Data growth.
- Latency sensitivity.
- Mobile and network conditions.
- Provider quotas.

Use measurements or explicit estimates with assumptions stated. Identify likely bottlenecks and avoid premature distributed complexity.

Prefer designs that can be evolved in response to evidence: clear module boundaries, indexed data access, bounded work, cacheable reads where correct, and replaceable external adapters.

Do not promise infinite scalability.

---

# 13. Architecture decisions and documentation

Record important decisions in concise Architecture Decision Records (ADRs) when the decision is consequential, difficult to reverse or likely to be questioned later.

An ADR should include:

1. Title and status.
2. Context and verified constraints.
3. Decision.
4. Alternatives considered.
5. Reasons for rejecting alternatives.
6. Consequences and trade-offs.
7. Security, cost and operational effects.
8. Revisit conditions.

Do not create an ADR for every trivial implementation choice.

Keep diagrams aligned with the real system. A diagram that does not match the code or deployment is harmful documentation.

The architecture document should help a developer answer: where does this behavior belong, what owns this data, what can call this module, and what happens when a dependency fails?

---

# 14. Architecture review gate

Before implementation or approving a major change, verify:

- [ ] Product workflows and acceptance conditions are understood.
- [ ] Confirmed facts, assumptions, unknowns and constraints are distinguished.
- [ ] Existing architecture and contracts were inspected.
- [ ] Component responsibilities and boundaries are explicit.
- [ ] Data ownership and source of truth are clear.
- [ ] Authorization and tenant boundaries are enforced in trusted layers.
- [ ] API and provider contracts are defined.
- [ ] Failure, retry and idempotency behavior is considered.
- [ ] Concurrency and data integrity are addressed.
- [ ] Schema evolution and migration risks are considered.
- [ ] Infrastructure cost and operational burden are proportionate.
- [ ] Observability and recovery are adequate for the risk.
- [ ] Performance decisions are supported by workload evidence or stated assumptions.
- [ ] The design does not introduce unnecessary services or abstractions.
- [ ] Testing boundaries are clear.
- [ ] Major decisions and trade-offs are documented.

Do not mark an item complete merely because it appears in a diagram or a planning note. Verify the corresponding design decision.

---

# 15. Architecture change protocol for existing systems

Do not rewrite an application simply because a different architecture looks cleaner.

Before a restructure:

1. Establish the current behavior and dependencies.
2. Identify the actual defect or limitation.
3. Define the desired state and measurable benefit.
4. Identify affected modules, data, APIs and deployments.
5. Plan an incremental migration where practical.
6. Preserve compatibility or define a migration plan.
7. Add characterization or regression tests before risky changes.
8. Make one coherent change at a time.
9. Verify the behavior after each meaningful step.
10. Remove obsolete code only after confirming it has no active consumers.

Do not combine unrelated refactors with a feature change unless the coupling makes separation unsafe or impractical. Explain the reason.

---

# 16. Final standard

Good architecture is not the most sophisticated diagram. It is a clear and defensible arrangement of responsibilities that makes the real product correct, secure, understandable and operable.

Choose boundaries for reasons. Make data ownership explicit. Design for failure. Keep complexity proportional. Record consequential trade-offs. Preserve working behavior. Make future change possible without building speculative machinery today.

**The architecture must serve the product and the people maintaining it, not the agent's desire to demonstrate technical sophistication.**
