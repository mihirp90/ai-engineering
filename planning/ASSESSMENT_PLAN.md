# Assessment and Evidence Plan

## Assessment philosophy

Assessment should show independent engineering judgment, not just recall or a working happy path. Every substantial feature gets representative examples before implementation, a baseline, a failure review, and a repeatable regression check. Use model-graded scores only as supporting evidence; humans calibrate the criteria and inspect consequential misses.

## Gate map

| Gate | Required artifact | Pass criteria | If it misses |
| --- | --- | --- | --- |
| Week 1 baseline | Skill matrix and diagnostic lab | Gaps and strengths have concrete examples; clean setup works | Add foundation practice to Month 1 |
| Week 4 engineering | API, schema/migration, tests and CI evidence | Another person can reproduce; core success/error cases tested; migration repeatable | Extend the missing Python/API/SQL material before AI features |
| Week 8 product/LLM | Scope brief, user flow, baseline eval set | One user/task/data boundary; baseline and success criterion are measurable | Revisit discovery; don't build unspecified scope |
| Week 12 retrieval/RAG | Corpus manifest, labeled retrieval set, RAG eval report | Provenance retained; citations resolve; no-answer works; retrieval compared to baseline | Improve corpus/query labels or simplify to search |
| Week 16 trust/reliability | Threat model, traces, adversarial regression set | Major trust boundaries identified; no critical open issue hidden; failure modes visible | Keep deployment and tools local; remediate |
| Week 20 tool/agent | Decision record and tool evaluation | Agent is measured against deterministic flow; if used, tool access is narrow and bounded | Defer agent and invest in core product quality |
| Week 24 portfolio | Runnable demo, report, runbook, final matrix | Independent reviewer can understand, reproduce/inspect, and identify limits | Finish evidence before new project work |

## Rubric (score each 0–4)

| Score | Meaning | Evidence |
| ---: | --- | --- |
| 0 | Not demonstrated | No artifact or cannot explain the concept |
| 1 | Followed | Completed a tutorial with substantial guidance; cannot yet adapt it |
| 2 | Independent on normal cases | Built a small feature and handled expected inputs |
| 3 | Robust and evaluated | Tests/evals cover failures; results inform design changes |
| 4 | Operable and explainable | Observed, secure within stated scope, reproducible; trade-offs and limits are clear |

For the Week 24 core outcome, target at least 3 in software quality, retrieval, evaluation, reliability, and security; at least 2 in remaining core areas. Do not inflate scores: attach a concrete evidence link or example to every score of 3 or 4.

## Product evaluation suite

Maintain a small version-controlled set initially, growing from 20–30 baseline cases to around 50–100 curated cases if time allows. Quality matters more than size. Each case should have an ID, user intent, input, expected behavior, source references where relevant, labels, severity, and review notes.

### Test slices

1. **Typical questions:** answerable from one or more documents.
2. **No-answer:** corpus lacks the evidence; system should abstain or say what is missing.
3. **Conflicting/dated sources:** identify conflict or temporal limitation rather than flatten it.
4. **Retrieval edge cases:** exact names, synonyms, broad/narrow query, metadata filter, duplicate passage.
5. **Ingestion edge cases:** malformed, empty, oversized, unsupported, duplicate documents.
6. **Security:** direct and indirect prompt-injection content, secret-seeking content, unsafe rendered output.
7. **Operations:** provider timeout/rate limit, database unavailable, empty corpus, retry exhaustion.
8. **Tool use (only if implemented):** invalid arguments, unauthorized operation, unavailable tool, loop, cancellation, budget exhaustion.

### Metrics and review

- **Retrieval:** relevant passage at k; precision/recall at k or reciprocal rank on human labels; exact-source coverage.
- **Answer:** task completion against a checklist; factual support of material claims; citation resolution/correctness; appropriate abstention.
- **Tool workflow:** task success; valid and necessary calls; permission/policy violations; completion without loop.
- **System:** latency distribution, error rate, estimated cost/task, retries, and availability in the tested setup.
- **Human review:** blind-review a sample of outputs; compare automated score to reviewer judgment; record disagreement and revise rubric.

Never reduce quality to one aggregate score. Keep failure examples, severity, responsible stage, and decision taken. Report the dataset version and system configuration for each comparison.

## Review checklist for a feature

- [ ] User problem and success behavior are stated.
- [ ] Baseline and representative cases exist before tuning.
- [ ] Input/output contract and failure paths are defined.
- [ ] Tests cover normal, boundary, malformed, and dependency failures as appropriate.
- [ ] Results can be traced to a versioned implementation/configuration.
- [ ] Quality, latency, and approximate cost were considered.
- [ ] Trust boundaries, data provenance, and residual risks are documented.
- [ ] README or design note explains how to reproduce and interpret evidence.

## Evidence folder convention

Store concise evidence alongside the lab or project: `evals/` for datasets/reports, `docs/decisions/` for decision records, `docs/threat-model.md`, `docs/runbook.md`, and a demo script. Keep datasets small and legally safe. Never commit secrets, private customer/employer content, or access tokens.
