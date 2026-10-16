# Distributed Systems, Kafka, Flink and Redis Track

## Goal
Reason about partial failure, ordering, duplicate delivery, state, latency and recovery before adding infrastructure.

## Ordered roadmap

| Stage | Topics | Evidence |
|---|---|---|
| S1 — Fundamentals | Processes, networks, partial failure, latency, timeouts, retries, idempotency, consistency and availability | Failure-mode diagram for one API flow |
| S2 — Messaging basics | Producer/consumer, durable log, partition/key, offset, consumer group, ordering scope and replay | Message-flow diagram and key choice |
| S3 — Delivery semantics | At-most/at-least-once, duplicate processing, retry/backoff, poison messages, DLQ and idempotent consumers | Duplicate/retry test with correct final state |
| S4 — Kafka design | Partition sizing, key skew, rebalancing, lag, schema evolution, retention, transactions, outbox/inbox trade-offs | Capacity assumptions, failure tests and runbook |
| S5 — Stream processing | Event vs processing time, windows, watermarks, keyed state, checkpoints, savepoints, backpressure and late events | Small Flink design or experiment |
| S6 — State/caches | Redis data types, TTL, eviction, invalidation, cache-aside, stampede, stale data and distributed-lock limits | Cache consistency decision and expiry test |
| S7 — Resilience | Bulkheads, bounded concurrency, circuit-breaker concepts, retry budgets, graceful degradation and load shedding | Failure-injection report |
| S8 — Operations | Lag, throughput, percentiles, replay/backfill, state recovery and incident response | Recovery drill and capacity estimate |
| S9 — AI workload integration | Separate low-latency deterministic paths from slower async model/LLM calls; queue work and persist status | Workload diagram and latency budget |
| S10 — Design review | Partitioning/indexing, consistency, scale assumptions, fault model and alternatives | Staff-level decision record |

## Recommended practice
Start with a local queue/worker or simulated events. Add Kafka for durability, replay, multiple consumers or throughput needs. Add Flink only for event-time/stateful processing. Use Redis for a clear cache/state need with a documented source of truth. Avoid an LLM call on every high-volume event when deterministic rules can serve the hot path.

## References
- [Kafka](https://kafka.apache.org/documentation/)
- [Flink architecture](https://flink.apache.org/what-is-flink/flink-architecture/)
- [Redis](https://redis.io/docs/latest/)
- [OpenTelemetry](https://opentelemetry.io/docs/)

## Exit evidence
Explain keying, delivery and ordering guarantees; demonstrate duplicate/retry recovery; identify source of truth; and document monitoring and recovery.
