# Detailed Curriculum

## Program goal

Develop the ability to design, build, evaluate, secure, and operate applied AI systems with evidence suitable for senior/staff-level engineering discussions. Learn through implementation and a scoped product, not framework badges.

## Operating assumptions

- **Length:** 26 weeks, approximately six months.
- **Pace:** 15 focused hours/week; about 390 total hours.
- **Weekly budget:** 10 hours core curriculum/product, 3 hours one focused topic track, 1 hour alternating system design/DSA, 1 hour reflection/planning.
- **Product hypothesis:** Research Intelligence over a bounded public/appropriately licensed corpus. Confirm the user/task/corpus at Week 8; change the concept if discovery evidence suggests another problem.
- **Primary language:** Python for AI services; Java/Spring Boot and React/TypeScript are maintained as explicit topic tracks and used in the product when justified.
- **Data policy:** retain provenance/licensing; never use employer/customer/private data or commit secrets.
- **Pacing:** stretch the calendar instead of skipping tests, evaluation, security, or reflection.

## Learning method

For each capability: define observable behavior → study a primary source → reproduce a small example → implement independently → test normal and failure paths → measure behavior → analyze misses → document decision and next step.

The weekly core sequence is in [ROADMAP.md](ROADMAP.md). Topic-by-topic syllabi are in [tracks/README.md](tracks/README.md); they are parallel roadmaps, not a demand to master every technology at once.

## Prerequisites and Week 1 diagnostic

Measure rather than assume: Python environments/imports, functions/collections, tests, HTTP/JSON, SQL, Git branches/commits, basic model API use, stack-trace reading, and explaining a component diagram. Put concrete examples in the skill matrix. Skip practice only when evidence shows independence; still keep the baseline artifact.

## Module A — Engineering foundations (Weeks 1–4)

**Outcome:** a reproducible service with a clear API contract and relational persistence.

**Topics:** Python modules/environments/types/exceptions; collections and file/JSON I/O; pytest, fixtures, parameterization and mocks; HTTP methods/status codes/validation/error contracts/OpenAPI; SQL keys/constraints/joins/indexes/transactions/migrations; Git and basic CI.

**Build:** diagnostic CLI → validated ingestion CLI → typed FastAPI endpoints → PostgreSQL persistence/migration → tests, logging and setup guide.

**Gate:** clean checkout runs; success/error paths are tested; migration is repeatable; no hard-coded credentials.

## Module B — LLM application engineering and product discovery (Weeks 5–8)

**Outcome:** a versioned model integration and measurable task baseline.

**Topics:** tokens/context, model capabilities/cost/latency, structured output, timeouts/rate limits/retries/cancellation; trusted instructions versus untrusted input; schema validation and abstention; golden cases, human review, model/prompt/config versioning; user/task discovery, baseline workflow, licensing and non-goals.

**Build:** provider adapter → structured extraction/summary task → 20–30 cases → portable evaluator → product brief and MVP boundary.

**Gate:** provider failures are observable, results reproducible, and a real user/task/corpus is selected or the product hypothesis is revised. No agent/RAG complexity before this gate.

## Module C — Data, search, and RAG (Weeks 9–12)

**Outcome:** reproducible source-aware ingestion and evidence-backed answers.

**Topics:** corpus licensing/provenance, parsing, normalization, checksums, deduplication and quarantine; lexical retrieval and metadata filtering; embeddings, chunking, vector similarity, hybrid retrieval and optional reranking; context assembly, citations, conflict handling, abstention and separate retrieval/answer metrics.

**Build:** public corpus manifest → deterministic ingestion → lexical baseline → embedding/hybrid comparison → cited-answer slice and no-answer behavior.

**Gate:** corpus rebuilds reproducibly, citations point to inspected passages, retrieval is measured against a baseline, and unsupported questions are handled explicitly.

## Module D — Evaluation, observability, reliability, security (Weeks 13–16)

**Outcome:** important failures are measurable, diagnosable, tested, and bounded by explicit controls.

**Topics:** error taxonomy, regression evaluation, structured logs/request IDs/traces, cost and latency, bounded retries/timeouts, graceful degradation, prompt injection, authorization, unsafe output rendering, secret hygiene, provenance, threat modeling and recovery.

**Build:** failure analysis → end-to-end traces → adversarial cases → threat model → provider/data failure tests → reviewed beta.

**Gate:** a reviewer can reproduce failures, identify their stage, and understand mitigations and residual risk.

## Module E — Workflows, agents, MCP, optional distributed processing (Weeks 17–21)

**Outcome:** choose the simplest reliable orchestration and expose tools with narrow permissions.

**Topics:** state machines versus model-directed actions; tool schemas and validation; MCP client/server/tools/resources/prompts/lifecycle; budgets, cancellation, loops and approval; tool-call evaluation; queue semantics, idempotency, retries, DLQ, Kafka/Flink only when justified.

**Build:** deterministic workflow → agent decision record → optional read-only MCP tool → compare deterministic versus agentic behavior → optional asynchronous ingestion or distributed-systems design exercise.

**Gate:** autonomy is justified by measured value or deferred. Tool access is least-privilege and tested. Infrastructure is not added merely to make the architecture look complex.

## Module F — Delivery, hardening, portfolio, career evidence (Weeks 22–26)

**Outcome:** a reproducible demo with quality, security, operability, and engineering evidence.

**Topics:** packaging/container setup, CI, config/secrets, migrations/health checks, low-cost deployment, runbooks/recovery, performance/cost boundaries, reviewer usability, architecture decisions, role requirements and interview stories.

**Build:** CI → deployment or reproducible local run → recovery drill → integration/performance/accessibility hardening → final evaluation/demo/90-day plan.

**Gate:** an independent reviewer can run or inspect the work, reproduce the evaluation, understand limits, and hear clear trade-off explanations.

## Topic-specific roadmaps

- [Java, OOP, JVM, concurrency, Spring](tracks/JAVA.md)
- [Python engineering](tracks/PYTHON.md)
- [React and TypeScript](tracks/REACT_TYPESCRIPT.md)
- [SQL, data modeling and search](tracks/DATA_SQL_SEARCH.md)
- [Distributed systems, Kafka, Flink, Redis](tracks/DISTRIBUTED_SYSTEMS.md)
- [LLM, embeddings, retrieval, RAG](tracks/AI_LLM_RAG.md)
- [MCP and agentic systems](tracks/MCP_AGENTS.md)
- [Evaluation, security, observability](tracks/EVALUATION_SECURITY_OBSERVABILITY.md)
- [System design and DSA](tracks/SYSTEM_DESIGN_DSA.md)
- [Delivery, DevOps, operations](tracks/DELIVERY_DEVOPS.md)

## Optional extensions

Choose from job-market evidence after the core: PyTorch/fine-tuning, advanced inference optimization, Kubernetes, multi-agent systems, advanced OpenSearch, deeper Flink state processing, or frontend performance. Do not displace evaluation, security, product completion, or evidence.

## Completion checklist

- [ ] Weekly outcomes and gates have evidence.
- [ ] Product is reproducible and useful for one bounded task.
- [ ] Evaluations include normal, no-answer, conflict, failure and adversarial cases.
- [ ] Data provenance, security boundaries, operation and limits are documented.
- [ ] Topic-track scores link to evidence.
- [ ] Demo, architecture, runbook and next-quarter plan are published.
