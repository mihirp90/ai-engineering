# 24-Week Applied AI Engineering Roadmap

**Duration:** 6 months · **Pace:** 10 focused hours/week (about 240 hours) · **Primary outcome:** a reproducible research-intelligence application plus evidence of engineering, evaluation, security, and operations skills.

This is a sequenced working plan, not a fixed-date promise. The weekly learning cadence is in [Program Flow](PROGRAM_FLOW.md). Learning objectives and module explanations are in the [curriculum](CURRICULUM.md). Weeks 8, 12, 16, and 20 are gates: use evidence to decide whether to proceed, revise, or reduce scope.

## Six-month flow at a glance

| Month | Weeks | Primary capability | Product state at month end | Gate |
| --- | --- | --- | --- | --- |
| 1. Build the engineering base | 1–4 | Python, API, SQL, tests, Git/CI | Reliable service skeleton | Can another developer run and verify it? |
| 2. Add an AI task responsibly | 5–8 | Model integration, structured output, evals, product discovery | Agreed use case and measured baseline | Is the user/problem/data boundary specific enough to build? |
| 3. Make knowledge searchable | 9–12 | Ingestion, lexical/semantic retrieval, RAG, citations | End-to-end evidence-grounded research slice | Does retrieval improve measured task outcomes? |
| 4. Make it trustworthy | 13–16 | Evaluation, observability, reliability, security | Reviewed beta with threat model | Are failures visible and material risks mitigated? |
| 5. Add bounded tool use | 17–20 | Workflow vs agent, MCP, optional queue | Evaluated tool workflow or documented deferral | Does an agent beat a simpler workflow safely? |
| 6. Ship and communicate | 21–24 | CI/deployment, operations, portfolio, role alignment | Reproducible demo and career evidence | Can someone independently inspect and run the work? |

## Month 1 — Engineering base

### Week 1 — Baseline and reproducible Python project

**Learn:** Python environment/interpreter, modules/imports, virtual environments, package layout, Git status/branch/commit, pytest basics. **Build:** diagnostic tasks in `labs/python/week-01-baseline/`: parse JSON, write one pure function, write a test, run a CLI, explain a stack trace. **Evidence:** initial skill matrix ratings cite examples; new project has README, pinned/runtime guidance, one command for checks. **Exit:** clean setup succeeds and a failing test is understood and fixed.

### Week 2 — Python quality and external boundaries

**Learn:** type hints, dataclasses or Pydantic models, exceptions, context managers, logging, environment configuration, dependency boundaries; unit vs integration testing. **Build:** CLI ingestion of a small public JSON/CSV fixture, validation, useful error summaries, and structured logs. Inject malformed input and a missing-file error. **Evidence:** tests for valid, invalid, empty, and duplicate records; short note on exception vs validation error. **Exit:** behavior is deterministic and no credentials/configuration are hard-coded.

### Week 3 — HTTP and service contracts

**Learn:** request/response lifecycle, methods/status codes, JSON schema, validation, pagination, idempotency, error envelope, OpenAPI. **Build:** FastAPI service for create/list/get on an in-memory collection; define request and response models; add contract-focused tests. **Evidence:** API examples and `/docs` screenshot or saved schema; tests for 400/404 and malformed requests. **Exit:** client can predict responses from the contract without reading implementation internals.

### Week 4 — Relational data and first gate

**Learn:** relational design, keys, constraints, joins, indexes, transaction boundaries, migrations, connection lifecycle. **Build:** persist Week 3 records in PostgreSQL; add one migration and prove a failed operation does not partially modify data. Add CI checks for tests and lint/type checks. **Evidence:** schema diagram, migration instructions, CI result, Week 4 assessment. **Gate:** revise pace and identify Python/API gaps before model work; do not progress if the service cannot be reproduced.

## Month 2 — LLM task, evaluation, product scope

### Week 5 — Model API and provider boundary

**Learn:** request/response payloads, tokens and context, structured outputs, timeouts, rate limits, retries, cancellation, cost/latency. **Build:** provider adapter with a typed input/output interface; configure via environment; never log secrets. Stub the provider in fast tests. **Evidence:** one successful response plus tests for timeout, rate-limit and malformed output; record baseline latency and estimated cost. **Exit:** provider-specific code is isolated from domain logic.

### Week 6 — Prompt and context design

**Learn:** separate instructions from untrusted input, task specification, examples, schema validation, uncertainty/abstention, context budgets. **Build:** small source-grounded extraction or brief-generation task using a fixed set of public texts. Write the system behavior as observable requirements, not style adjectives. **Evidence:** at least 20 representative input cases and expected properties; sample failure annotations. **Exit:** output is validated and a bad/empty answer has a defined application path.

### Week 7 — Evaluation-first iteration

