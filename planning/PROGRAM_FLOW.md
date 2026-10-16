# Program Flow and Working Method

This file explains how the curriculum, topic tracks, labs, flagship product, reviews and career evidence fit together. The [26-week roadmap](ROADMAP.md) is the core product schedule; the [topic track index](tracks/README.md) contains independent section-wise roadmaps.

## Weekly 15-hour budget

| Work block | Hours/week | Purpose |
|---|---:|---|
| Core roadmap and flagship product | 10 | Concepts, build, verification and debugging |
| One selected topic track | 3 | Deepen one topic sequence; don't split time across every track |
| System design or DSA | 1 | Alternate weekly and connect practice to real engineering |
| Learning log and planning | 1 | Record evidence, misses, decisions and next task |
| **Total** | **15** | About 390 hours over 26 weeks |

## Learning loop

**Problem → baseline → primary source → small experiment → independent implementation → tests/evaluation → failure analysis → decision record.**

The end-to-end core flow is:

1. Baseline and target-role evidence.
2. Engineering foundations.
3. Model-backed task with a measured baseline.
4. Product problem and data boundary.
5. Ingestion and search.
6. RAG and citations.
7. Evaluation and error analysis.
8. Security and reliability.
9. Bounded tools/MCP only if justified.
10. Deployment, operations, portfolio and career review.

Add frameworks, vector stores, distributed infrastructure or agents only when evidence shows a need.

## Workstreams

| Workstream | Main weeks | Contribution |
|---|---|---|
| Core AI/product | 5–26 | Model adapter, evaluation, research workflow, retrieval and delivery |
| Python engineering | 1–4, then throughout | Packages, API/data work, testing and integrations |
| Java/JVM/Spring | Focus blocks in topic track | OOP, collections, concurrency, JVM, transactions, async services |
| SQL/data/search | 4, 9–12 and selected track blocks | Modeling, provenance, lexical/semantic retrieval and indexing |
| Frontend | Selected track blocks after API stability | Accessible React/TypeScript UI and reliable async behavior |
| Distributed systems | 20–21 and selected track blocks | Queues, idempotency, Kafka/Flink/Redis when justified |
| Trust/operations | 7, 13–16, 22–25 | Evaluation, traces, security, failure handling and recovery |
| Career/evidence | 4, 8, 12, 16, 21, 26 | Skill matrix, role evidence, architecture explanations and portfolio |

## Suggested cadence

Use the core 10-hour block flexibly: about 2 hours for primary reading/concepts, 2 for guided experiment, 4 for independent implementation, 1 for testing/evaluation and 1 for failure analysis/write-up. The separate 3-hour track block should produce a mini-lab, test, benchmark, diagram or explanation. Use the 1-hour reflection block to update progress. Use the remaining hour for either DSA or system design, alternating weekly.

If a week is missed, resume from the next incomplete outcome. Do not compress weeks by skipping tests or reflection. Extend the calendar before sacrificing evaluation/security quality.

## Track-selection rule

Tracks are a catalog of sequenced roadmaps, not ten simultaneous commitments. Prioritize one track at a time based on the product task and the skill matrix. Suggested first priorities: Python foundations; then Java OOP/concurrency/Spring; SQL/search; React/TypeScript; distributed systems and delivery. Reorder with evidence from current target-role postings.

## Artifact path

- Concept → concise note in `notes/concepts/`.
- Exercise → named lab.
- Reusable feature → flagship product only when it supports the agreed workflow.
- Evidence → tests, labeled cases, evaluation reports, traces and decision records.
- Reflection → `progress/LEARNING_LOG.md` and `progress/PROGRESS.md`; update the skill matrix monthly and at gates.

## Monthly review

At Weeks 4, 8, 12, 16, 21 and 26: rerun the previous gate; update the skill matrix from artifacts; review 8–12 current postings at career-check weeks; select one gap that changes the next period; revisit scope, hours, data provenance, costs and resource versions.

## Completion definition

A reproducible applied-AI product, meaningful evaluation suite, clear data provenance, architecture and threat model, observable failures, runbook, runnable demo and honest limitations. Finishing videos or certificates alone does not satisfy the outcome.
