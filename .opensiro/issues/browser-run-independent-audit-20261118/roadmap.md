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
