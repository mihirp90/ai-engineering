# AI, LLM, Embeddings, Retrieval and RAG Track

## Goal
Build evidence-grounded AI features; understand when generation helps, where systems fail, and how to measure quality.

## Ordered roadmap

| Stage | Topics | Evidence |
|---|---|---|
| A1 — Model basics | Tokens, context, sampling, model capabilities, latency/cost and probabilistic behavior | Model adapter and comparison note |
| A2 — Contracts | Prompt structure, trusted instructions vs untrusted input, structured output, schema validation, refusals/timeouts | Typed provider interface and failure tests |
| A3 — Prompt/context design | Task decomposition, examples, context selection, token budget, ambiguity, abstention and versioning | Fixed dataset and controlled experiment |
| A4 — Evaluation-first | Golden cases, scoring rubric, regression, reviewer calibration, configuration/model versions and error taxonomy | Baseline report with reviewed misses |
| A5 — Document pipeline | License/provenance, parsing, normalization, chunking, hashes, duplicates and incremental ingestion | Rebuildable corpus |
| A6 — Lexical retrieval | Full-text ranking, query classes, filters, passage IDs and relevance labels | Search baseline |
| A7 — Embeddings | Model/version, vectors, similarity, dimensions, limits and semantic mismatch | Vector-vs-lexical benchmark |
| A8 — Hybrid/reranking | Rank fusion, metadata constraints, reranking, relevance and latency trade-offs | Evidence-backed retrieval choice |
| A9 — RAG assembly | Query → retrieve → filter → assemble context → generate → validate citations; token budgets | End-to-end cited answer |
| A10 — Grounding/abstention | Claim-evidence links, citation correctness, conflicting/dated sources and missing evidence | No-answer/conflict evaluations |
| A11 — Quality iteration | Separate retrieval/answer metrics; error slices; data/prompt/model change analysis | Before/after report |
| A12 — Model deployment electives | Open models, Hugging Face inference, quantization, batching, fine-tuning rationale | Only pursue when evidence warrants it |

## Dependencies
Model integration and an evaluation set precede RAG. Establish lexical search before embeddings. Compare with the same query set. Do not tune against a changing test set. Build agents only after RAG works and a task requiring model-directed action is identified.

## References
- [Hugging Face NLP course](https://huggingface.co/learn/nlp-course/)
- [Sentence Transformers](https://sbert.net/)
- [pgvector](https://github.com/pgvector/pgvector)
- [PostgreSQL full-text search](https://www.postgresql.org/docs/current/textsearch.html)
- [Evaluation best practices](https://developers.openai.com/api/docs/guides/evaluation-best-practices)

## Exit evidence
A reviewer can inspect sources, verify citations, reproduce retrieval measurements, identify no-answer behavior, and understand limitations without claims such as “hallucination-free.”
