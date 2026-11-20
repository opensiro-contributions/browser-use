# Capability Roadmap Receipt — Browser Use independent run acceptance (v0.18 rerun)

## Identity and pins
- Receipt contract: proposal-gate
- Original repository: browser-use/browser-use
- Original HEAD: ccbdb8095fbaf903c748880a600054a34c7b6191
- Observed at: 2026-11-19
- Accepted Index assessment: https://github.com/opensiro/vsm-harness-index/blob/c2e43bf4750841277b3e58d8ba80314121734764/assessments/br/browser-use.md
- Accepted assessment blob SHA: ae39d03d98023d1da055f3b7c215cdbad4009273
- Accepted review ref: 50f205533fe10ba35b553d2a3689c77b87bd5d0a
- Accepted reviewed at: 2026-09-15
- Accepted VSM vector: S1=A · S2=— · S3=— · S3*=— · S4=— · S5=—
- System in focus: shipped OSS browser-use Agent.run and optional independently authorized release of one run result, excluding private Cloud, browser-harness and fleet schedulers
- Repository-wide source map: https://github.com/browser-use/browser-use/tree/ccbdb8095fbaf903c748880a600054a34c7b6191/browser_use (agent service, loop, judge, browser/CDP, REPL, CLI, skills, MCP, tests/ci, examples, config and first-party dependencies)
- Profile version: 0.2.1
- Assessment procedure version: 0.3.1
- Historical review age: 65 days; recommend Index-owned source-pinned re-assessment, not an admission block

## Rights and authority
- Matched fork: https://github.com/opensiro-contributions/browser-use (verified fork=true, parent browser-use/browser-use, opensiro/meta branch)
- Fork owner control: ACTIVE / ALLOW at https://github.com/opensiro-contributions/browser-use/blob/opensiro/meta/.opensiro/state.json, prior to this metadata write; a later explicit STOP supersedes this record
- License and contribution policy: MIT (original LICENSE and pyproject.toml); https://github.com/browser-use/browser-use/blob/ccbdb8095fbaf903c748880a600054a34c7b6191/.github/CONTRIBUTING.md points to external contributor guide; CLA/AI rules for any external PR not fully cleared
- Product implementation authority: NOT GRANTED by this roadmap
- External communications: exact approval not given; no original or public fork Issue/PR/comment published
- Parent responsibility: user/operator controls domain, model, secrets, downstream acceptance and verification authority; do not infer S5

## Existing work / overlap
- Shipped current behavior: https://github.com/browser-use/browser-use/blob/ccbdb8095fbaf903c748880a600054a34c7b6191/browser_use/agent/service.py uses one Agent.run, a Pydantic AI agent and REPL; _judge sends the same agent model one low-effort request and explicitly never fails the run when the judge fails; result.judgement is diagnostic. https://github.com/browser-use/browser-use/blob/ccbdb8095fbaf903c748880a600054a34c7b6191/browser_use/agent/judge.py uses redacted bounded trace and latest screenshots; https://github.com/browser-use/browser-use/blob/ccbdb8095fbaf903c748880a600054a34c7b6191/browser_use/agent/views.py distinguishes self-reported success, completed status and optional judgement.
- Native developer alternative: caller checks result.judgement, verifies required fields and holds consumer-side output; or runs a separate model/checker in its own service. This is the zero-product-change comparator, not automatically inadequate.
- Unmerged overlap at observed time: https://github.com/browser-use/browser-use/pull/6414 (OPEN, head 252c16a3fd35375e8642158127120f021085a884, action hooks); https://github.com/browser-use/browser-use/pull/6415 (OPEN, head 728a671cdc4025ec55a9b1ea9af9d2390a4bd32e, hash-chained log); https://github.com/browser-use/browser-use/pull/6446 (OPEN, head b8e2182a2740fc8aebeece4752fe8ab9232eccd5, alternate audit and file guards); https://github.com/browser-use/browser-use/pull/6423 (OPEN, head 3b1852c1d0544e466b674fe034988d009b8966bc, pre-execution injection critic); https://github.com/browser-use/browser-use/pull/6416 (OPEN, head 40a04f0120913ae65c1d6da2bdcd4dcc5a6941c7, effect approvals). These are ORIGINAL proposed work, not shipped on pinned main; do not reproduce their logging/approval/critic mechanisms.
- Demand/context: https://github.com/browser-use/browser-use/issues/4860 requests reproducible run audits; https://github.com/browser-use/browser-use/issues/5137 requests action evidence. Both discuss older APIs and cannot be counted as direct current-1.0 demand for an independent verifier. No maintainer endorsement of this exact S3* idea observed: NOT_STATED.
- Different function: action refusal, domain safeguards and pre-action security critics are safety/parent controls, not automatically independent after-run acceptance S3*. Run trace and hash chain alone are observability, not a decision.

