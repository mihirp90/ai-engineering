# AI Engineering Learning Workspace

Single source of truth for a six-month applied AI Engineering program: curriculum, topic roadmaps, learning resources, labs, product work, assessments, and progress.

## Start here

1. [Program flow](planning/PROGRAM_FLOW.md) — weekly time budget and working method.
2. [26-week roadmap](planning/ROADMAP.md) — weekly build tasks and gates.
3. [Detailed curriculum](planning/CURRICULUM.md) — learning outcomes and concepts.
4. [Topic learning tracks](planning/tracks/README.md) — section-wise roadmaps by technology.
5. [Learning resources](planning/LEARNING_RESOURCES.md) — documentation and applied readings.
6. [Assessment plan](planning/ASSESSMENT_PLAN.md) — rubric and evidence requirements.
7. [Product portfolio](planning/PRODUCT_PORTFOLIO.md) — flagship hypothesis and boundaries.
8. [Progress](progress/PROGRESS.md) · [Learning log](progress/LEARNING_LOG.md) · [Skill matrix](progress/SKILL_MATRIX.md).

## Program at a glance

- **Duration:** 26 weeks, about six months.
- **Effort:** 15 focused hours/week, approximately 390 hours.
- **Main learning vehicle:** one scoped product built incrementally, plus small experiments.
- **Flagship hypothesis:** Research Intelligence using public/appropriately licensed sources; confirm its first user, task, and corpus at the Week 8 discovery gate.
- **Data rules:** never use employer/customer/private data or commit credentials.

| Month | Weeks | Focus | Expected evidence |
|---|---:|---|---|
| 1 | 1–4 | Python engineering, APIs, SQL, tests | Reproducible service foundation |
| 2 | 5–8 | Model integration, evaluation, product discovery | Measured baseline and agreed MVP boundary |
| 3 | 9–12 | Ingestion, lexical/semantic retrieval, RAG | Evidence-grounded research slice |
| 4 | 13–16 | Evaluation, observability, reliability, security | Reviewed beta and threat model |
| 5 | 17–21 | Workflows, MCP, agents, optional distributed processing | Bounded tool decision with evidence |
| 6 | 22–26 | Delivery, deployment, hardening, portfolio | Reproducible demo and final evidence |

## Weekly time allocation

| Activity | Hours/week |
|---|---:|
| Core curriculum and flagship product | 10 |
| One selected topic learning track | 3 |
| System design or DSA (alternate weekly) | 1 |
| Learning log, review, planning | 1 |
| **Total** | **15** |

The topic tracks are independent roadmaps, not ten simultaneous commitments. See [Track Index](planning/tracks/README.md) and select one focused track at a time.

## Workspace map

- `planning/` — curriculum, schedule, resources, assessment, product scope, tracks
- `progress/` — current state, learning log, skill matrix
- `notes/` — concepts, architecture, debugging
- `labs/` — isolated experiments by topic; the previous lab repository history was imported
- `projects/research-intelligence/` — proposed flagship application
- `projects/supporting-projects/` — focused supporting work

## Working rules

- Learn a concept, reproduce a small example, implement independently, test failures, and document the decision.
- Establish baselines before adding frameworks, vector stores, or agents.
- Preserve tests, evaluation results, data provenance, traces, decisions, threat model, and runbook.
- Keep the MVP small enough to finish; optional technologies must solve a real need.
- Update progress at each weekly review and gate.
- Never commit secrets, tokens, private keys, or employer/customer data.

## Current state

The plan is drafted as a 26-week / approximately 390-hour program with section-wise topic tracks. Learning execution has not started. Product scope remains a hypothesis until the Week 8 gate. See [Progress](progress/PROGRESS.md).
