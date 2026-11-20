# Browser Use — source-native S3* independent acceptance construction contract

**Canonical storage:** `opensiro-contributions/browser-use@opensiro/meta:.opensiro/issues/browser-run-independent-audit-20261118/constructor-sufficiency.md`.
**Level 1 / Human decision Issue:** [issue.md](issue.md).
**Canonical decision receipt:** [roadmap.md](roadmap.md) — only owner of historical VSM states, P0/P1/P2 and research decision.
**Stage:** PLAN_ONLY; proposed C path only. **DRAFT — NOT PUBLISHED**. Native implementation and tests NOT_RUN.

## 1. Function-specific construction boundary and methodology checks

**Source and mode boundary:** `browser-use/browser-use@ccbdb8095fbaf903c748880a600054a34c7b6191`, Python library `Agent.run` / `AgentHistoryList`, `judge_run`, local/allowed Cloud-backed browser, CLI/MCP alternatives; private Cloud orchestration, browser-harness, external fleets, original maintainer governance and CI review excluded. Frozen accepted Index/procedure in [roadmap.md](roadmap.md).

**Target transition:** S3*=— -> S3*=C

**Six-function dependencies (S1/S2/S3/S3*/S4/S5):** S1's actual browser effects and `AgentHistoryList` supply auditable evidence; S2/S3 are not silently created by one-run concurrency/timeout handling; S3* must own an independent assessment with operational return; S4 is not a task-level judge; S5 reviewer appointment and ultimate policy remain with the external parent. Historical values belong to [roadmap.md](roadmap.md), not a duplicate table.

**Function witness:** Disturbance is a superficially successful browser run with missing or contradictory evidence. Parent authorizes an independent reviewer to choose ACCEPT/HOLD/REQUEST_REWORK. The proposed verified-output API enforces that choice for its participating consumer and returns an attributable evidence/disposition receipt to the integration or next task. It cannot undo already executed browser effects.

**Counterfactual owner test:** With the independent reviewer removed but all evidence transport kept, no legitimate ACCEPT can be produced. Existing agent-model `Judgement.success` is diagnostic and does not substitute for the reviewer; an opt-in verified consumer must HOLD.

**Possible methodological negative control:** A separate parent-side service doing the same check and withholding is a valid complete alternative, potentially proving no first-party C addition necessary. Not reading Cloud governance as OSS S5.

**Contributor / maintainer priorities:** Precise adoption intent for this architecture: NOT_STATED; original open PRs show native engineering alternatives but are not endorsements.

## 2. Source-pinned baseline and parallel native Track A / on-top Track B

