# React and TypeScript Track

## Goal
Build a focused, accessible UI for the flagship with typed contracts and reliable handling of asynchronous API calls, including stale-response and race-condition prevention.

## Ordered roadmap

| Stage | Topics | Evidence |
|---|---|---|
| R1 — TypeScript foundations | Types vs runtime values, interfaces/type aliases, unions, narrowing, generics, unknown vs any, Promise types | Typed API client and safe response handling |
| R2 — React fundamentals | Components, props, state, render model, keys, controlled inputs and component boundaries | Search/results UI with clear data flow |
| R3 — State/effects | Hooks, dependencies, derived state, refs, cleanup and stale closures | Remove redundant state; explain effect lifecycle |
| R4 — Async correctness | Loading/error/empty states, AbortController, request IDs, race conditions and stale-response prevention | Rapidly change selected asset/query and prove older responses cannot overwrite latest data |
| R5 — Forms and API | Input validation, API error mapping, pagination and URL state | Query form with retryable errors |
| R6 — Shared state | Local state first; context/library only when shared; normalization/cache invalidation | State placement decision |
| R7 — Accessibility | Semantic HTML, keyboard flow, focus, labels, contrast, status announcements and reduced motion | Keyboard-only review |
| R8 — Product workflow | Streaming response UX, citations, passage preview, source conflicts, no-answer messaging, save/export/feedback | Research screen where claims link to evidence |
| R9 — Tests/performance | React Testing Library, user-oriented tests, network mocks, profiler and justified memoization | Loading/error/race/keyboard tests and measured performance finding |
| R10 — Delivery | Error boundaries, config, build and CI | Reproducible UI build and setup instructions |

## Suggested order
Start after the API contract exists. Complete R1–R4 first; build the actual workflow in R5–R8; harden with R9–R10. Keep the UI small until users can inspect sources and evidence.

## References
- [React Learn](https://react.dev/learn)
- [TypeScript Handbook](https://www.typescriptlang.org/docs/handbook/intro.html)
- [MDN Web Docs](https://developer.mozilla.org/)
- [Testing Library](https://testing-library.com/docs/)

## Exit evidence
The UI is keyboard-navigable, has explicit failure/loading states, prevents stale async responses, and has behavior-focused tests.
