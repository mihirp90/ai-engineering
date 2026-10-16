# Production-Grade AI + Distributed Systems — Master Topic Map

> **Purpose:** The integrated technical map for designing, building, evaluating, securing, and operating product-based AI systems with distributed software engineering where it creates real value. This is the master reference behind the individual topic tracks and the 26-week roadmap.

**Time budget:** 26 weeks × 15 hours/week ≈ 390 hours. The core roadmap delivers one scoped product; topic tracks deepen selected subjects. This map is intentionally broader than what can be mastered in six months. The target is a production-minded portfolio product plus evidence-backed engineering judgment—not implementation of every technology listed here.

**Flagship hypothesis:** Research Intelligence over a bounded public or appropriately licensed corpus. Confirm the first user, recurring task, data source, and success baseline at Week 8. Keep the design extensible, but do not build an unrestricted platform before product evidence exists.

## What production-grade means in this program

A product is not production-minded merely because it uses Kafka, Kubernetes, an LLM, or microservices. It should demonstrate:

- **User value:** named user workflow, measurable baseline, explicit scope and non-goals.
- **Correctness:** contracts, invariants, validation, transaction boundaries and failure-path tests.
- **Distributed correctness:** clear source of truth, delivery/order semantics, idempotency, bounded retries and recovery.
- **AI quality:** versioned evaluation data, baseline comparisons, citation/grounding checks where relevant, explicit abstention and reviewed failure cases.
- **Security:** least privilege, secret hygiene, untrusted-input boundaries, authorization and a threat model.
- **Operability:** useful logs, traces/metrics, health checks, runbook, latency/cost budget and recovery evidence.
- **Reproducibility:** setup instructions, pinned dependencies, migrations, CI, tests and repeatable demo.
- **Engineering judgment:** complexity is added only when workload, measurements or product requirements justify it.

Do not call a project production-ready without a real deployment context, security review, load expectations, operational ownership and tested recovery. Use the term **production-minded portfolio system** unless those requirements are genuinely met.

---

## Track 0 — Product discovery and requirements

### Topics and subtopics

- **User and problem:** persona, job-to-be-done, current process, pain, frequency, stakes, alternatives, accessibility and constraints.
- **Functional requirements:** primary/secondary workflows, permissions, history, export, feedback, admin/maintenance tasks, error/empty states and explicit non-goals.
- **Non-functional requirements:** throughput, latency percentiles, availability, durability, consistency, freshness, privacy, security, accessibility, maintainability and operating cost.
- **Success criteria:** baseline workflow, measurable improvement, acceptance criteria, evaluation set, severity categories and stopping conditions.
- **Data policy:** provenance, source license, attribution, retention, deletion, confidential data and source refresh.
- **Delivery boundaries:** MVP vs later phases; manual vs automated steps; deterministic vs model-assisted decisions.
- **Discovery artifacts:** one-page brief, user flow, use-case examples, risk register and decision log.

### Practice and evidence

Write a product brief, at least 10 representative user requests, five out-of-scope requests, and a baseline for the chosen workflow. Set thresholds only after measuring the baseline.

## Track 1 — Software engineering foundations

### Languages and runtimes

- **Python:** values/types, control flow, functions, modules/imports, collections, iterators/generators, classes/dataclasses, exceptions, context managers, typing, protocols, packaging, environments and dependency locking.
- **Java:** OOP, encapsulation, abstraction, composition/inheritance, SOLID, equals/hashCode, generics, collections, lambdas/streams, exceptions, JVM memory/GC/class loading/JIT, profiling and thread dumps.
- **TypeScript/JavaScript:** runtime vs static types, narrowing, unions, generics, async/Promise semantics, modules, build tooling and runtime validation.
- **Resource management:** file/socket/connection lifecycle, cancellation, cleanup, bounded memory and avoiding leaked threads/tasks.
- **Contracts:** DTOs/schemas, compatibility, versioning, validation, defaults and stable error envelopes.

### Code quality and maintainability

- Separate domain logic from I/O; use dependency inversion at meaningful boundaries; favor cohesive modules and explicit side effects.
- Readable control flow, useful names, small abstractions, avoiding speculative frameworks and duplicated policy logic.
- Error taxonomy: user input, domain conflict, transient dependency failure, permanent failure, authorization failure and internal defect.
- Configuration/secret handling: environment config, safe defaults, no secret literals and redacted logs.
- Build reproducibility: locked dependencies, pinned runtimes, clean checkout, deterministic tests and migrations.
- Code review: correctness, failure cases, readability, security, performance evidence and architecture fit.

