# Learning Resources and Assignment Map

Use this catalog with the [26-week roadmap](ROADMAP.md) and [topic tracks](tracks/README.md). It is not a requirement to complete every course. Read the assigned concept, reproduce one example, change a variable, explain the result, then implement independently. Prefer official documentation for API and standards facts.

Links are resource candidates reviewed 2026-10-16; recheck version-sensitive pages when implementing.

## Weekly core assignments

| Week | Primary source | Apply it to |
|---:|---|---|
| 1 | [Python tutorial](https://docs.python.org/3/tutorial/) and [pytest start](https://docs.pytest.org/en/stable/getting-started.html) | Baseline CLI and tests |
| 2 | [Python Packaging User Guide](https://packaging.python.org/en/latest/) and pytest guides | Reproducible project and validation |
| 3 | [FastAPI tutorial](https://fastapi.tiangolo.com/tutorial/) | API contract and HTTP failures |
| 4 | [PostgreSQL tutorial](https://www.postgresql.org/docs/current/tutorial.html) | Modeling, transactions, migration and CI |
| 5 | Selected model provider's official API docs; [Python logging](https://docs.python.org/3/library/logging.html) | Provider adapter and failure behavior |
| 6 | Provider structured-output docs; [Hugging Face NLP course](https://huggingface.co/learn/nlp-course/) | Task/context/output contract |
| 7 | [Evaluation best practices](https://developers.openai.com/api/docs/guides/evaluation-best-practices) and [pytest parametrization](https://docs.pytest.org/en/stable/how-to/parametrize.html) | Portable eval harness |
| 8 | 8–12 current target-role descriptions and candidate data-source licenses | Product boundary and role gap map |
| 9 | Public corpus documentation; [pathlib](https://docs.python.org/3/library/pathlib.html) | Provenance and ingestion |
| 10 | [PostgreSQL full-text search](https://www.postgresql.org/docs/current/textsearch.html) | Lexical baseline |
| 11 | [Sentence Transformers](https://sbert.net/) and [pgvector](https://github.com/pgvector/pgvector) | Embedding retrieval comparison |
| 12 | Evaluation principles and chosen provider's grounding/citation guidance | RAG, citation accuracy and abstention |
| 13 | FastAPI error/testing docs and Python async timeout docs | Failure-path tests |
| 14 | [OpenTelemetry](https://opentelemetry.io/docs/) and provider usage/pricing docs | Traces, latency and cost |
| 15 | [OWASP Top 10 for LLM Applications](https://genai.owasp.org/resource/owasp-top-10-for-llm-applications-2025/) | Threat model and injection cases |
| 16 | OWASP guidance plus selected host's security docs | Beta review and risk remediation |
| 17 | [LangGraph workflows/agents](https://docs.langchain.com/oss/python/langgraph/workflows-agents) as a reference | Deterministic workflow versus agent |
| 18 | [MCP introduction](https://modelcontextprotocol.io/docs/getting-started/intro) and linked official SDK docs | Read-only tool protocol |
| 19 | [LangSmith evaluation guide](https://docs.langchain.com/langsmith/evaluation) plus local cases | Tool-choice and failure eval |
| 20 | [Kafka documentation](https://kafka.apache.org/documentation/) | Optional async ingestion semantics |
| 21 | [Flink architecture](https://flink.apache.org/what-is-flink/flink-architecture/) and Kafka docs | State/replay/capacity decision |
| 22 | [GitHub Actions Python guide](https://docs.github.com/en/actions/tutorials/build-and-test-code/python) and [Docker getting started](https://docs.docker.com/get-started/) | CI and reproducible packaging |
| 23 | Official docs for chosen deployment host | Safe config and deploy |
| 24 | Host's logging, backup and recovery docs | Operations runbook |
| 25 | Project tests plus [React accessibility/learn docs](https://react.dev/learn) if UI is present | Integration hardening |
| 26 | Current job descriptions and assessment rubric | Final evidence and next plan |

## Topic-track reference shelf

### Java/JVM/Spring
- [Dev.java](https://dev.java/learn/)
- [Java Language Specification](https://docs.oracle.com/javase/specs/)
- [Java concurrency tutorial](https://docs.oracle.com/javase/tutorial/essential/concurrency/)
- [Java 21 virtual threads](https://docs.oracle.com/en/java/javase/21/core/virtual-threads.html)
- [Spring Boot](https://docs.spring.io/spring-boot/index.html)
- [Spring guides](https://spring.io/guides)
- [Project Reactor](https://projectreactor.io/docs/core/release/reference/)

### Python
- [Python tutorial](https://docs.python.org/3/tutorial/)
- [Typing](https://docs.python.org/3/library/typing.html)
- [asyncio](https://docs.python.org/3/library/asyncio.html)
- [Packaging](https://packaging.python.org/en/latest/tutorials/packaging-projects/)
- [pytest](https://docs.pytest.org/en/stable/)
- [FastAPI](https://fastapi.tiangolo.com/tutorial/)

### Frontend
- [React Learn](https://react.dev/learn)
- [TypeScript Handbook](https://www.typescriptlang.org/docs/handbook/intro.html)
- [MDN](https://developer.mozilla.org/)
- [Testing Library](https://testing-library.com/docs/)

### Data/distributed
- [PostgreSQL](https://www.postgresql.org/docs/current/)
- [pgvector](https://github.com/pgvector/pgvector)
- [OpenSearch](https://docs.opensearch.org/latest/)
- [Redis](https://redis.io/docs/latest/)
- [Kafka](https://kafka.apache.org/documentation/)
- [Flink](https://flink.apache.org/what-is-flink/flink-architecture/)

### AI, agentic systems, security and operations
- [Hugging Face NLP course](https://huggingface.co/learn/nlp-course/)
- [Sentence Transformers](https://sbert.net/)
- [MCP](https://modelcontextprotocol.io/docs/getting-started/intro)
- [LangGraph workflows and agents](https://docs.langchain.com/oss/python/langgraph/workflows-agents)
- [OWASP LLM Application risks](https://genai.owasp.org/resource/owasp-top-10-for-llm-applications-2025/)
- [OpenTelemetry](https://opentelemetry.io/docs/)

### System design and algorithms
- [Interview With Bunny — System Design](https://www.interviewwithbunny.com/systemdesign)
- [The Design Round — problems](https://thedesignround.com/system-design/problems/01-url-shortener)
- [Princeton Algorithms](https://algs4.cs.princeton.edu/home/)
- [LeetCode](https://leetcode.com/) for timed practice after learning the concept.

## Career-market review

At Weeks 8, 16, 21 and 26, collect 8–12 current descriptions for the intended role/geography. Record title, date, seniority, core responsibilities, required vs preferred skills, and evidence already available. Count repeated skills; don't treat one posting as a universal requirement.

## Resource maintenance

Quarterly, mark links current/moved/replace. Preserve concept notes and experiments when SDKs or hosted services change. Prefer portable local evaluation cases over dependency on a single vendor's evaluation service.
