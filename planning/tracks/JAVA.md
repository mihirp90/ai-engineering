# Java, OOP, JVM, Concurrency and Spring Track

## Goal
Develop strong JVM backend engineering judgment: object modeling, collection contracts, the memory model, threading/concurrency, Spring transaction behavior, async execution, and operational failures.

## Ordered roadmap

| Stage | Topics | Practice evidence |
|---|---|---|
| J1 — OOP and modeling | Classes/objects, encapsulation, abstraction, interfaces, composition vs inheritance, SOLID, cohesion/coupling, immutability, equals/hashCode, records/sealed types | Domain model, equality tests, explain composition choice |
| J2 — Types and collections | Generics/bounds, List/Set/Map/Queue, ArrayList vs LinkedList, HashMap hashing/collisions, TreeMap, comparators, iteration, fail-fast behavior, complexity | Build small index/cache and explain edge cases and complexity |
| J3 — Modern Java | Lambdas, functional interfaces, stream pipeline/laziness, Optional, method references, java.time, exceptions, try-with-resources and I/O | Transform data with streams and robust failure handling |
| J4 — Build and tests | Maven/Gradle concepts, JUnit 5, Mockito, parameterized/integration tests, dependency boundaries | Unit + integration tests for service/repository |
| J5 — JVM | Heap/stack/metaspace concepts, allocation, reachability, GC, class loading, JIT, heap/thread dumps, JFR/JMC, jcmd/jstack, leak vs high allocation | Diagnose a deliberate leak or contention issue |
| J6 — Threading fundamentals | Processes/threads, Thread/Runnable, executors, races, atomicity/visibility/ordering, Java Memory Model, happens-before, safe publication and thread confinement | Reproduce and fix a data race; explain why the fix works |
| J7 — Synchronization | synchronized, volatile limits, intrinsic locks, ReentrantLock/Condition, read-write locks, lock ordering, deadlock/livelock/starvation, contention, concurrent collections | Compare unsafe counter, lock, atomic and concurrent-collection solutions |
| J8 — Async execution | ExecutorService, Future, CompletableFuture, compose vs block, timeout/cancel, bounded pools/queues, rejection, backpressure, ForkJoinPool, Java 21 virtual threads, ThreadLocal implications | Concurrent I/O simulation with bounded resources and latency comparison |
| J9 — Spring core/REST | IoC/DI, bean lifecycle/scopes, profiles, auto-configuration, controllers/services/repositories, validation, error mapping, OpenAPI, Actuator | Typed REST API with integration tests |
| J10 — Persistence/transactions | JDBC/JPA boundary, N+1, transactions and proxy behavior, self-invocation, propagation/isolation, optimistic/pessimistic locks, pool sizing, idempotency | Demonstrate rollback and proxy behavior with tests |
| J11 — Resilience/observability | Timeouts, capped retries/backoff, graceful degradation, security basics, logs/metrics/traces, OpenTelemetry | Trace IDs and failure metrics in a service |
| J12 — Event-driven services | Kafka keys/partitions/groups, ordering/delivery semantics, DLQ, idempotent consumer, outbox/inbox trade-offs, Redis TTL/cache invalidation, WebClient/Reactor boundaries | Reliable consumer or architecture ADR covering replay/duplicates |
| J13 — Review/capstone | API/data consistency, profiling, race/failure tests, code review and design narrative | Reviewed service and two trade-off explanations |

## Suggested 26-week cadence
Weeks 1–4: J1–J2; weeks 5–6: J3; weeks 7–8: J4; weeks 9–10: J5; weeks 11–14: J6–J7; weeks 15–16: J8; weeks 17–18: J9; weeks 19–20: J10; weeks 21–22: J11; weeks 23–24: J12; weeks 25–26: J13. Use the three-hour weekly focus block, then extend the calendar if evidence shows a gap.

## Concurrency checklist
Explain atomicity vs visibility vs ordering; why volatile does not make compound updates atomic; happens-before and safe publication; synchronized vs Lock vs Atomic*; contention despite lock-free primitives; executor sizing, queue bounds/rejection, cancellation/timeouts; CompletableFuture composition vs accidental blocking; deadlock diagnosis with thread dumps; virtual-thread strengths/limits; and avoiding blocking calls on reactive event loops.

## References
- [Dev.java](https://dev.java/learn/)
- [Java Language Specification](https://docs.oracle.com/javase/specs/)
- [Java concurrency tutorial](https://docs.oracle.com/javase/tutorial/essential/concurrency/)
- [Java 21 virtual threads](https://docs.oracle.com/en/java/javase/21/core/virtual-threads.html)
- [JUnit 5](https://junit.org/junit5/docs/current/user-guide/)
- [Spring Boot](https://docs.spring.io/spring-boot/index.html)
- [Spring guides](https://spring.io/guides)
- [Project Reactor](https://projectreactor.io/docs/core/release/reference/)

## Exit evidence
For each completed topic, attach tests/code or a concrete explanation of correctness, failure modes, alternatives, complexity and operational trade-offs.
