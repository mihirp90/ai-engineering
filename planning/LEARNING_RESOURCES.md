# Learning Resources and Assignment Map

This is an applied reading list, not a requirement to finish every course. Each resource is tied to a roadmap outcome; use the listed sections first and keep a note about what you applied. Links were checked on 2026-10-16. Recheck version-sensitive documentation at the point of use.

## How to use a resource

For each item: (1) read the concept or tutorial section, (2) reproduce one example, (3) change one variable, (4) write what changed and why, (5) implement the roadmap task without copying the tutorial wholesale. Prefer official docs for APIs and standards; use other sources to deepen understanding, not as the only source for fast-changing behavior.

## Week-by-week assignments

| Week | Read/watch | Apply it to |
| --- | --- | --- |
| 1 | [Python tutorial](https://docs.python.org/3/tutorial/) sections on data structures, modules, errors; [pytest getting started](https://docs.pytest.org/en/stable/getting-started.html) | Baseline CLI and first tests |
| 2 | [Python Packaging User Guide](https://packaging.python.org/en/latest/); pytest fixtures/how-to guides | Reproducible project, validation and error-path tests |
| 3 | [FastAPI tutorial](https://fastapi.tiangolo.com/tutorial/) on path operations, request bodies, errors and testing | API contract and OpenAPI |
| 4 | [PostgreSQL tutorial](https://www.postgresql.org/docs/current/tutorial.html) plus constraints, transactions and indexes references | Data model, migration, transaction experiment |
| 5 | [OpenAI API docs](https://developers.openai.com/api/docs/) or equivalent selected provider's official docs; [Python logging](https://docs.python.org/3/library/logging.html) | Provider adapter, timeouts, error handling, cost/latency baseline |
| 6 | Provider docs for structured outputs; [Hugging Face NLP course: transformers](https://huggingface.co/docs/course/chapter1/4) for model/tokenization foundations | Task contract, output validation, prompt/context experiments |
| 7 | [OpenAI evaluation best practices](https://developers.openai.com/api/docs/guides/evaluation-best-practices) for design principles; [pytest parametrization](https://docs.pytest.org/en/stable/how-to/parametrize.html) | Local eval harness and regression cases |
| 8 | [PwC 2026 Global AI Jobs Barometer](https://www.pwc.com/gx/en/issues/artificial-intelligence/job-barometer/2026/2026-global-ai-jobs-barometer-full-report.pdf); sample current job descriptions for your target role/geography | Role skill map and product brief. Treat broad market reports as directional, not a personal forecast. |
| 9 | Selected public dataset documentation and license; [Python pathlib](https://docs.python.org/3/library/pathlib.html), [PostgreSQL JSON types](https://www.postgresql.org/docs/current/datatype-json.html) | Corpus manifest, provenance and ingestion |
| 10 | PostgreSQL [full-text search](https://www.postgresql.org/docs/current/textsearch.html) | Lexical search baseline and relevance labels |
| 11 | [Sentence Transformers documentation](https://sbert.net/) and [pgvector README](https://github.com/pgvector/pgvector) | Embedding experiment and retrieval comparison |
| 12 | Revisit evaluation best practices; inspect citations and source-grounding requirements in selected model API docs | RAG evaluation, citation correctness, abstention |
| 13 | FastAPI error handling/testing docs and Python `asyncio` timeout/task documentation as needed | Reliable failure paths and controlled retries |
| 14 | [OpenTelemetry docs](https://opentelemetry.io/docs/) and selected provider’s usage/pricing documentation | Traces, latency and cost measures |
| 15 | [OWASP Top 10 for LLM Applications](https://genai.owasp.org/resource/owasp-top-10-for-llm-applications-2025/); [OWASP Top 10 for Agentic Applications](https://genai.owasp.org/2025/12/09/owasp-genai-security-project-releases-top-10-risks-and-mitigations-for-agentic-ai-security/) | Threat model, indirect prompt-injection and tool-boundary cases |
| 16 | OWASP guidance above; selected deployment provider's security and backup docs | Product review and mitigation evidence |
| 17 | [LangGraph workflows and agents concepts](https://docs.langchain.com/oss/python/langgraph/workflows-agents) as a design reference; implement first with plain code | Workflow/agent decision; avoid framework-first implementation |
| 18 | [Model Context Protocol introduction](https://modelcontextprotocol.io/docs/getting-started/intro) and official SDK docs linked there | Read-only MCP tool boundary, lifecycle and schemas |
| 19 | [LangChain/LangGraph evaluation guidance](https://docs.langchain.com/langsmith/evaluation) as one example; maintain portable local cases | Agent tool selection and failure evaluations |
| 20 | [Apache Kafka documentation](https://kafka.apache.org/documentation/) and [Apache Flink architecture](https://flink.apache.org/what-is-flink/flink-architecture/) | Optional queue/streaming design decision |
| 21 | [GitHub Actions: build and test Python](https://docs.github.com/en/actions/tutorials/build-and-test-code/python); [Docker get started](https://docs.docker.com/get-started/) | CI and reproducible packaging |
| 22 | Official deployment, secrets, logging, backup, and cost docs for the chosen host | Runbook and deploy/recovery check |
| 23 | Revisit the sources behind architecture decisions; don't add new tools | Portfolio README, diagram, demo and limitations |
| 24 | Fresh target-role postings, the monthly skill matrix, and the full assessment rubric | Evidence-based next-quarter plan |

## Core reference shelf

### Python and software engineering

- [Python tutorial](https://docs.python.org/3/tutorial/)
- [Packaging Python Projects](https://packaging.python.org/en/latest/tutorials/packaging-projects/)
- [pytest documentation](https://docs.pytest.org/en/stable/)
- [FastAPI tutorial](https://fastapi.tiangolo.com/tutorial/)
- [PostgreSQL documentation](https://www.postgresql.org/docs/current/)
- [GitHub Actions Python guide](https://docs.github.com/en/actions/tutorials/build-and-test-code/python)

### Models, retrieval, evaluation

- [OpenAI API documentation](https://developers.openai.com/api/docs/) — one provider reference, not a requirement to couple the whole application to it.
- [Hugging Face NLP course](https://huggingface.co/learn/nlp-course/) — transformer, tokenizer, dataset and model fundamentals; free and useful for conceptual depth.
- [Sentence Transformers](https://sbert.net/) — embedding and reranking concepts.
- [pgvector](https://github.com/pgvector/pgvector) — vector similarity inside PostgreSQL.
- [Evaluation best practices](https://developers.openai.com/api/docs/guides/evaluation-best-practices) — principles for task-specific datasets, logging, automation and human calibration. The page currently says the hosted Evals platform is scheduled to become read-only on 2026-10-31 and shut down on 2026-11-30. Learn portable evaluation principles and verify status before depending on that hosted platform.

### Agents, protocols, and security

- [Model Context Protocol introduction](https://modelcontextprotocol.io/docs/getting-started/intro) — protocol concepts and getting started.
- [LangGraph workflows and agents](https://docs.langchain.com/oss/python/langgraph/workflows-agents) — useful for comparing deterministic workflows and agent patterns; learn underlying control flow first.
- [OWASP Top 10 for LLM Applications](https://genai.owasp.org/resource/owasp-top-10-for-llm-applications-2025/)
- [OWASP Top 10 for Agentic Applications](https://genai.owasp.org/2025/12/09/owasp-genai-security-project-releases-top-10-risks-and-mitigations-for-agentic-ai-security/)
- [OpenTelemetry documentation](https://opentelemetry.io/docs/) — telemetry concepts and instrumentation.

### Distributed systems and role-dependent extensions

- [Apache Kafka documentation](https://kafka.apache.org/documentation/)
- [Apache Flink architecture](https://flink.apache.org/what-is-flink/flink-architecture/)
- [Spring Boot documentation](https://docs.spring.io/spring-boot/index.html)
- [Spring AI documentation](https://docs.spring.io/spring-ai/reference/)
- [React documentation](https://react.dev/learn)
- [TypeScript handbook](https://www.typescriptlang.org/docs/handbook/intro.html)

## Career-market review method

At Weeks 8, 16, 20, and 24, collect 8–12 job descriptions from the intended geography and role family. For each, record title, date, seniority, core responsibilities, required vs preferred skills, and evidence you already have. Count repeated skills across the sample and map them to a project artifact. Re-run the sample monthly because job titles and stacks shift. The [PwC Global AI Jobs Barometer](https://www.pwc.com/gx/en/issues/artificial-intelligence/job-barometer/2026/2026-global-ai-jobs-barometer-full-report.pdf) gives broad context; the [Cisco AI Workforce Consortium analysis](https://www.cisco.com/site/m/ai-workforce-consortium/agent-cybersecurity-impact.html) is specifically about cybersecurity and should not be generalized to every AI engineering role.

## Resource maintenance

Each quarter, check links and mark resources `current`, `moved`, or `replace`. For fast-changing model APIs, use current official docs when implementing. Preserve the concept and experiment record if an endpoint, SDK, or product feature changes.
