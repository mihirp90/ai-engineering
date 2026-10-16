# Assessment and Evidence Plan

## Philosophy

Assessment must show independent engineering judgment, not just recall or a happy-path demo. Every substantial feature gets representative cases, a baseline, failure review, and repeatable regression checks. Automated/model-graded scores support but do not replace human review.

## Gates

| Gate | Required evidence | Pass criteria | If it misses |
|---|---|---|---|
| Week 1 baseline | Skill matrix + diagnostic lab | Strengths/gaps have concrete examples; clean setup works | Adjust foundations to actual gaps |
| Week 4 engineering | API, schema/migration, tests and CI | Another developer can reproduce; core failures tested | Repair Python/API/SQL basics |
| Week 8 product/LLM | Scope brief, user flow, baseline set | One user/task/data boundary and measurable criterion | Revisit discovery; don't build unspecified scope |
| Week 12 retrieval/RAG | Corpus manifest, labeled queries, evaluation report | Provenance retained, citations resolve, no-answer works | Improve corpus/retrieval or simplify |
| Week 16 trust/reliability | Threat model, traces, adversarial regressions | Trust boundaries and material failure modes visible | Limit deployment/tools and remediate |
| Week 21 tools/distributed | Agent decision/evaluation and workload decision | Tool use bounded and justified; infrastructure evidence-based | Document deferral; prioritize core reliability |
| Week 26 portfolio | Demo, report, runbook, final matrix | Independent reviewer can run/inspect and understand limits | Finish evidence before new work |

## Rubric (0–4)

| Score | Meaning | Evidence |
|---:|---|---|
| 0 | Not demonstrated | No artifact or cannot explain |
| 1 | Followed | Tutorial completed with substantial guidance; cannot adapt |
| 2 | Independent on normal cases | Built a feature and handled expected inputs |
| 3 | Robust and evaluated | Failure cases tested; results informed changes |
| 4 | Operable and explainable | Reproducible, observed, secure within scope; trade-offs and limits are clear |

By Week 26, target at least 3 in software quality, retrieval, evaluation, reliability and security; at least 2 in other core areas. Scores 3–4 require evidence links/examples.

## Product evaluation suite

Start with 20–30 representative cases; expand toward 50–100 curated cases only if time and value justify it. Each case has ID, intent, input, expected behavior, source references, labels, severity and review notes.

Test slices:
1. Typical answerable questions.
2. No-answer cases where the corpus lacks evidence.
3. Conflicting or dated sources.
4. Retrieval edge cases: exact names, synonyms, broad/narrow queries, filters and duplicates.
5. Ingestion errors: malformed, empty, oversized, unsupported or duplicate documents.
6. Security cases: direct/indirect injection, secret-seeking and unsafe rendering.
7. Operations cases: provider timeout/rate-limit, database unavailable, empty corpus and retry exhaustion.
8. Tool-use cases only if implemented: invalid arguments, unauthorized operation, unavailable tool, loop, cancellation and budget exhaustion.

## Measures

- **Retrieval:** relevant passage at k, precision/recall at k or reciprocal rank, source coverage.
- **Answer:** task completion, support for material claims, citation correctness, appropriate abstention.
- **Tool workflow:** task success, valid/necessary calls, policy violations, no looping.
- **System:** latency distribution, error rate, approximate cost/task, retries and availability.
- **Human review:** blind-review a sample; compare automated scores with reviewer judgment and log disagreements.

Never let a single aggregate score hide severe misses. Record case-set and configuration versions for each comparison.

## Feature review checklist

- [ ] Problem and success behavior stated.
- [ ] Baseline and representative cases exist before tuning.
- [ ] Input/output contract and failure paths defined.
- [ ] Normal, boundary, malformed and dependency failures tested.
- [ ] Results trace to a versioned implementation/configuration.
- [ ] Quality, latency and approximate cost considered.
- [ ] Trust boundaries, provenance and residual risks documented.
- [ ] Reproduction steps and interpretation documented.

## Topic-track assessment

Each chosen topic unit must produce evidence: runnable mini-lab, test suite, benchmark, architecture/decision note, or explanation with examples. Reading alone is not completion. Use the same 0–4 rubric in the skill matrix.

## Evidence conventions

Store evaluation data/reports in `evals/`, decisions in `docs/decisions/`, threat model in `docs/threat-model.md`, runbook in `docs/runbook.md`. Keep data legally safe; never commit secrets, private employer/customer content or tokens.
