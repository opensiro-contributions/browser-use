# Browser Use — independent run acceptance review (Upstream #58)

**OpenSiro internal Human issue; PLAN ONLY; no public GitHub Issue or product implementation.**

**Original:** [browser-use/browser-use@ccbdb809](https://github.com/browser-use/browser-use/commit/ccbdb8095fbaf903c748880a600054a34c7b6191) · **Accepted Index:** [included assessment](https://github.com/opensiro/vsm-harness-index/blob/c2e43bf4750841277b3e58d8ba80314121734764/assessments/br/browser-use.md) (reviewed 2026-09-15; Profile 0.2.1; Skills procedure 0.3.1; assessment blob ae39d03d98023d1da055f3b7c215cdbad4009273) · **fork:** [opensiro-contributions/browser-use](https://github.com/opensiro-contributions/browser-use).

**Target transition:** S3*=— -> S3*=C
**Proposal-stage decision:** GO
**Research disposition:** NEEDS_EVIDENCE

Canonical [roadmap.md](roadmap.md) · developer [constructor-sufficiency.md](constructor-sufficiency.md) · historical [acceptance cases](constructor-acceptance.md).

## The six-function source review

| Function and purpose | Accepted historical grade | 2026-11-19 source finding and ranked action |
| --- | --- | --- |
| **S1 · Operations** | A | Model-directed Pydantic AI loop drives a persistent Python REPL, browser and CDP; preserve shipped capability; no target |
| **S2 · Coordination** | — | No first-party multi-independent-agent coordination for the selected one-run boundary; no target, not a defect assertion |
| **S3 · Current control** | — | Run budget and loop state are not management of multiple S1 commitments; no target |
| **S3* · Independent audit** | — | Shipped post-run same-model judge is advisory and cannot hold completed result; P0 opt-in separate reviewer and authorized verified-output gate |
| **S4 · Future adaptation** | — | Search/website lessons pursue current task; no sourced prospective external adaptation loop; no target |
| **S5 · Policy and identity** | — | Secrets, domains and release rules remain operator-supplied; preserve parent authority, no target |

**These are accepted historical states, not a new Index evaluation or six quality scores.** The 2026-09-15 source pin differs from current original 2026-11-19 main; recommend an Index-owned fresh reassessment, not a blocker.

## Source-backed decision

P0 is an **opt-in independently configured S3* reviewer constructor**, not another judge prompt. Native [Agent._judge](https://github.com/browser-use/browser-use/blob/ccbdb8095fbaf903c748880a600054a34c7b6191/browser_use/agent/service.py) uses the producing model and explicitly says failed judge requests never fail an Agent.run; [result models](https://github.com/browser-use/browser-use/blob/ccbdb8095fbaf903c748880a600054a34c7b6191/browser_use/agent/views.py) expose judgement separately from self-reported success. New C chain: distinct reviewer -> redacted evidence -> accept/hold/rework -> enforced consumer release/hold -> recorded feedback. Only optional, parent-authorized decisions are allowed; browser actions already performed cannot be undone by review.

**Track A:** shipped judge and trace plus caller-side result check. Original unmerged [#6414 hooks](https://github.com/browser-use/browser-use/pull/6414), [#6415 chain log](https://github.com/browser-use/browser-use/pull/6415), [#6446 alternate audit](https://github.com/browser-use/browser-use/pull/6446), [#6423 injection guard](https://github.com/browser-use/browser-use/pull/6423) and [#6416 approvals](https://github.com/browser-use/browser-use/pull/6416) must not be copied or treated as shipped. Original [#4860 run replay](https://github.com/browser-use/browser-use/issues/4860) and [#5137 per-action evidence](https://github.com/browser-use/browser-use/issues/5137) show historical diagnostics interest, not confirmed current 1.0 S3* demand.

**Track B:** opt-in reviewer interface with a separately authorized acceptance decision, non-producer evidence captured while browser state exists, and a first-party enforceable verified-output boundary. P1 = existing PR reconciliation, independent evidence and negative tests; P2 = NONE. A simple caller wrapper that checks result.judgement or calls a second model is the primary cheaper alternative.

**GO is conditional proposal permission to investigate, not permission to implement.** Research NEEDS_EVIDENCE, validation NOT_RUN, economic impact NOT_MEASURED. **Falsifier:** a caller wrapper achieves the same accept/hold outcomes and evidence fidelity at lower total integration/maintenance cost, or the proposed reviewer cannot enforce lawful hold when missing/failing. Then NO_GO, not more architecture.

## Scope and comparison

The previous 2026-11-18 case selected a similar S3* review path with PLAN_ONLY / conditional DECISION_READY. This v0.18 independent rerun selected the target before reading it; it retains the narrow candidate, converts the proposal-stage decision to explicit GO + NEEDS_EVIDENCE, updates current PR head overlap and states a cheaper-wrapper falsifier. No changed Index vector, native tests, code change or external publication. Current fork is ACTIVE / ALLOW for internal metadata only.

**Publication:** no fork GitHub Issue/PR, no original Issue/PR/comment. External public text and destination require separate exact owner approval.
