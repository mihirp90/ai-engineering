# System Design and DSA Track

## Goal
Build consistent interview practice that strengthens fundamentals and connects algorithms/architecture to the flagship product. This complements product work; it does not replace implementation time.

## DSA progression

| Stage | Topics | Practice |
|---|---|---|
| D1 | Big-O time/space, arrays, strings, hash maps/sets | Explain complexity and boundary cases |
| D2 | Two pointers, sliding window, prefix sums, sorting/searching | Compare brute force and optimized approach |
| D3 | Stacks, queues, linked lists, monotonic structures | State invariants and test edge cases |
| D4 | Binary search, intervals, heaps/top-k | Explain loop invariant and complexity |
| D5 | Trees/BST, traversal, recursion/backtracking | Draw recursive state and base cases |
| D6 | Graphs, BFS/DFS, topological sort, union-find | Choose algorithm based on constraints |
| D7 | Dynamic programming, greedy, state compression | Define state and transition before coding |
| D8 | Concurrency/practical problems | Thread safety, rate limiting, LRU/cache, bounded queues |

## System-design progression

| Stage | Topics | Deliverable |
|---|---|---|
| S1 | Requirements, assumptions, scale, APIs | Concise design sheet |
| S2 | Entities, schema, indexes, partition keys, consistency | Data-model diagram |
| S3 | Cache, queue, rate limit, idempotency, retries | Flow diagram including failures |
| S4 | Service boundaries, sync/async flows, state, concurrency | Left-to-right HLD |
| S5 | Kafka partitioning, ordering, replay, stateful stream processing | Distributed flow and trade-offs |
| S6 | RAG/AI architecture: ingestion, retrieval, evaluation, policy, observability | AI platform HLD and quality gates |
| S7 | Reliability, backpressure, SLOs, degradation, recovery | Failure table and capacity plan |
| S8 | Staff-level trade-offs, phased delivery, design narrative | 10-minute walkthrough |

## Weekly routine
Use the one-hour block for DSA or system design, alternating weekly. DSA: restate constraints, brute-force baseline, implement, test edge cases, analyze complexity, explain. System design: requirements/assumptions, APIs/entities, HLD, bottlenecks/failure modes, trade-offs. Keep concise notes in `notes/concepts/` or `notes/architecture/`.

## References
- [Princeton Algorithms](https://algs4.cs.princeton.edu/home/)
- [The Design Round — System Design Problems](https://thedesignround.com/system-design/problems/01-url-shortener)
- [Interview With Bunny — System Design](https://www.interviewwithbunny.com/systemdesign)
- [LeetCode](https://leetcode.com/) for timed practice after understanding the concept.

## Exit evidence
Explain brute-force and improved algorithms, complexity and edge cases. For system design, cover requirements, assumptions/scale, APIs, entities, HLD, flows, tech rationale, failure modes and deep dives.
