# 26-Week Applied AI Engineering Roadmap

**Duration:** 26 weeks · **Total effort:** approximately 390 hours · **Pace:** 15 focused hours/week. Ten hours/week go to the core AI/product sequence; the remaining five hours are defined in [Program Flow](PROGRAM_FLOW.md).

Research Intelligence is a product hypothesis, not yet a fixed specification. Confirm the first user, task and corpus at Week 8—or revise the idea based on discovery evidence. Public/appropriately licensed data only.

## Month overview

| Month | Weeks | Focus | Month-end evidence |
|---|---:|---|---|
| 1 | 1–4 | Engineering foundation | Reproducible API/data service and CI |
| 2 | 5–8 | Model integration, evaluation, product scope | Baseline evaluation and agreed MVP |
| 3 | 9–12 | Ingestion, search, retrieval, RAG | Measured cited-answer slice |
| 4 | 13–16 | Reliability, observability, security | Reviewed beta and threat model |
| 5 | 17–21 | Workflows, MCP, agent decision, optional distributed processing | Bounded tool decision with evidence |
| 6 | 22–26 | Delivery, hardening, portfolio | Reproducible demo and final evidence |

## Month 1 — Engineering foundation

### Week 1 — Baseline and reproducible Python project
**Learn:** interpreter/environment, modules/imports, functions, tests and Git. **Build:** parse JSON, implement a pure function, write a pytest, run a CLI and explain a stack trace. **Evidence:** skill matrix with examples and one command for checks. **Exit:** clean setup succeeds and a failed test is understood.

### Week 2 — Python quality and failure paths
**Learn:** types, dataclasses/Pydantic, exceptions, collections, file I/O, logging, configuration and dependencies. **Build:** CLI ingestion of public JSON/CSV with validation. **Evidence:** valid, invalid, empty and duplicate input tests. **Exit:** deterministic behavior, no hard-coded secrets.

### Week 3 — HTTP/API contracts
**Learn:** methods/status codes, validation, pagination, idempotency, errors and OpenAPI. **Build:** typed FastAPI create/list/get endpoints. **Evidence:** success, malformed input, not-found and dependency-failure tests. **Exit:** client contract is clear without reading implementation.

### Week 4 — SQL, migrations, CI and Gate 1
**Learn:** keys, constraints, joins, indexes, transactions and migrations. **Build:** PostgreSQL persistence and repeatable migration; basic lint/test CI. **Evidence:** schema diagram and clean test run. **Gate:** clean setup and reproducible persistence; otherwise strengthen foundations.

## Month 2 — Model integration, evaluation and product scope

### Week 5 — Model adapter
**Learn:** API contracts, tokens/context, latency/cost, timeouts, rate limits, retries and cancellation. **Build:** narrow provider interface with typed response and safe configuration. **Evidence:** success plus mocked timeout/rate-limit/malformed-response tests.

### Week 6 — Task and context design
**Learn:** task contracts, trusted instructions vs untrusted data, examples, structured output, validation and abstention. **Build:** small extraction/summary task over fixed public texts. **Evidence:** expected properties for at least 20 representative cases and reviewed misses.

### Week 7 — Evaluation before tuning
**Learn:** golden cases, scoring, human review, configuration versioning and regression tests. **Build:** portable evaluator recording case/config/result/scores/approximate cost/latency/reviewer notes. **Evidence:** baseline, three error categories and regressions.

### Week 8 — Product discovery and Gate 2
**Learn:** user/job-to-be-done, baseline workflow, value measure, data rights and non-goals. **Build:** one-page product brief with one user, research task and corpus—or replace Research Intelligence. **Evidence:** success criteria, sample queries and source shortlist. **Gate:** do not broaden implementation until scope and baseline are clear.

## Month 3 — Ingestion, search, retrieval, RAG

### Week 9 — Source-aware ingestion
**Learn:** parsing, normalization, provenance, checksums, deduplication and quarantine. **Build:** ingest 20–50 documents from one public/appropriately licensed collection. **Evidence:** reproducible command, corpus manifest and parser diagnostics.

### Week 10 — Lexical-search baseline
**Learn:** tokenization, full-text ranking, filters, relevance labels and top-k metrics. **Build:** passage search with stable IDs and metadata filters. Label 15–25 realistic queries. **Evidence:** lexical baseline and failed-query notes.

### Week 11 — Embeddings and hybrid retrieval
**Learn:** embedding behavior, chunking, vector similarity, filters and hybrid ranking. **Build:** add one embedding model and compare using Week 10's query set. **Evidence:** side-by-side results and a decision grounded in evidence.

### Week 12 — Grounded answers and Gate 3
**Learn:** context assembly, claim/source mapping, citation correctness, conflict and no-answer. **Build:** cited answer slice with visible passages and abstention. **Evidence:** demo, separate retrieval/answer metrics and five reviewed failures. **Gate:** citations resolve and retrieval adds measured value over search.