## Function ownership
- S1 disposition: Accepted A; on current code a single model-operated browser loop executes Python cells through a persistent worker and gets direct page feedback. No further S1 C construction needed.
- S2 disposition: Accepted —; current first-party shipped Agent.run lacks a distinct multi-independent-S1 disturbance-regulation topology. Cloud control and browser-harness are outside the selected system; no justified S2 C target for this run-scoped proposal.
- S3 disposition: Accepted —; timeout, max steps, REPL session and judge manage a run, not whole-system multi-S1 resources or competing commitments. No justified independent S3 manager.
- S3* disposition: Accepted —; current same-producer-model post-run judge inspects history but cannot withhold completed result and no separately authorized reviewer owns acceptance. Potential opt-in independent reviewer C path exists, conditioned on proof of a native advantage over caller wrapper.
- S4 disposition: Accepted —; browsing and search pursue the immediate task; lessons/gotchas are internal post-run learning, not a sourced external prospective intelligence-to-adaptation loop. No justified S4 proposal.
- S5 disposition: Accepted —; domain, secrets, policy and verifier authority are operator/developer supplied. No evidence of autonomous ultimate policy identity; parent ownership is a valid boundary.
- Accepted grades are historical at 2026-09-15, not a 2026-11-19 regrade; no demand is inferred solely from an empty cell.

## Capability priority
- Priority rationale: P0 independent S3* audit-release is the only bounded candidate with a concrete native decision/effect delta. Existing same-model judge preserves valuable diagnostics but is not a distinct acceptance owner; open audit/guard PRs remain separate. This remains proposal-stage rather than demonstrated business need.
- Target transition: S3*=— -> S3*=C
- P0: smallest opt-in, first-party developer-constructible review-and-release contract covering one Agent.run output
- P1 dependencies: decide actual original PR #6414/#6415/#6446 status and reuse accepted trace/audit facilities; provenance, reviewer authority, negatives, user need and native cost measurements
- P2 optional: NONE; no qualified S2/S3/S4/S5 extra feature
- Proposed C construction: independent developer-provided reviewer identity/policy and evidence snapshot from browser+run (not producer self-claim), explicit ACCEPT/HOLD/REQUEST_REWORK alternative, parent-delegated release right, fail-closed enforcement before verified result reaches a consumer, durable feedback/receipt; extension must not re-implement unmerged native logging or claim to undo browser actions
- C sufficiency falsifier: if a missing/untrusted reviewer or missing evidence can still cause verified release, if reviewer lacks an independent lawful decision or feedback path, or if a caller-side result.judgement check with an external reviewer provides the same accepted outcomes at lower total cost, no incremental C is justified

## Implementation options
- Cheapest unchanged route: use current Agent.run(judge=True), inspect result.judgement and the output in caller, optionally independently verify outside the library; default until side-by-side demonstrates a native gap
- Track A original implementation: ship existing Pydantic loop, trace/judge/results; evaluate pending #6414/#6415/#6446 interfaces as they actually merge or reject, no assumptions; current code has no built-in authority-checked verified-output release
- Track B minimum on-top: opt-in VerifiedRun adapter around existing results with independently supplied auditor and explicit release/hold; acquire immutable redacted evidence and last browser state while live, separate decision actor and actual downstream gate, durable receipt to later operator/agent; no platform/fleet scheduler and no duplicate action-hook implementation
- Track B minimality boundary: if external wrapper already supplies equivalent evidence and release control, use wrapper, do not add a core API. Distinguish trace-hash presence from truthfulness of browser state; no full security or exfiltration protection claim.