**Learn:** test-set coverage, golden cases, deterministic metrics, human review, model judge limitations, regression tests, prompt/model versioning. **Build:** local evaluation runner that records case ID, config, output, scores, cost/latency estimate, and reviewer notes. Compare baseline with one controlled change at a time. **Evidence:** baseline report, at least 3 error categories, a regression case added for each important failure. **Exit:** a reviewer can reproduce the comparison. Prefer a small local harness over depending on a vendor-hosted eval feature.

### Week 8 — Product discovery and scope gate

**Learn:** user/job-to-be-done, current workaround, evidence of value, data licensing/provenance, success and non-goals. **Build:** one-page product brief for Research Intelligence; choose one user, one research task, one corpus boundary, and an MVP. Sketch a user flow and context/data boundaries. Review a small sample of current target-role job descriptions and note repeated skills. **Evidence:** signed-off scope decision record, success metric definitions, data source shortlist, updated skill matrix. **Gate:** no major product build until the user/problem and corpus are specific enough. If not, spend a week interviewing/researching instead of coding.

## Month 3 — Ingestion, search, retrieval-augmented answers

### Week 9 — Document ingestion and provenance

**Learn:** document formats, parsing, normalization, content hashes, metadata, source attribution, duplicate detection, incremental reprocessing, error quarantine. **Build:** import 20–50 documents from one selected public corpus; retain source URL, title, dates if available, license/provenance note, fetched time, checksum, parser version. **Evidence:** repeatable ingestion command, corpus manifest, diagnostics for failed documents. **Exit:** the corpus can be rebuilt without losing provenance.

### Week 10 — Lexical search baseline

**Learn:** query analysis, tokenization, full-text search, ranking, filters, precision/recall, relevance judgments. **Build:** search endpoint with lexical retrieval, metadata filters, deterministic result IDs and passage previews. Label 15–25 real queries and relevant passages. **Evidence:** retrieval dataset and first top-k baseline; include exact-name and broad-topic queries. **Exit:** search is useful without an LLM and failure cases are visible.

### Week 11 — Semantic retrieval experiment

**Learn:** embedding model input/output, vector similarity limitations, chunk sizes/overlap, metadata filtering, hybrid fusion, reranker purpose. **Build:** add embeddings to the same corpus; compare lexical vs semantic results on the exact Week 10 set. Keep data schema and embedding model/version explicit. **Evidence:** side-by-side retrieval report; record queries helped and harmed. **Exit:** choose lexical, semantic, or hybrid based on evidence; do not add reranking unless it solves a measured miss.

### Week 12 — RAG answer slice and retrieval gate

**Learn:** evidence selection, context assembly, citation mapping, grounding, no-answer behavior, source conflict, citation correctness. **Build:** answer a question from retrieved passages; expose source passages and citations; abstain when evidence is insufficient. Score retrieval and answer separately. **Evidence:** reproducible end-to-end demo; report on the fixed set; 5 reviewed failure examples. **Gate:** continue only if citations resolve and answers are more useful than search alone. Simplify or change corpus if the data is poor.

## Month 4 — Quality, observability, security

### Week 13 — Error analysis and reliability patterns

**Learn:** error taxonomy (ingestion, retrieval, context, model, validation, UX, operations), timeout/retry policy, empty state, degraded mode, idempotency. **Build:** classify all known misses; improve one issue per category only where supported. Add deterministic validation and bounded retry behavior. **Evidence:** before/after eval report; explicit no-provider/no-results behavior. **Exit:** recurring errors can be traced to a system stage.

### Week 14 — Observability and cost/latency

**Learn:** request IDs, structured logs, traces, latency percentiles, token and provider costs, privacy-aware data retention. **Build:** trace request → query transform (if any) → retrieval → model → citation validation; add safe logs and a simple local report. **Evidence:** trace of one success and two failure cases, latency/cost estimate by stage. **Exit:** diagnose why an answer failed without dumping secrets or relying on model-visible chain-of-thought.

### Week 15 — Security threat model and adversarial tests

**Learn:** assets, trust boundaries, prompt injection, indirect instruction attacks in documents, sensitive-information exposure, unsafe output rendering, supply chain/model provenance. **Build:** threat model for user, corpus, ingestion, model, database, API, logs; include adversarial public document/query cases; mitigate using isolation, validation, access control, and explicit tool boundaries. **Evidence:** threat table with likelihood/impact, mitigations, residual risks, test outcomes. **Exit:** untrusted document content cannot silently become authorization or tool instructions.

### Week 16 — Product review and security gate

**Learn:** release readiness, accessibility/usability feedback, recovery/backup basics, incident notes. **Build:** walk a reviewer through a focused research task; fix top 2–3 evidenced problems; simulate provider failure and malformed document; update threat model. **Evidence:** review notes, release checklist, eval regression report, updated skill matrix. **Gate:** no tool execution or public deployment until key data/security risks are understood and mitigated.