## Month 4 — Evaluation, observability, security, reliability

### Week 13 — Error analysis
**Learn:** classify data, parsing, retrieval, context, model, validation, UI and operations failures. **Build:** prioritize by severity and fix one root cause at a time. **Evidence:** before/after evaluation and regression cases.

### Week 14 — Observability and economics
**Learn:** request IDs, structured logs, traces, latency percentiles, failure counts, cost estimates and privacy-aware retention. **Build:** trace request → retrieval → model → citation validation. **Evidence:** success/failure traces and baseline latency/cost report.

### Week 15 — Threat model and adversarial testing
**Learn:** trust boundaries, prompt injection, leakage, unsafe rendering, authorization, dependencies and audit. **Build:** threat model and adversarial/conflicting document tests. **Evidence:** abuse cases, mitigations, residual risks and regressions.

### Week 16 — Reliability/security Gate 4
**Learn:** bounded retries, timeout, graceful degradation, fallback and recovery. **Build:** simulate provider outage, empty corpus, malformed/oversized input and citation failure. **Evidence:** threat-model update, regression report, runbook. **Gate:** material failures are visible and remaining risks are explicit.

## Month 5 — Workflows, MCP, agent decision and distributed options

### Week 17 — Deterministic workflow first
**Learn:** state machines, retries, human checkpoints and stopping conditions. **Build:** explicit research workflow; identify decisions needing a model. **Evidence:** sequence diagram and agent/no-agent decision.

### Week 18 — MCP contracts
**Learn:** client/server, tools/resources/prompts, schemas, lifecycle, transports, consent and trust. **Build:** optional read-only search/inspection tool. **Evidence:** schema, permission boundary, test transcript and failure behavior.

### Week 19 — One bounded agent and comparison
**Learn:** tool selection, budgets, step limits, loop prevention, cancellation, approvals and injection in tool results. **Build:** one-tool agent only if useful; compare it with deterministic flow on the same cases. **Evidence:** success, invalid/unneeded calls, policy failures, cost and latency.

### Week 20 — Async ingestion and idempotency
**Learn:** queue/worker, at-least-once delivery, idempotency, retries, dead letters and ordering. **Build:** optional duplicate-safe background ingestion or fault-injection design lab. **Evidence:** retry experiment or evidence-backed deferral.

### Week 21 — Distributed-systems gate
**Learn:** partitioning, consumer groups, event time/state/checkpoints, caching and service boundaries. **Build:** workload-backed choice about Kafka/Flink/Redis; prototype only if justified. **Evidence:** capacity assumptions, fault/replay model, decision record. **Gate:** keep only complexity that solves a defined requirement.

## Month 6 — Delivery, operations, hardening and portfolio

### Week 22 — Reproducible packaging and CI
**Learn:** packages/containers, config separation, migrations, health checks and dependency checks. **Build:** CI for tests, lint/type checks and evaluation smoke cases. **Evidence:** clean CI and tested setup instructions.

### Week 23 — Deployment
**Learn:** hosting choices, secrets, networking, logs/metrics, resource sizing and cost. **Build:** low-cost deployment or reproducible local demo if hosting is not justified. **Evidence:** launch steps, health check and teardown.

### Week 24 — Operations and recovery
**Learn:** runbooks, backup/recovery, incident triage, limits and data retention. **Build:** recovery/debug drill. **Evidence:** runbook and recorded failure exercise.

### Week 25 — Integration and hardening
**Learn:** end-to-end regression, UI/accessibility, bottlenecks and technical debt. **Build:** integrate scoped features; rerun evaluations and tests; fix source-inspection/failure-state issues. **Evidence:** release checklist, regression comparison and architecture diagram.

### Week 26 — Final assessment and next-quarter plan
**Learn:** retrospective, evidence-based skill claims and role mapping. **Build:** final evaluation report, demo, skill matrix, two engineering trade-off stories and a 90-day plan. **Evidence:** reproducible product, provenance, threat model, runbook and honest limitations. **Gate:** an independent reviewer can inspect/run the work and understand quality criteria.

## Decision gates

| Week | Gate | Evidence |
|---:|---|---|
| 4 | Engineering foundation | Clean setup, API, migrations, tests, CI |
| 8 | Product/model scope | User/task boundary, baseline cases and data source |
| 12 | Retrieval/RAG | Corpus manifest, retrieval report and citations |
| 16 | Trust/reliability | Threat model, traces and adversarial regressions |
| 21 | Agent/distributed decision | Bounded tool evaluation or justified deferral; workload decision |
| 26 | Portfolio/final | Demo, report, runbook, final matrix and next plan |

If a gate fails, extend the calendar or reduce scope; do not skip verification to keep a date.