## Parallel contribution-on-top review
- Evaluation object: whether a separate developer-composed complementary run auditor can authorize delivery of a verified result after Agent.run, not prevention of arbitrary page-side effects
- Existing-work overlap: native same-model post-run judge, app-side result checks and pending action-hook, logging, injection-guard and approval PRs
- Our on-top contribution: optional independently owned evidence-review-disposition-release chain, reusing actual shipped and later accepted first-party primitives
- Incremental benefit: potentially uniform fail-closed acceptance semantics and evidence-bound reviewer/consumer feedback across integrations, instead of repeated fragile wrappers; unmeasured and falsifiable
- Decision scope: proposal-stage architecture GO only; no shipped C, accepted Index grade, user benefit, product code, fork public Issue or original PR

## Specification and domain alternatives
- The VSM S3* mapping remains Profile/Skills-owned, unchanged by this proposal. A separate optional adapter outside core or domain-specific experimental fork is a valid competitor.
- Parent/domain boundaries and source license govern deployment; do not convert review policy into a fictitious autonomous S5.
- A source-pinned Index re-assessment should be recommended because the accepted review predates the 1.0 source, but is not a mandatory admission barrier.

## Cost experiment
- Scenario basis: HYPOTHETICAL
- Proposed validation: run matched deterministic real-Chrome tasks including a false-positive success and missing/truncated evidence; compare default judge + caller guard, independent service-side auditor, and proposed native verified-run under same allowed task, browsers and model budget. Test accept/hold/rework; withheld consumer output on hold; reviewer crash, stale/refused authority, secret redaction, side effects and replay; report false-accept/false-hold rate, latency, token/cost, lines of glue and maintenance burden
- Validation state: NOT_RUN
- Proposal falsifier: independent reviewer cannot demonstrably alter a lawful acceptance decision based on non-producer evidence, or no cost/effect advantage over minimal wrapper; downgrade to NO_GO rather than expand scope
- Cost status: NOT_MEASURED

## Delivery and publication
- Result: NEEDS_EVIDENCE
- Proposal-stage decision: GO
- Research disposition: NEEDS_EVIDENCE
- External issue: DRAFT — NOT PUBLISHED
- Fork public issue: NOT PUBLISHED
- Original external PR/comment: NOT PUBLISHED
- Product code: NOT_IMPLEMENTED
- Native tests: NOT_RUN
- Index change: NONE
- Previous-case comparison AFTER independent verdict: historical 2026-11-18 PLAN_ONLY / DECISION_READY conditional already selected S3*=C and a run release gate; current independent v0.18 verdict agrees on the scoped hypothesis but makes GO vs validation evidence explicit, updates PR heads, and foregrounds the minimal caller-wrapper counterfactual; existing constructor-acceptance.md/external-issue-draft.md retained as historical, not published.
- Next permitted action: report to Upstream #58 and internal status PR; separately evaluate evidence and owner approval before any public fork or external original communication.


## Post-v0.18.2 same-case native-specific refinement (2026-11-20)

**Status:** reviewed / plan-only, existing stable `browser-run-independent-audit-20261118` case; **proposal-stage GO / research NEEDS_EVIDENCE unchanged**; `S3*=— -> S3*=C` is a hypothetical developer-composable construction, NOT a changed Index grade, shipped feature, independently validated result or maintainer adoption. Historical 2026-11-18 and 2026-11-19 receipts above remain intact. Source observation uses original `browser-use/browser-use@ccbdb8095fbaf903c748880a600054a34c7b6191`; included accepted Index blob `ae39d03d98023d1da055f3b7c215cdbad4009273`, catalog-matching review `50f205533fe10ba35b553d2a3689c77b87bd5d0a`, Profile 0.2.1 / Skills 0.3.1. Refinement protocol `opensiro/upstream@5d004be0000bc6ecb7be62be4584318e8afcf315` (v0.18.2, template/publication preflight).

**Six-function review retained:** S1=A operative `Agent.run` and REPL/browser; S2=— no independent multi-S1 interference closure; S3=— run-local deadline/steps are not whole-system management; S3*=— same-model `judge_run` is not independently authorized result acceptance; S4=— browser task exploration is not prospective organizational adaptation; S5=— parent/integrator supplies authority and domain policy. No standalone current-grade reassessment is claimed.

