# SQL, Data Modeling and Search Track

## Goal
Design correct data models and measure retrieval quality before adding sophisticated search infrastructure.

## Ordered roadmap

| Stage | Topics | Evidence |
|---|---|---|
| D1 — Relational modeling | Entities, keys, normalization, constraints, cardinality, migrations, referential integrity | Schema diagram and migration |
| D2 — SQL fluency | SELECT, joins, aggregation, CTEs, window functions, NULL semantics, dates/times and parameterized queries | Query set answering representative questions |
| D3 — Transactions | Atomicity, isolation, lost updates, locks, rollback, unique constraints and idempotent writes | Concurrent/failed-write test and consistency note |
| D4 — Index/performance | B-tree and composite indexes, selectivity, EXPLAIN/ANALYZE, plans and connection pools | Baseline plan and measured index experiment |
| D5 — Data API boundary | Repository pattern, migrations, pagination, transaction boundaries and validation | Tested API with clear persistence guarantees |
| D6 — Full-text search | Tokenization, stemming, ranking, filters, snippets and relevance judgments | Labeled lexical-search benchmark |
| D7 — Embeddings/vector search | Model/version, dimensions, distance metric, chunk IDs, filters and recall/latency | Reproducible semantic-search experiment |
| D8 — Hybrid retrieval | Lexical/vector fusion, rank fusion, reranking and latency trade-offs | Evidence-backed retrieval choice |
| D9 — Provenance/ingestion | Source URL/license, checksums, fetched/modified times, parser version, duplicates, incremental reprocessing and quarantine | Rebuildable corpus manifest |
| D10 — Search operations | Reindexing, schema changes, stale embeddings, bulk ingestion, backups and monitoring | Re-index and recovery runbook |

## Technology order
Begin with PostgreSQL and full-text search as a clear baseline. Add pgvector to compare semantic retrieval. Consider OpenSearch only if requirements/measurements justify a dedicated search engine. Don't operate several data stores just to list technologies.

## References
- [PostgreSQL tutorial](https://www.postgresql.org/docs/current/tutorial.html)
- [Full-text search](https://www.postgresql.org/docs/current/textsearch.html)
- [Indexes](https://www.postgresql.org/docs/current/indexes.html)
- [pgvector](https://github.com/pgvector/pgvector)
- [OpenSearch](https://docs.opensearch.org/latest/)

## Exit evidence
Explain data invariants, prove transaction behavior, measure retrieval on labeled queries, and justify the chosen search method against alternatives.
