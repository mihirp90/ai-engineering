# Delivery, DevOps and Operations Track

## Goal
Make software reproducible, testable, deployable, observable and recoverable without building infrastructure the product doesn't need.

## Ordered roadmap

| Stage | Topics | Evidence |
|---|---|---|
| V1 — Git discipline | Status/diff/branch/commit, reviewable changes, .gitignore, secrets, tags and rollback | Clean history and contribution notes |
| V2 — Local reproducibility | Python runtime/dependencies, Java build, Node lock file, config, task shortcuts | Fresh-checkout setup guide |
| V3 — Quality pipeline | Format/lint, types, unit/integration tests, deterministic eval smoke test | CI workflow with visible failures |
| V4 — Containers | Images/layers, non-root user, build context, env/config, health checks and Compose | Reproducible local stack |
| V5 — Database lifecycle | Migrations, startup ordering, compatibility, backup/restore and test DB | Migration/recovery exercise |
| V6 — Secrets/supply chain | Secret manager/environment, credential boundaries, dependency updates and provenance | Secret scan and dependency review |
| V7 — Deployment | Low-cost host, networking/TLS, health/readiness, resources and teardown | Deploy or documented local demo |
| V8 — Operations | Logs, metrics, traces, runbook, backup/recovery, incident response | Simulated failure drill |
| V9 — Performance/cost | Load tests, concurrency, p95/p99, resource limits and model cost | Benchmark and capacity note |
| V10 — Release discipline | Versioning, rollback, release checklist, risks and demo script | Reproducible release candidate |

## References
- [Git](https://git-scm.com/doc)
- [GitHub Actions](https://docs.github.com/en/actions)
- [Docker getting started](https://docs.docker.com/get-started/)
- [OpenTelemetry](https://opentelemetry.io/docs/)
- Official docs for the selected host/model provider.

## Exit evidence
A clean checkout runs tests and launches the app; CI catches regressions; secrets aren't tracked; deploy/recovery steps are tested; costs and limitations are explicit.