**Native Track A / exact overlap:** [`Agent._run` in `service.py`](https://github.com/browser-use/browser-use/blob/ccbdb8095fbaf903c748880a600054a34c7b6191/browser_use/agent/service.py) obtains a final screenshot before shutdown; `_judge` runs in shutdown `finally` and can leave `result.judgement=None` without failing the ordinary run. [`views.py`](https://github.com/browser-use/browser-use/blob/ccbdb8095fbaf903c748880a600054a34c7b6191/browser_use/agent/views.py) returns `AgentHistoryList` with `status`, `success`, `messages`, final/structured output and `judgement`; [`judge.py`](https://github.com/browser-use/browser-use/blob/ccbdb8095fbaf903c748880a600054a34c7b6191/browser_use/agent/judge.py) uses redacted/truncated trace and a bounded final-screenshot set, with same producer model. [`test_judge.py`](https://github.com/browser-use/browser-use/blob/ccbdb8095fbaf903c748880a600054a34c7b6191/tests/ci/test_judge.py) exercises nonfatal judge failure. Live checked original PRs remain OPEN at observed heads: [#6414 hooks@252c16a](https://github.com/browser-use/browser-use/pull/6414), [#6415 log@728a671](https://github.com/browser-use/browser-use/pull/6415), [#6446 audit/file guards@b8e2182](https://github.com/browser-use/browser-use/pull/6446), [#6416 effect approval@40a04f0](https://github.com/browser-use/browser-use/pull/6416), [#6423 pre-action injection critic@3b1852c](https://github.com/browser-use/browser-use/pull/6423), [#6452 telemetry/judge reporting@3a83940](https://github.com/browser-use/browser-use/pull/6452), and [#6457 cached same-model judge@de933f7](https://github.com/browser-use/browser-use/pull/6457). Heads/diffs reviewed for #6452 and #6457; none demonstrates independently authorized post-run acceptance/release. Do not treat a proposed PR as merged or an Issue title as approval.

**Track B: smallest Browser Use-native construction (P0, conditional):** an **opt-in verified-delivery path** over existing `Agent.run()`/`AgentHistoryList`, with a frozen redacted run/evidence snapshot produced while the browser page still exists, an integrator-appointed reviewer independent of the agent model, discretionary ACCEPT/HOLD/REQUEST_REWORK, and a typed verified-output view that releases only after ACCEPT. HOLD/REQUEST_REWORK returns an attributed reviewer/evidence receipt to the integrating caller or next task. This does *not* change the ordinary `run()` semantics, undo browser side effects, add a fleet supervisor or require one fixed port count. A caller-side independent reviewer + result withholding is the strongest zero-core-change alternative; that comparator is not presumed inadequate.

**C decision/authority/effect/return:** external parent appoints the reviewer and sets allowed scope; developer-composed reviewer owns the S3* accept/hold decision, not the producer judge or telemetry transport; opt-in verified-result gate enforces the choice on the participating consumer; the decision/evidence identifier and reason return to subsequent operation. Missing/failed reviewer, absent evidence, stale run ID or revoked parent right MUST NOT produce verified release. Failure to achieve that closure falsifies C sufficiency at the declared boundary.

**Priority and falsifier retained:** P0 one coherent opt-in S3* verified-run construction; P1 evidence lifecycle, lawful independent owner and matched caller-wrapper comparison, plus refresh overlapping PR states before implementation; P2 NONE. If a normal caller-side result check and independent verifier provides equivalent accept/hold/evidence with less integration or maintenance effort, prefer no core change. Product adoption remains entirely with original maintainers; neither workarounds nor open Issues prove final architectural intent.

**Validation and rights:** Proposed native acceptance (positive ACCEPT, independent HOLD, absent reviewer/judge failure, stale/missing evidence, legacy `Agent.run` unchanged, matched external-wrapper baseline) is **NOT_RUN**; cost `NOT_MEASURED`. The fork remains `ACTIVE / ALLOW` for internal source-linked case updates only. Current four-file template preflight and canonical structural validation are separate checks against committed metadata, not native tests or permission. `External issue: DRAFT — NOT PUBLISHED`; original/fork-public PR, Issues, comments, product implementation and Index changes: NONE. **No new Upstream status-only PR** under current reporting hygiene; publish only a short completion pointer to [Upstream #58](https://github.com/opensiro/upstream/issues/58).

**Canonical synchronized companions:** [Human issue](issue.md) and [AI constructor sufficiency](constructor-sufficiency.md) follow the v0.18.2 eight-/six-section templates. The preceding historical receipt's suggestion to open an internal report PR is superseded by this section and current [Roadmap reporting hygiene](https://github.com/opensiro/upstream/blob/5d004be0000bc6ecb7be62be4584318e8afcf315/PROTOCOL.md).
