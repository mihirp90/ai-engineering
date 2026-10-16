# Evaluation, Security and Observability Track

## Goal
Make AI quality measurable, failures diagnosable, and risks visible throughout the product lifecycle.

## Ordered roadmap

| Stage | Topics | Evidence |
|---|---|---|
| Q1 — Test strategy | Unit/integration/contract/evaluation tests; deterministic vs probabilistic checks; golden datasets | Test pyramid and baseline |
| Q2 — Dataset design | Representative sampling, labels, no-answer/conflict cases, severity and versioning | Dataset schema and case set |
| Q3 — Metrics | Retrieval precision/recall at k, reciprocal rank, grounded claims/citations, abstention, success, latency/cost | Metric definitions and report |
| Q4 — Human calibration | Review rubrics, blind review, reviewer disagreement and limits of LLM-as-judge | Calibration note and samples |
| Q5 — Failure analysis | Data/retrieval/context/model/validation/UI/ops; root cause vs symptom | Prioritized failure log |
| Q6 — Telemetry | Request IDs, structured logs, traces, spans, percentiles, high-cardinality and privacy | Traced success and failure |
| Q7 — Resilience | Timeouts, retry budgets, cancellation, bounded concurrency, degradation and recovery | Failure injection tests |
| Q8 — AI security | Prompt injection, untrusted retrieval, leakage, unsafe rendering, provenance, permissions, supply chain | Threat model and adversarial tests |
| Q9 — Tool security | Allowlists, argument validation, least privilege, approval, audit, side effects and idempotency | Tool policy tests |
| Q10 — Release gate | Regression criteria, acceptable risk, rollback and monitoring | Release checklist and residual-risk record |

## Quality principles
- Keep retrieval, answer correctness, citation correctness and abstention distinct.
- Never let an aggregate score hide severe failures.
- Version datasets/config; compare on the same fixed cases.
- Inspect misses manually; automated judges are supporting signals.
- Avoid collecting secrets or sensitive prompts in traces.
- Treat retrieved content and tool outputs as untrusted.
- Record residual risk honestly.

## References
- [Evaluation best practices](https://developers.openai.com/api/docs/guides/evaluation-best-practices)
- [pytest](https://docs.pytest.org/en/stable/)
- [OpenTelemetry](https://opentelemetry.io/docs/)
- [OWASP LLM Application risks](https://genai.owasp.org/resource/owasp-top-10-for-llm-applications-2025/)
- [OWASP Agentic Application risks](https://genai.owasp.org/2025/12/09/owasp-genai-security-project-releases-top-10-risks-and-mitigations-for-agentic-ai-security/)

## Exit evidence
Major capabilities have baseline cases, versioned evaluations, failure taxonomy, traceable outcomes, documented security boundaries and release decisions tied to evidence.