## Month 5 — Workflow, agents, MCP, optional distributed systems

### Week 17 — Deterministic workflow before agent

**Learn:** state machines, workflow graphs, decision points, retries, human review, stopping conditions; distinguish a workflow with model steps from an agent with model-selected actions. **Build:** express research workflow as explicit stages; mark decisions the model must make and decisions code should own. **Evidence:** sequence/state diagram and decision record: agent needed / deferred / not needed. **Exit:** there is a specific measurable reason for adding agent autonomy.

### Week 18 — MCP and tool contracts

**Learn:** MCP client/server, tools/resources/prompts, schema validation, transports/lifecycle, versioning and trust. **Build:** if useful, expose one read-only operation (e.g., search documents) through a local MCP server; otherwise write a protocol evaluation note and keep the product simple. **Evidence:** tool schema, permission boundary, protocol test/manual transcript, failure behavior. **Exit:** no arbitrary shell, write, or account-access tool is exposed.

### Week 19 — Bounded agent and agent evaluation

**Learn:** tool selection and arguments, state persistence, budget/step limits, loop prevention, cancellation, approval checkpoint, prompt injection through tool results. **Build:** minimal one-tool agent for one research task only if it beats deterministic flow; compare both with identical eval cases. **Evidence:** task success, unnecessary calls, invalid calls, policy violation, latency and cost counts. **Exit:** retain the agent only if measured value exceeds complexity and security risk.

### Week 20 — Optional asynchronous ingestion and gate

**Learn:** queue/worker separation, at-least-once delivery, idempotency, retry and dead-letter queues, ordering and schema evolution; Kafka/Flink concepts only as needed. **Build:** optional background ingestion job with duplicate-safe processing and retry visibility. If not needed, do a written architecture exercise using the product’s real workload assumptions. **Evidence:** duplicate/retry experiment or architecture decision record; Month 5 review. **Gate:** keep distributed infrastructure out of the MVP unless a real throughput/reliability requirement exists.

## Month 6 — Delivery, operations, portfolio

### Week 21 — Reproducible delivery and CI

**Learn:** container basics, config separation, migrations, health checks, GitHub Actions workflow, supply-chain/security checks. **Build:** CI runs formatting/lint, type checks, unit/integration tests, and a small deterministic eval smoke set; add container/dev setup if useful. **Evidence:** clean CI run, README setup tested from a clean environment, no secret in tracked files. **Exit:** a fresh checkout has a documented route to run.

### Week 22 — Deployment and operations

**Learn:** deployment choices, secrets, logs/metrics, backup/recovery, health/readiness, rate limits, cost guardrails, teardown/data retention. **Build:** deploy a small demo or document and verify local deployment if hosting introduces unnecessary cost/risk; add runbook and failure procedures. **Evidence:** demo URL or recorded local launch steps; recovery/debug exercise; cost/latency budget and known limit. **Exit:** operators know how to start, inspect, and recover the demo.

### Week 23 — Portfolio communication

**Learn:** concise architecture storytelling, decision records, technical demo design, honest claims, portfolio readability. **Build:** project landing README, architecture diagram, evaluation summary, threat model summary, data provenance, demo script, limitations and future work. Ask one person unfamiliar with the code to follow the setup. **Evidence:** completed reviewer checklist and feedback fixes. **Exit:** a reviewer can explain what problem is solved and how quality is measured.

### Week 24 — Final assessment and next-quarter plan

**Learn:** retrospective, role requirement mapping, evidence-based skill claims, gap prioritization. **Build:** rerun all evaluations, complete final rubric and skill matrix, compare 8–12 current roles, select next 90-day specialization (applied AI, platform, ML engineering, enterprise Java, or data/streaming). **Evidence:** final report, portfolio demo, two interview stories (failure/trade-off), next 90-day roadmap. **Exit:** claims link to demonstrable work; unresolved gaps and limits are explicit.

## Monthly gates and what to do when a gate fails

| Gate | Proceed when | If not yet true |
| --- | --- | --- |
| Week 4 | Clean setup, API/data behavior, tests and migration are reproducible | Spend the next week strengthening the missing foundation before model work |
| Week 8 | One user, task, corpus boundary and measurable success criteria are named | Do discovery; revise the product rather than inventing features |
| Week 12 | Search/RAG has a measured baseline and citations are inspectable | Revisit corpus, query set, retrieval or abstention; do not add agents |
| Week 16 | Important security/reliability failures are handled and observable | Keep deployment/tool scope local and remediate first |
| Week 20 | Agent/tool decision is measured and permissions are narrow | Document deferral and use remaining time for product quality |
| Week 24 | A reviewer can run/inspect the work and understand limits | Finish the artifact and evidence before starting another project |
