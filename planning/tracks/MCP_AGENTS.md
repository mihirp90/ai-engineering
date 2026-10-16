# MCP and Agentic Systems Track

## Goal
Understand tool integration and agent orchestration while bounding permissions, cost, side effects and failures.

## Ordered roadmap

| Stage | Topics | Evidence |
|---|---|---|
| M1 — Workflow fundamentals | Explicit steps, state machines, branches, retry policy, stopping conditions and review | Deterministic workflow diagram |
| M2 — Tool boundary | Narrow schemas, validation, timeouts, auth, least privilege and side-effect classification | Tool contract and threat boundary |
| M3 — MCP concepts | Host/client/server, tools/resources/prompts, discovery, lifecycle, transports, versions and consent | Protocol concept note |
| M4 — Read-only server | FastMCP/official SDK, typed tools, resources, errors, logs and local tests | One read-only search/inspect tool |
| M5 — Client integration | Discovery, result validation, timeout/missing/invalid result paths and context handling | Integration tests and failure transcript |
| M6 — Agent basics | Model-selected tools, state boundaries, stopping criteria, step/token budgets and cancellation | Minimal single-tool experiment |
| M7 — Security controls | Untrusted tool results, escalation prevention, prompt injection, shell/code restrictions, safe writes and secrets | Allowlist and adversarial tests |
| M8 — Agent evaluation | Task success, tool/argument correctness, unnecessary calls, loops, violations, latency and cost | Side-by-side eval report |
| M9 — Human approval/audit | Approval checkpoints, audit records, idempotency for permitted writes and reversible actions | Workflow with explicit approval |
| M10 — Architecture decision | Workflow vs single agent vs deferral; complexity/reliability/risk | Decision record |

## Safety rules
Start with read-only tools. Do not expose shell execution, arbitrary file access, credentials or consequential external actions to an agent. Add writable tools only with a clear requirement, least-privilege controls, and tests for authorization/idempotency/recovery.

## References
- [MCP introduction](https://modelcontextprotocol.io/docs/getting-started/intro)
- [LangGraph workflows and agents](https://docs.langchain.com/oss/python/langgraph/workflows-agents)
- [OWASP Top 10 for Agentic Applications](https://genai.owasp.org/2025/12/09/owasp-genai-security-project-releases-top-10-risks-and-mitigations-for-agentic-ai-security/)

## Exit evidence
Show tool contract/permission boundary, failure and timeout behavior, comparison with a deterministic workflow, and why the agent's added complexity is worth it—or document deferral.