### Testing

- Unit tests for pure logic; component tests for adapters; contract tests for APIs/events; integration tests against test dependencies; end-to-end tests for critical workflows.
- Fixtures, parameterization, mocks at external boundaries, fake clocks, deterministic IDs and isolation.
- Property-based/fuzz-testing concepts; boundary, malformed, duplicate, large, empty and unexpected-input cases.
- Concurrency/race tests, stress and load tests, fault injection.
- AI evaluation sets are different from ordinary unit tests: version them, label expected behavior, inspect misses and preserve regressions.

### Practice and evidence

A clean checkout runs tests using documented commands. Include success, boundary, malformed-input and dependency-failure cases. Explain which tests mock a dependency and which exercise the real integration.

## Track 2 — Backend, APIs, domain and service boundaries

### API design

- REST resource modeling, HTTP methods/status codes, pagination/filter/sort, idempotent commands, concurrency control and stable errors.
- OpenAPI, request/response schema validation, compatibility, deprecation, authentication and authorization.
- SSE/streaming only where the UX needs incremental results; handle cancellation, disconnects and bounded buffering.
- gRPC/protobuf concepts: service definitions, compatibility, deadlines, status codes, streaming, metadata, retry semantics and backpressure.
- Rate limits, quotas, request-size limits, timeout budgets and overload responses.

### Domain and application design

- Entities/value objects, invariants, state transitions, domain/application/infrastructure boundaries.
- Use cases, orchestration, transaction boundaries, repository interfaces, validation and side-effect isolation.
- Long-running jobs with job ID, state, cancellation, progress, result and failure detail.
- API versioning, idempotency keys, correlation IDs, stable pagination and optimistic concurrency using versions/ETags where appropriate.
- Multi-tenancy: tenant-scoped authorization, tenant identifiers in queries/keys/events, isolation tests and prevention of cross-tenant cache leakage.

### Java/Spring Boot specialization

- IoC/DI, bean lifecycle/scopes, profiles, auto-configuration, filters/interceptors, validation, exception mapping and Actuator.
- Transaction proxy boundaries, self-invocation, propagation/isolation, rollback rules, JPA/N+1 pitfalls, optimistic/pessimistic locking and pool sizing.
- Resilience: deadlines, capped retries/backoff, circuit-breaker/bulkhead concepts, fallback policy and idempotent consumers.
- Reactor/Mono/Flux, WebClient, cancellation, non-blocking I/O, backpressure, blocking-call hazards and thread model.
- REST/gRPC integration, security filters, metrics/traces, and safe configuration.

### Practice and evidence

Implement an API with typed contracts, stable failures, request IDs, idempotent behavior where needed, and contract/integration tests. Document why each component belongs in its layer.

## Track 3 — Data modeling, databases, caches and search

### Relational data

- Entity relationships, keys, normalization/denormalization, constraints, migrations and referential integrity.
- SQL joins, aggregations, CTEs, window functions, NULL semantics, date/time, parameterized queries and pagination.
- ACID, transaction scope, isolation levels, lost updates, locking, unique constraints and rollback.
- Index selection, composite/covering indexes, selectivity, EXPLAIN/ANALYZE, query plans, connection pools and slow-query investigation.
- Schema evolution, migration ordering, backward-compatible deployment, backup/restore and retention.

### Data stores and caches

- PostgreSQL as durable relational source of truth; JSON/JSONB and full-text search where justified.
- Redis data structures, TTL/expiry, eviction, cache-aside, invalidation, stampedes, stale reads, cache key design and pool limits.
- Cache vs source of truth; do not store irreplaceable state only in a cache unless the durability model supports it.
- OpenSearch: mappings/analyzers, inverted index, filters, ranking, refresh/visibility, shards/replicas, reindexing, index versioning and operations.
- Vector search: dimensions, similarity metric, embedding model/version, metadata filters, index recall/latency, freshness and stale embeddings.

### Ingestion and data quality