**Original native workflow:** `Agent.run` in [service.py](https://github.com/browser-use/browser-use/blob/ccbdb8095fbaf903c748880a600054a34c7b6191/browser_use/agent/service.py) executes Pydantic-AI + REPL browser work and returns `AgentHistoryList` in [views.py](https://github.com/browser-use/browser-use/blob/ccbdb8095fbaf903c748880a600054a34c7b6191/browser_use/agent/views.py). `_run` captures final page before browser shutdown; `_judge` executes in shutdown `finally`, uses same agent model, and failure leaves `judgement=None` without veto. [judge.py](https://github.com/browser-use/browser-use/blob/ccbdb8095fbaf903c748880a600054a34c7b6191/browser_use/agent/judge.py) truncates/redacts trace and selects bounded screenshots.

**Closest existing solution:** Application checks `status/success/judgement` and independently calls a reviewer; only application publishes results after acceptance. This is a legitimate NO-C fallback and comparison.

**Relevant original Issues/PRs:** [#6414 action hooks](https://github.com/browser-use/browser-use/pull/6414) OPEN_PR `252c16a3fd35375e8642158127120f021085a884`; [#6415 hash log](https://github.com/browser-use/browser-use/pull/6415) OPEN_PR `728a671cdc4025ec55a9b1ea9af9d2390a4bd32e`; [#6446 alternative audit/guards](https://github.com/browser-use/browser-use/pull/6446) OPEN_PR `b8e2182a2740fc8aebeece4752fe8ab9232eccd5`; [#6416 effect approval](https://github.com/browser-use/browser-use/pull/6416) OPEN_PR `40a04f0120913ae65c1d6da2bdcd4dcc5a6941c7`; [#6423 pre-action critic](https://github.com/browser-use/browser-use/pull/6423) OPEN_PR `3b1852c1d0544e466b674fe034988d009b8966bc`; [#6452 library judgement reporting](https://github.com/browser-use/browser-use/pull/6452) OPEN_PR `3a83940550111d9cf40dc5dce1cdde84d2565239`; [#6457 same-model cache judge](https://github.com/browser-use/browser-use/pull/6457) OPEN_PR `de933f7f780a19ecc44bf26a9fbe346b4af07fe0`; [#6031 false-success tests](https://github.com/browser-use/browser-use/issues/6031) ISSUE_ONLY. These observed heads have not been merged into the pinned `main` source. Do not claim implemented C or maintainer consent.

| Required C link / outcome | Track A current coverage | Track B smallest original-native addition | Falsifier |
| --- | --- | --- | --- |
| Evidence from finished run | `AgentHistoryList.messages`, `steps`, `status`, optional bounded `judge_run` inputs | Freeze a redacted, run-bound evidence snapshot before browser shutdown for the opt-in path | Current result offers equally reliable evidence without native capture |
| Independent decision right | Same-model `Judgement`, no release veto | Parent-appointed separate reviewer bound to one run/evidence, choosing ACCEPT/HOLD/REQUEST_REWORK | Reviewer can be absent and gate still ACCEPTs |
| Observable release and return | `Agent.run` unconditionally returns regular result on judge failure | `VerifiedRunResult`-like return requiring accepted decision for verified payload; HOLD/REQUEST_REWORK returns receipt | Consumer gets verified output despite HOLD or feedback never reaches requester |

**On-top distinctness:** Unlike action hooks, pre-effect approvals, audit telemetry and same-producer judgement, this integrates independent post-run acceptance into a supported *verified-delivery* call. The original unverified `run` remains available by design; the specified C boundary is strictly opt-in consumers.

**Source ambiguity / rights blockers:** Need current accepted PR heads at implementation time; unverified external CLA/AI rules prohibit assuming a publishable PR. Missing measured user demand is research NEEDS_EVIDENCE, not an architecture veto. Original is MIT; parent must designate independent reviewer and downstream release authority.

## 3. Minimal complete S3* first-party C construction

**Required property:** A function-specific first-party construction path permitting an integrator to compose independent, legitimate evidence-based S3* decisions that alter later verified output and return feedback; not merely another hook or audit event.

| Necessary native component / port | Existing source | Proposed smallest edit / integration | Owner, effect, return |
| --- | --- | --- | --- |
| Frozen evidence for one `Agent.run` | `Agent._run` final screenshot is captured before shutdown; `judge_run` currently reads bounded redacted `result.messages` | For opt-in verified run, store non-producer-evidenced redacted snapshot and run ID before shutdown; reject absent/truncated material according to parent policy | Agent supplies evidence; reviewer decides fitness |
| Verified-result API seam | `AgentHistoryList.final_result()`, `structured_output()`, `judgement` in `views.py` | Optional `run_verified(reviewer=...)`-style interface or equivalent typed wrapper that cannot label release verified without independent ACCEPT | Parent appoints reviewer; accepted output visible to verified consumer only |
| Review and feedback | Normal `_judge` failure is non-blocking, [tests/ci/test_judge.py](https://github.com/browser-use/browser-use/blob/ccbdb8095fbaf903c748880a600054a34c7b6191/tests/ci/test_judge.py) tests it | Separate verdict and receipt with HOLD/REQUEST_REWORK, recorded for consumer/operator and next-run handoff; no autonomous rollback | Reviewer verdict has enforceable verified-output effect and returned attributable reason |

**Native-specific design advice:** Respect Browser Use 1.0's `Agent.run` / `AgentHistoryList` migration, persistent Python REPL, `judge` default, `use_vision` dependence, bounded screenshots and the fact that `_judge` occurs during shutdown. Do not build a general scheduler or generic supervisor to implement one opt-in accepted result.

**Architectural C-sufficiency argument:** Option A is no source change: caller checks `result.judgement` and runs a separate checker; this can fully close a parent-governed task but may require repeated fragile glue. Option B is a first-party thin `run_verified` boundary that freezes evidence in the existing `_run` lifecycle, binds an independently supplied reviewer and gates a typed verified payload while returning a HOLD/REQUEST_REWORK receipt. Option C is an extension atop #6414/#6415 action/evidence hooks if merged, but those hooks alone lack independent release decision ownership. B is a coherent conditional C constructor; a measured equivalence of A to B would make no native addition preferable. None is currently implemented.

**Explicit non-goals:** No mandatory review of all runs; no pre-action security decision, no third-party compliance certification, no browser-effect rollback, no S4/5 governance or fleet control, no assumption that a log hash proves a truthful screenshot.

**Implementation dependency graph:** P1 pin newer native hooks/PRs, define reviewer authority and evidence sensitivity; then P0 add optional evidence/independent-review/verified-output closure; then validate a matching consumer contract, missing-owner and side-effect boundaries before any real proposal.

## 4. Priorities, optional alternative and stopping rules

**P0 and P1:** P0 is strictly opt-in S3* verified result release; P1 is current-native overlap, evidence capture timing, parent consent, run identity and falsification of the cheapest wrapper. Read [roadmap.md](roadmap.md) for canonical priorities.

**P2:** NONE. Other VSM functions are not pulled into this case.

**Alternative path:** Keep unchanged `Agent.run`, use `judge=True` and a caller-controlled external reviewer that withholds acceptance. Prefer this if same outcome and less glue/cost.

**Stop:** The candidate fails if equivalent first-party C is already shipped, no independent legal reviewer can own the choice, the return cannot be enforced, or original boundary is unsupported. Maintainer product taste and lack of cost metrics alone do not disprove architectural constructibility; publication still has a separate exact consent gate.

## 5. Future source-native acceptance — derive tests, do not copy a matrix

**Native test commands and entry points:** Existing `tests/ci/test_judge.py` exercises own-model judgement and `None` failure. Future targeted pytest cases would be added under `tests/ci/` following the actual repo test patterns; **NOT_RUN** for this research-only update.

**Positive functional closure:** In a deterministic mocked Browser Use run, an independently supplied reviewer sees bounded evidence and chooses ACCEPT; a participating `run_verified` consumer receives verified output and a reviewer/run/evidence receipt. A subsequent run/operator reads the disposition.

**Independent alternative (where applicable):** On the same operative run, a reviewer chooses HOLD (or REQUEST_REWORK) and the verified payload is withheld; this must differ from the producer judge's `success=True` claim.

**Negative authority and compatibility (where applicable):** Missing/revoked reviewer, stale evidence, malformed verdict and reviewer timeout must fail closed for the opt-in verified output; ordinary `Agent.run` retains its existing result and nonfatal judge behavior. Browser side effects are not undone.

**Matched native alternative:** Replay identical mocked runs with current caller-side `result.judgement` + independent checker vs native proposed result path; compare true accept/hold outcomes, evidence integrity, integration complexity and support burden. Cost remains unmeasured.

| Proposed case (NOT_RUN) | Source-native setup | Expected later effect / return | Falsifier |
| --- | --- | --- | --- |
| Accept | `tests/ci/test_judge.py` patterns + external deterministic reviewer | Verified output and reviewer receipt | Producer-only verdict accepted |
| Hold | Mocked run returns `success=True`, separate reviewer rejects evidence | Verified payload withheld, feedback available | Consumer still receives verified output |
| Missing reviewer / failed judge | `judgement=None` or reviewer fails | Opt-in verified call HOLDs, normal `run` compatible | Silent verified-release |
| Existing wrapper comparator | Same run/history and parent policy | Same decisions measured with external guard | Native API is strictly duplicative and costlier |

## 6. Proposal verdict, falsification, evidence ownership and handoff

**Proposal-stage decision:** GO
**Research disposition:** NEEDS_EVIDENCE

**Primary falsifier:** Existing caller-side check plus independent review gives identical accepted/held outcomes with better evidence/cost, or proposed owner/return proves ineffective.
**Validation state:** NOT_RUN.
**Ownership of truth:** Profile owns S3* semantics, Skills method, Index historical classification, original maintainers product adoption, parent integrator reviewer and approval authority; [roadmap.md](roadmap.md) owns this research decision. No new grade is asserted.
**Cost status:** NOT_MEASURED.
**Next permitted action:** Run bounded comparator and authority tests only under separate implementation authorization; keep current case on verified `opensiro/meta`, report internally to #58, do not open third-party Issues or PRs.
**Human backlink:** [issue.md](issue.md).
**case receipt:** [roadmap.md](roadmap.md).
**AI disclosure:** Prepared with AI assistance, not independently tested or approved. No third-party external or fork-public publication is authorized.
