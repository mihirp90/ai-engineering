# Python Engineering Track

## Goal
Build maintainable Python for AI services, ingestion, evaluation and tooling. Focus on packaging, typing, tests, failure handling and concurrency—not syntax alone.

## Ordered roadmap

| Stage | Topics | Evidence |
|---|---|---|
| P1 — Language fundamentals | Values, expressions, control flow, functions, scope, imports, comprehensions and idiomatic iteration | Small functions with boundary tests |
| P2 — Data structures | list/tuple/dict/set, sorting/keys, mutability/copying, iterators, complexity and memory | Transform/index a dataset; compare approaches |
| P3 — Function/object model | Parameters, closures, decorators, dataclasses, classes, composition, protocols/duck typing, dunder methods, equality/hash | Domain model with invariants and tests |
| P4 — Errors and resources | Exception hierarchy, context managers, pathlib, JSON/CSV, encoding, cleanup, logging | Robust file-ingestion CLI |
| P5 — Types and validation | Type hints, generics, unions, TypedDict/Protocol, Pydantic, validation boundaries | Typed contracts and invalid-input tests |
| P6 — Packaging/environment | Python version, uv/venv, lock files, pyproject.toml, package layout, CLI entry points, config/secrets | Clean install and one-command checks |
| P7 — Test engineering | pytest, fixtures, parametrization, mocks, monkeypatch, unit vs integration, deterministic tests, property-test concepts | Failure-focused test suite |
| P8 — HTTP/API/data | HTTP, JSON, FastAPI, request validation, stable errors, SQL, transactions and migrations | Tested service backed by PostgreSQL |
| P9 — Concurrency | Sync vs async; asyncio tasks/await/gather/semaphore; cancellation/timeouts; threads for blocking I/O; processes for CPU work; bounded concurrency | Benchmark sequential vs bounded concurrent processing |
| P10 — Production boundaries | Retries with jitter/caps, idempotency, logging/tracing, error classification, graceful degradation and dependency timeouts | Simulated dependency failures and useful logs |
| P11 — AI integration | Provider adapter, structured outputs, token/context budget, output validation, streaming and cancellation | Provider interface with mocked tests |
| P12 — Evaluation | Dataset schema, reproducible runs, deterministic metrics, reviewer notes, model/config versioning | Portable evaluation command and report |
| P13 — Performance/maintainability | Profiling, memory, clean abstractions, docs, lint/type checks and CI | Measured optimization and reviewed package |

## Suggested sequence
Weeks 1–4: P1–P7 foundation; weeks 5–8: P8 and model boundary; weeks 9–16: ingestion/reliability; weeks 17–21: P9/P11/P12 for tools and bounded concurrency; weeks 22–26: profiling, CI, delivery and hardening. The core roadmap sets product deadlines.

## Diagnostic checklist
Can install from project metadata; explain imports and working-directory assumptions; distinguish validation from infrastructure errors; test real behavior instead of mocking everything; bound concurrency; handle cancellation/timeouts; avoid secret leaks in logs; profile before optimizing; reproduce an eval.

## References
- [Python tutorial](https://docs.python.org/3/tutorial/)
- [Typing](https://docs.python.org/3/library/typing.html)
- [asyncio](https://docs.python.org/3/library/asyncio.html)
- [Packaging Python Projects](https://packaging.python.org/en/latest/tutorials/packaging-projects/)
- [pytest](https://docs.pytest.org/en/stable/)
- [FastAPI](https://fastapi.tiangolo.com/tutorial/)
- [PostgreSQL](https://www.postgresql.org/docs/current/)

## Exit evidence
A fresh environment runs the app/tests, failures are tested, concurrency has a bounded model, and the implementation choices can be explained with concrete examples.