- Provenance/license, source URL/ID, retrieval time, modified time if available, checksum, parser version and source status.
- Batch sizing, checkpoints, incremental updates, deduplication, retries, malformed-record quarantine and dead-letter analysis.
- Schema validation, missing/outlier/conflicting values, freshness measures and reproducible data snapshots.
- Deletion/correction propagation across source data, chunks, embeddings, caches and indexes.

### Practice and evidence

Produce a schema/ER diagram, repeatable migration, query-plan comparison, cache-consistency decision and corpus manifest. Explain source of truth and safe rebuild/reindex behavior.

## Track 4 — Distributed systems fundamentals

### Core concepts

- Network latency, partial failure, partitions, timeouts, retries, clocks, process failure and correlated failures.
- Strong/eventual consistency, read-after-write, stale reads, linearizability/serializability at a useful conceptual level, availability trade-offs and consistency scope.
- Replication, partitioning/sharding, key choice, hot keys, skew, horizontal scaling and uneven load.
- Load balancing, service discovery, connection pooling, backpressure, bounded queues, bulkheads and load shedding.
- Idempotency, deduplication, at-most/at-least-once delivery, ordering constraints, replay and the scope of exactly-once claims.
- Sagas/compensating actions, outbox/inbox, dual-write hazards, transaction boundaries and distributed-lock limitations.
- Event time vs processing time, clock assumptions, monotonic IDs and avoiding wall-clock dependencies for correctness.
- CAP/PACELC as reasoning tools, not slogans; identify actual operation and consistency requirements.
- Failure-mode analysis, blast radius, graceful degradation and recovery objectives.

### Distributed-design questions

1. What is the source of truth?
2. What happens if a request succeeds but its response is lost?
3. Can an event be duplicated or delivered out of order?
4. How is partial completion represented and repaired?
5. What is the timeout/retry budget across the full call chain?
6. How will operators know which stage failed?
7. What can be reconstructed after a cache, index or worker is lost?

### Practice and evidence

Draw sequence diagrams for success, timeout, duplicate, retry, out-of-order and dependency outage. Include state transitions and repair/recovery paths.

## Track 5 — Event-driven systems, Kafka and asynchronous workflows

### Kafka

- Topics, partitions, keys, offsets, producer acknowledgments, replication, retention, consumer groups and rebalancing.
- Partitioning strategy, per-key ordering, hot partitions, consumer lag, parallelism and capacity estimates.
- At-most/at-least-once processing, idempotent producers, transactions and limits of end-to-end exactly-once guarantees.
- Consumer commit order, retry topics, dead-letter queues, delayed retries, poison messages and replay.
- Schema evolution, compatibility, event envelopes, timestamps, correlation/causation IDs and schema registry concepts.
- Outbox/inbox, CDC, dual writes, transactional state updates and event publication.
- Monitoring: lag, throughput, failures, expired events, rebalances, disk/retention pressure and safe replay.

### Async job/workflow model

- Durable job record and queued/running/succeeded/failed/cancelled states, leases/heartbeats and progress.
- At-least-once delivery, idempotent handler, dedupe key, attempt count, retry schedule, max attempts and dead-letter remediation.
- Work queues, worker concurrency, bounded queues, backpressure, cancellation, task timeouts and resource budgets.
- Fan-out/fan-in, dependencies, workflow versioning, compensation, approvals and resumability.
- Avoid holding HTTP connections for long jobs; return a job handle and offer status/events where appropriate.
- Distinguish event log, task queue, workflow engine and stream processor; choose by required semantics.

### Practice and evidence

Build or simulate a durable job with retries, duplicate delivery and a poison item. Demonstrate idempotency and safe operator replay.

## Track 6 — Stream processing and Apache Flink

### Fundamentals

- Streams vs batches, keyed streams, operators, transformations, event time, processing time, watermarks and late events.
- Windows, triggers, allowed lateness, stateful aggregation and hot/skewed keys.
- Managed/keyed state, state backend concepts, checkpoints, savepoints, restart strategies and recovery.
- Checkpoint barriers, backpressure, operator chaining, parallelism, key groups, rescaling and state migration.
- Source → operator state → sink delivery; transactional/idempotent sinks and external side-effect caveats.
- Schema evolution, replay, backfills, reprocessing, event-time correctness and state TTL.
- Monitoring busy/backpressured time, checkpoint duration/failure, lag, records in/out, restart count and state growth.
- Safe upgrades, savepoint-restore testing, checkpoint storage, capacity sizing and incident runbooks.

