# Browser Use — opt-in independent run acceptance (OpenSiro Roadmap)

**PLAN_ONLY · proposal-stage GO · research NEEDS_EVIDENCE · DRAFT — NOT PUBLISHED**

**One-sentence proposal:** Let a Browser Use integrator compose an independent S3* reviewer that can ACCEPT or HOLD delivery of a verified `Agent.run()` result, using the original's actual result, judge and browser-evidence lifecycle. This is an optional architectural hypothesis, not a statement that Browser Use needs or should adopt it.

**Canonical decision receipt:** [roadmap.md](roadmap.md) — sole authority for historical grades, target, P0/P1/P2, GO and research status.
**Technical companion:** [constructor-sufficiency.md](constructor-sufficiency.md) — original-native source paths, counterfactuals and proposed tests.
**Working fork:** `opensiro-contributions/browser-use` on `opensiro/meta`.
**Case:** `.opensiro/issues/browser-run-independent-audit-20261118/`.

## 1. Why Opensiro and central accepted VSM assessment

OpenSiro studies whether VSM-informed construction can make agent-system engineering more systematic. That is not demonstrated cost reduction, a current-grade certification, a product requirement or evidence of maintainer adoption.

### Central starting point — accepted Index, not the target

> **ACCEPTED HISTORICAL INDEX — not current-HEAD grades or proposed after-states**
>
> **`S1=A · S2=— · S3=— · S3*=— · S4=— · S5=—`**
>
> Accepted [Index assessment](https://github.com/opensiro/vsm-harness-index/blob/c2e43bf4750841277b3e58d8ba80314121734764/assessments/br/browser-use.md), blob `ae39d03d98023d1da055f3b7c215cdbad4009273`, `review_ref=50f205533fe10ba35b553d2a3689c77b87bd5d0a` (catalog match), reviewed 2026-09-15, Profile 0.2.1, Skills 0.3.1. Current original `main@ccbdb8095fbaf903c748880a600054a34c7b6191` is separately pinned (2026-11-20).

**Repository-wide audit:** First-party OSS Python `Agent`, persistent REPL/browser executor, `AgentHistoryList`, `judge_run`, CLI/MCP modes, public config, domain/secret controls, tests/CI, docs, contributor surfaces and related original Issues/PRs. System in focus is one supported library run and the integrator's lawful acceptance boundary; private Cloud, a separate browser-harness repository, arbitrary external fleet and external maintainers are outside this recursion.

| Function / plain-language role | Historical Index state | Current source-backed owner / closure | Candidate, uncertainty and rank |
| --- | --- | --- | --- |
| **S1 · Operations** | A | `Agent.run` drives browser/Python actions from model decisions and page feedback in [service.py](https://github.com/browser-use/browser-use/blob/ccbdb8095fbaf903c748880a600054a34c7b6191/browser_use/agent/service.py) | NO_TARGET: no additional S1 constructor required for this experiment |
| **S2 · Coordination** | — | Per-run concurrent-agent rejection is local to one `Agent`; no separate multi-S1 interference owner in selected scope | NO_TARGET: do not infer multi-agent coordination |
| **S3 · Current management** | — | `max_steps`, timeout and run lifecycle are one agent's controls, not whole-system competing commitments | NO_TARGET at this run boundary |
| **S3* · Independent review** | — | [judge.py](https://github.com/browser-use/browser-use/blob/ccbdb8095fbaf903c748880a600054a34c7b6191/browser_use/agent/judge.py) reuses producer model; [test_judge.py](https://github.com/browser-use/browser-use/blob/ccbdb8095fbaf903c748880a600054a34c7b6191/tests/ci/test_judge.py) confirms failed judgement does not block result | **P0:** optional developer-composed independent acceptance decision and returned disposition |
| **S4 · Future adaptation** | — | Current browser search/planning and judge gotchas are task-related, not an independently established prospective adaptation owner | NO_TARGET; no inferred S4 deficit |
| **S5 · Identity/policy** | — | Parent/integrator owns reviewer appointment, acceptance policy and credentials | NO_TARGET: do not invent autonomous S5 or expand rights |

**Interpretation:** These are ownership categories, not quality ranks. `A` means evidenced autonomous closure; `C` would mean a first-party construction path for a developer to compose decision ownership; `—` is bounded non-evidence, not a defect. Parent authority can be legitimate.

**Priority rationale:** Only S3* has a supported, bounded independent decision/return construction hypothesis: `AgentHistoryList` already carries run status, final output, messages and optional judgement; an opt-in evidence and verified-release seam could distinguish independent review from diagnostics. Native comparator cost and actual need remain untested.

**Deliberate exclusions / methodology challenge:** The selected OSS library is not an entire fleet; absent S2/S3/S4/S5 rows cannot be projected onto private Cloud or a parent. A reviewer not separate from the production judge, or one that cannot affect later output, is not C.

**Contributor / maintainer interests (OPTIONAL):** Specific maintainer acceptance of this exact S3* change: NOT_STATED. Existing open PRs are alternatives, not statements of final intent.

## 2. Selected construction hypothesis and operator outcome

**Target transition:** S3*=— -> S3*=C

**Function-specific disturbance:** An `Agent.run()` may report success while observed evidence is insufficient; its optional same-model judge may fail and leave `result.judgement=None` without preventing normal result delivery.

**Proposed C capability (P0):** An opt-in first-party `run_verified`-style path (name illustrative) reuses `AgentHistoryList` and frozen, redacted run evidence to let an integrator supply an independently governed reviewer with ACCEPT/HOLD/REQUEST_REWORK alternatives. Only ACCEPT exposes a verified result to the participating consumer; HOLD has an attributable feedback receipt for a subsequent run or operator. The parent grants reviewer and release rights.

**Best native operator alternative:** Leave Browser Use unchanged and inspect `result.status`, `result.success`, `result.judgement` and `result.messages` in the calling application, with a separate verifier service and application-level withholding. This may already be the lower-cost complete solution.

**Expected user benefit:** HYPOTHETICAL uniform opt-in acceptance semantics across integrations, not measured improvement or confirmed demand. It cannot undo browser actions that occurred before review.

**Architectural sufficiency argument:** `Agent.run` supplies the operative result; source-native capture before `Agent._run` browser shutdown supplies bounded evidence; an independent integrator-appointed reviewer makes a discretionary acceptance choice; a typed result view only permits verified release after ACCEPT, and gives HOLD/REQUEST_REWORK plus source-linked feedback. Absence of reviewer/evidence must fail closed within this *opt-in verified-delivery interface*. Proof of both reviewer independence and a meaningful improvement over a caller wrapper is outstanding.

## 3. Existing native work versus missing construction

**Track A — native coverage:** SHIPPED: [service.py](https://github.com/browser-use/browser-use/blob/ccbdb8095fbaf903c748880a600054a34c7b6191/browser_use/agent/service.py), [views.py](https://github.com/browser-use/browser-use/blob/ccbdb8095fbaf903c748880a600054a34c7b6191/browser_use/agent/views.py), [judge.py](https://github.com/browser-use/browser-use/blob/ccbdb8095fbaf903c748880a600054a34c7b6191/browser_use/agent/judge.py). OPEN_PR, not shipped: [#6414 hooks](https://github.com/browser-use/browser-use/pull/6414) `252c16a3`, [#6415 audit](https://github.com/browser-use/browser-use/pull/6415) `728a671c`, [#6446 file guards/audit](https://github.com/browser-use/browser-use/pull/6446) `b8e2182a`, [#6416 approvals](https://github.com/browser-use/browser-use/pull/6416) `40a04f01`, [#6423 action critic](https://github.com/browser-use/browser-use/pull/6423) `3b1852c1`, [#6452 telemetry/judge reporting](https://github.com/browser-use/browser-use/pull/6452) `3a839405`, [#6457 cached same-model judge](https://github.com/browser-use/browser-use/pull/6457) `de933f7f`. These do not independently establish S3* accept/hold closure. ISSUE_ONLY: [#6031 false-success regression](https://github.com/browser-use/browser-use/issues/6031); its existence alone is not consent or demand.

**Track B — independent on-top C construction:** A narrow opt-in verified-delivery path using original `AgentHistoryList`, `judge_run` redaction and final screenshot timing, rather than a generic new audit platform. Capture a stable evidence snapshot before shutdown; invoke a reviewer not owned by the production model; bind its decision to a result-delivery gate and return receipt.

| C-sufficiency requirement | Already present / proposed in original (A) | Smallest missing construction (B) |
| --- | --- | --- |
| Evidence bound to one browser run | `result.messages`, `status`, `steps`; [judge screenshots](https://github.com/browser-use/browser-use/blob/ccbdb8095fbaf903c748880a600054a34c7b6191/browser_use/agent/judge.py) are bounded and captured before shutdown | Explicit frozen/redacted evidence snapshot + run-id binding for opt-in review; reject absent/stale evidence |
| Independent lawful decision | Optional same-model `Judgement`; no independent release authority | Integrator-provided reviewer with ACCEPT/HOLD/REQUEST_REWORK and parent-supplied right |
| Downstream effect and feedback | `Agent.run()` returns normal `AgentHistoryList` even on judge failure | Verified-only result access under opt-in path; durable attributable verdict and next-run/operator handoff |

**Distinctness and falsifier:** An action hook, telemetry event, signed log or same-model judgement is not independent output acceptance. If a simple caller-side reviewer+guard is equivalent with less engineering, or a reviewer can be absent yet get verified release, a core S3* constructor is not justified.

## 4. Priorities and minimum sufficient result

- **P0:** Opt-in independent S3* review-and-release for one browser run, not a new autonomous control plane.
- **P1:** Freeze evidence while page exists; verify original PR heads and lawful reviewer ownership; prove negative/matched-wrapper cases and native test entry points before any implementation decision.
- **P2:** NONE; do not add S2/S3/S4/S5 features to justify this case.

**Proposed C-sufficiency verdict:** PROPOSED_C_SUFFICIENT as a source-grounded architectural hypothesis **if built**; not current C, not validated, not an Index grade change.

## 5. Proposed acceptance and stop gates

**Future positive test:** An integrator-appointed independent reviewer accepts a complete run based on captured evidence; verified consumer receives output and feedback records reviewer, evidence ID and decision.
**Future negative test:** Reviewer absent/fails, missing/stale evidence or HOLD must not yield verified output; plain `Agent.run` compatibility is unchanged. Browser side effects remain out of scope.
**Proposed falsifier:** No lawful independently owned reviewer, no enforced return path, or equivalent downstream acceptance via current caller wrapper with lower ongoing cost.
**Validation state:** NOT_RUN; current upstream native pytest suite was not executed in this roadmap-only metadata follow-up.

## 6. Independent paths

**Original-native contribution:** Prefer reuse of shipped `AgentHistoryList`/judge and any later accepted first-party PRs; propose a small library seam only if a matched wrapper does not suffice.
**Profile / Skills:** No method change proposed; any genuine function-boundary counterexample belongs in owning Profile/Skills.
**Domain fork:** A permitted application-side wrapper is an alternative experiment, not an external publication or an approved product change.

## 7. Cost hypothesis

HYPOTHETICAL: Compare the same browser runs with default `result.judgement` + caller hold, independent service-side reviewer + caller hold, and the proposed opt-in native verified-result path. Measure false accepts/holds, missing-evidence behavior, integration glue, latency and maintenance effort later. **Cost status:** NOT_MEASURED. No claim of savings.

## 8. Decision / handoff

**Proposal-stage decision:** GO
**Research disposition:** NEEDS_EVIDENCE

**Decision reason / next permitted step:** Native code permits a coherent optional independent S3* constructor, but tested closure, real operator demand, parent-appointed reviewer provenance, original PR evolution and cost superiority over caller-side withholding remain open. Keep the same case source-pinned on `opensiro/meta`; no implementation or external-publication step is inferred.

**Agent/developer handoff:** [constructor-sufficiency.md](constructor-sufficiency.md) with full source-native test design, and [canonical roadmap.md](roadmap.md) with the decision and historical comparison.

**Rights and publication:** Verified public original [MIT LICENSE](https://github.com/browser-use/browser-use/blob/ccbdb8095fbaf903c748880a600054a34c7b6191/LICENSE); original CLA/AI contributor policy not fully cleared for a future external PR. Matched `opensiro-contributions/browser-use` fork is `ACTIVE/ALLOW` for internal metadata only. No public fork Issue, original Issue/PR/comment, product code, grade change or S5 authority. Outward publication requires fresh exact approval for the destination, action and complete text/diff.

**AI disclosure:** Prepared with AI assistance. Native tests, cost benefit, and independent human approval are not presumed.