### AI + stream processing

- Separate low-latency deterministic decisions from slower model/LLM calls when appropriate.
- Streams can update features, create jobs, detect anomalies, or trigger asynchronous AI investigation; correlate outputs with source events.
- Define freshness, late-event and correction policies. Decide whether model output is advisory, a durable decision, or a downstream event.
- Never assume an LLM call per event gives predictable latency, ordering or exactly-once external effects.

### Practice and evidence

Demonstrate keyed state, late-event behavior, checkpoint/recovery reasoning and idempotent outputs with a small workload or design exercise. Use Flink only when stateful streaming/event time is needed.

## Track 7 — AI application and model engineering

### Model fundamentals and inference

- Tokens, context windows, tokenization, sampling, capability profiles, structured output, multimodal constraints and failure modes.
- Hosted vs local/open models: privacy, capability, latency, cost, availability, concurrency and hardware.
- Provider adapters, typed inputs/outputs, timeouts, rate limits, retries, cancellation, streaming, quota handling and fallback.
- Prompt/config versioning, feature flags, routing policy, normalization and model-deprecation strategy.
- Batching, caching, concurrency limits, queues, rate limiting, latency budgets and cost attribution.
- CPU/GPU/memory, quantization, throughput/latency trade-offs, cold starts, model serving and inference optimization as an elective after measurement.
- Schema validation, refusal paths, malformed/empty output and safe fallbacks.

### Prompt and context engineering

- Task contracts, instructions vs data, few-shot examples, decomposition, context selection and context budgets.
- Grounding, uncertainty, abstention, citations, ambiguity and conflict behavior.
- Injection resistance is a system property: delimit untrusted text, constrain tools, validate outputs and test adversarial inputs; prompt wording alone is not a security boundary.
- Link prompt/model versions to evaluations and traces.

### Embeddings and RAG

- Source ingestion, parsing, normalization, chunk boundaries, metadata, provenance, hashes and updates.
- Lexical retrieval baseline, full-text/BM25 ranking, embeddings, vector similarity, hybrid fusion, metadata filters and reranking.
- Query rewriting only when measured; preserve original query and inspect result changes.
- Context selection, token budget, source diversity, deduplication and conflict-aware assembly.
- Citation IDs mapped to actual passages; validate reference membership; distinguish evidence coverage from fluent generation.
- No-answer, stale/contradictory evidence, source freshness, access filtering and deletion propagation.
- Retrieval metrics (precision/recall at k, reciprocal rank), answer support/citation measures, task success and latency/cost reported separately.
- Version-aware cache keys and invalidation for retrieval/embedding caches.

### Evaluation and iteration

- Dataset sampling, labels, rubrics, leakage awareness, held-out cases and versioning.
- Deterministic unit/contract tests vs probabilistic eval cases; human review and judge calibration.
- Error taxonomy across source/data, parsing, retrieval, context, model, validation, tools, UI and operations.
- Baseline first; change one variable at a time; compare quality, latency and cost; preserve regression cases.
- Slice by query type, source, language, freshness, difficulty and severity instead of relying on one aggregate score.

### Practice and evidence

Publish a reproducible evaluation harness, fixed labeled queries, lexical/vector comparison, cited-answer tests, no-answer cases and failure analysis. Keep model-specific code behind a boundary.

## Track 8 — Agents, MCP and tool integration

### Workflow vs agent

- Deterministic workflow/state machine vs model-selected actions; identify where nondeterminism adds value.
- State, checkpointing, resumability, retry, step/token/time budgets, cancellation, loop prevention and stopping rules.
- Human approval, reversible actions, audit trail and responsibility for side effects.
- Tool selection/argument validation, result parsing, error handling and unavailable tools.
- Multi-agent concepts: coordination, delegation, shared state, message costs, consistency, evaluation and failure amplification. This is an advanced elective, not the default architecture.

### MCP

- Host/client/server roles, tools/resources/prompts, initialization/capability negotiation, transport/lifecycle, schemas and version compatibility.
- Discovery, typed arguments/results, errors, timeouts, cancellation, session handling, auth/consent and audit.
- Begin with read-only tools, explicit allowlists and least privilege. Do not expose arbitrary shell, unrestricted file access, secrets or consequential side effects without robust authorization and review.
- Treat tool results as untrusted; validate outputs and preserve provenance.
- Test unavailable server, malformed output, invalid arguments, injection attempts and timeout/cancellation.

### Practice and evidence

Compare a deterministic workflow to a bounded one-tool agent on the same cases. Retain autonomy only if measured benefit outweighs latency, cost, reliability and security complexity.

## Track 9 — Security, privacy and governance

### Application/platform security

- Threat modeling, trust boundaries, assets, abuse cases, assumptions and residual risks.
- Authentication, authorization, least privilege, tenant isolation, object-level checks and authorization in retrieval/tools.
- Secret management, rotation, dependency scanning, supply-chain provenance and least-privilege CI.
- Input validation, request/response size limits, SSRF protection, safe parsing, upload validation, output encoding and injection prevention.
- Encryption where appropriate, retention/deletion, backup protection and audit logging.
- API limits/quotas, abuse prevention, exfiltration controls, secure headers and defaults.
- Public data license/attribution; never include employer/customer/private data in a portfolio.

### AI-specific security

- Direct/indirect prompt injection, hostile retrieval, tool-result injection, cross-tenant leakage, sensitive-data exposure and unsafe rendering.
- Tool permission scopes, allowlists, approval gates, output validation, audit and side-effect containment.
- Poisoned/misleading sources, provenance, contradictory evidence, model supply chain and dependency updates.
- Red-team cases, severity, regression tests and explicit limitations.
- Redact secrets and unnecessary sensitive prompts from logs/traces.

### Practice and evidence

Produce a threat model, adversarial evaluation cases, tenant/source-filtering tests, residual-risk record and release blockers.

## Track 10 — Observability, reliability and SRE

### Observability

- Structured logs with correlation/request/job IDs; avoid unbounded/high-cardinality labels.
- Metrics for request rate/errors/latency, queue depth/age, consumer lag, retries, model tokens/cost, retrieval and evaluation results.
- Distributed traces across gateway, services, database, queue, retrieval and model provider.
- Health/readiness/liveness checks, dependency status, redaction, sampling and retention.
- Dashboards/alerts tied to user impact, not every internal variable.

### Reliability/SLOs

- Availability/latency SLOs, error budgets, freshness objectives, durability, RTO/RPO scoped to an actual deployment.
- Deadline propagation, retry budgets, jitter/caps, bulkheads, backpressure, load shedding and graceful degradation.
- Partial failure, fallback provider/model, queue age, retry exhaustion and poison messages.
- Capacity estimates, saturation signals, dependency limits, graceful shutdown and worker draining.
- Incident response, runbooks, postmortems, corrective actions and regression tests.
- Backup/restore, point-in-time recovery where applicable, replay and reindex procedures.

### Practice and evidence

Trace successful and failed requests end-to-end. Run a dependency-outage/recovery drill. Write a runbook that an unfamiliar engineer can follow.

## Track 11 — Performance, scale and cost

- Throughput vs latency, p50/p95/p99, queueing basics, Little's Law as a sizing aid, contention and saturation.
- CPU/memory/allocation/GC, DB pools, connection limits, event-loop blocking, network and serialization.
- Caching, batching, pagination, streaming, backpressure and concurrency bounds.
- Load generation, realistic workloads, warm/cold starts, soak tests and bottleneck diagnosis before tuning.
- Horizontal scaling, partitions, hot keys, skew, fan-out and downstream capacity.
- AI performance: token/context growth, prompt size, retrieval latency, model concurrency/rate limits, time-to-first-token, full-response latency and cost/task.
- Performance/cost budgets per user action; compare against product value.

**Evidence:** record a baseline before tuning; change one bottleneck at a time; preserve before/after results and note quality changes too.

## Track 12 — Frontend and user-facing product quality

- TypeScript API contracts, runtime validation and schema evolution.
- React component boundaries, state ownership, render/effect behavior, stale closures and cleanup.
- Async correctness: cancellation, request IDs, stale-response prevention, loading/error/empty states, retries and reconnection.
- Streaming responses, citation navigation, source inspector, conflicts, abstention, feedback and export.
- Accessibility: semantic HTML, keyboard navigation, labels, focus, status announcements, contrast and screen-reader support.
- Long-running jobs: progress, status, cancellation, partial results and recoverable errors.
- Behavior-focused component/E2E tests, network mocks and profiling.

**Evidence:** demonstrate the workflow keyboard-only; prove stale responses cannot overwrite the current selection; test loading/error/no-answer paths.

## Track 13 — Delivery, CI/CD and platform operations

- Git workflow, reviewable commits, branches/tags, rollback and repository structure.
- Reproducible runtimes/dependencies, build artifacts, container layers, non-root images, minimal images, health checks and environment separation.
- CI for lint/format, static/type checks, unit/integration/contract tests, evaluation smoke cases, dependency/security scan and reproducible builds.
- Configuration/secrets, migration ordering, backward compatibility, rolling deployments, feature flags and rollback.
- Deployment choice: local, low-cost host, managed DB/model service or container platform based on requirements and budget.
- Infrastructure as code/networking/TLS/resource limits only when useful.
- Release checklist, runbook, operational ownership, cost monitoring and data retention.

**Evidence:** fresh checkout can run tests and demo; CI catches regressions; run/deploy/recovery instructions are verified.

## Track 14 — System design and technical leadership

### System design

- FR/NFR, assumptions, workload/capacity estimates, availability/latency/durability/security/consistency.
- APIs, entity/schema design, indexes, partition keys, cache keys, events and source of truth.
- Left-to-right HLD, sync/async flows, lifecycle states, concurrency, idempotency and transaction boundaries.
- Bottlenecks, backpressure, failure modes, retries/DLQ, replay, degradation, disaster recovery and observability.
- Trade-offs: monolith vs services, REST vs gRPC, SQL vs NoSQL, queue vs stream, cache vs DB, workflow vs agent, hosted vs local model.
- Evolution: MVP architecture, scaling path, migration, compatibility and rollback/deletion path.
- Staff-level communication: decision record, alternatives, evidence, operating costs and what not to build.

### DSA

- Complexity, arrays/strings/hash maps, two pointers/sliding window/prefix sums, stacks/queues/monotonic structures.
- Sorting/search/binary search, intervals, heaps/top-k, linked lists, trees/BST, recursion/backtracking.
- Graphs/BFS/DFS/topological sort/union-find; greedy, dynamic programming and state compression.
- Practical problems: LRU, rate limiter, bounded queues, retries, concurrency-safe state and streaming aggregation.

**Evidence:** design writeups include requirements, scale, APIs, entities, complete HLD, flows, technology rationale, data model, concurrency/partitioning, failure modes and deep dives. DSA evidence includes brute force, optimized solution, tests and complexity.

---

## How tracks map to a production product

| Product capability | Required topic areas | Production evidence |
|---|---|---|
| User request/API | Product requirements, backend, security, frontend | Contract, validation, auth, error behavior, tracing |
| Source ingestion | Data, async work, distributed systems, delivery | Provenance, idempotency, quarantine, replay, freshness |
| Search/RAG | SQL/search, AI/RAG, evaluation, security | Retrieval baseline, relevance labels, citation checks, abstention |
| Model call | AI engineering, reliability, observability | Timeouts, quota handling, typed output, cost/latency, fallback |
| Background jobs/events | Distributed systems, Kafka, optional Flink | Retry/DLQ, duplicates, ordering, idempotency, lag/age metrics |
| Tool/agent workflow | MCP/agents, security, evaluation | Allowlist, schemas, budgets, audit and adversarial tests |
| User interface | React/TypeScript, API contracts, accessibility | Stale-response protection, clear errors and source inspection |
| Release/operations | DevOps, SRE, performance/security | CI, runbook, recovery drill, load/cost baseline |

## Six-month boundaries

390 hours cannot deeply implement every topic above. The mandatory path is: reproducible API/data foundation → measured model task → source-aware search/RAG → evaluation/security/observability → bounded tool decision → delivery and final evidence. Java, React, Kafka/Flink, OpenSearch, advanced model serving, Kubernetes and multi-agent systems are depth tracks or optional experiments selected by product and target-role evidence.

**Production-minded quality applies to what is built:** contracts, tests, failure handling, authorization, observability, measurement, provenance and documented trade-offs. Installing every technology is not the goal.
