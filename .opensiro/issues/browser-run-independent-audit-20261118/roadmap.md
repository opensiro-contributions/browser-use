# Capability Roadmap Receipt — Browser Use independent run-audit constructor

## Identity and pins
- Original repository: browser-use/browser-use
- Original HEAD: ccbdb8095fbaf903c748880a600054a34c7b6191
- Observed at: 2026-11-18
- Accepted Index assessment: https://github.com/opensiro/vsm-harness-index/blob/5f6ea0c777733813ca42e3f210390a719488dcfb/assessments/br/browser-use.md
- Accepted assessment blob SHA: ae39d03d98023d1da055f3b7c215cdbad4009273
- Accepted review ref: 50f205533fe10ba35b553d2a3689c77b87bd5d0a
- Accepted reviewed at: 2026-09-15
- System in focus: first-party Browser Use Agent.run and opt-in independently verified result release, one run, excluding fleet-level resource control
- Historical VSM vector: S1=A / S2=— / S3=— / S3*=— / S4=— / S5=—; no live regrade inferred
- Accepted last check: 2026-09-17 at d8110c5ff87ccba887aaa726cdb780f2f84bef8d
- Fork: opensiro-contributions/browser-use (id 1451835969; confirmed parent browser-use/browser-use; default source b49a68e4060acb226da8f784194fef301c53a6d7)
- Metadata branch: opensiro/meta
- Local case: .opensiro/issues/browser-run-independent-audit-20261118/
- Human Issue: https://github.com/opensiro-contributions/browser-use/blob/opensiro/meta/.opensiro/issues/browser-run-independent-audit-20261118/issue.md
- AI contract: https://github.com/opensiro-contributions/browser-use/blob/opensiro/meta/.opensiro/issues/browser-run-independent-audit-20261118/constructor-sufficiency.md
- Acceptance: https://github.com/opensiro-contributions/browser-use/blob/opensiro/meta/.opensiro/issues/browser-run-independent-audit-20261118/constructor-acceptance.md

## Rights and authority
Both repos report MIT license. Inspected [contributor notes](https://github.com/browser-use/browser-use/blob/ccbdb8095fbaf903c748880a600054a34c7b6191/.github/CONTRIBUTING.md); a definitive CLA/AI policy clearance for an external PR is not asserted. OpenSiro holds fork admin/push permission, and verified the parent. The fork has GitHub Issues DISABLED at observation; publication not possible as-is, and any issue needs its own exact approval. S5/domain/secret authority remains parent-supplied. No external PR/issue permission inferred.

## Existing work / overlap
[SHIPPED judge](https://github.com/browser-use/browser-use/blob/ccbdb8095fbaf903c748880a600054a34c7b6191/browser_use/agent/judge.py), [Agent._judge](https://github.com/browser-use/browser-use/blob/ccbdb8095fbaf903c748880a600054a34c7b6191/browser_use/agent/service.py), [judge tests](https://github.com/browser-use/browser-use/blob/ccbdb8095fbaf903c748880a600054a34c7b6191/tests/ci/test_judge.py) and [merged #6398](https://github.com/browser-use/browser-use/pull/6398): post-run same-agent-model diagnostic review, failure never fails completed run. [Draft #6414](https://github.com/browser-use/browser-use/pull/6414) head f25e90dc96473b96e88285a753befa1d721178aa: action hooks; [draft #6415](https://github.com/browser-use/browser-use/pull/6415) head 4882a0469783a85d9f58de8a1b490da186894f0d: audit; [open #6446](https://github.com/browser-use/browser-use/pull/6446) head b8e2182a2740fc8aebeece4752fe8ab9232eccd5: alternate audit/file guards. Patches examined; all remain unmerged. [Closed-unmerged #4927](https://github.com/browser-use/browser-use/pull/4927); open original Issues [#4860](https://github.com/browser-use/browser-use/issues/4860), [#5137](https://github.com/browser-use/browser-use/issues/5137), [#5293](https://github.com/browser-use/browser-use/issues/5293).

## Function ownership
Historical S1=A remains an accepted past pin, not a current assessment. Single-agent iteration is S1, not S2 or whole-system S3. A same-model in-loop/post-run judge with no independent authority is not sufficient S3*. Parent-supplied domain controls are not autonomous S5; collected website tips are not demonstrated S4. Proposed **S3*=C** requires an independent developer-constructible review owner with evidence, lawful options, enforced verified-result release/hold, durable feedback and explicit parent authority. Reassess aged Index vector separately; no automatic grade update.

## Capability priority
**P0 S3*=C:** opt-in independent run audit-and-release decision, not generic logging. **P1:** reconcile outstanding native hooks/audit PRs, evidence provenance, review authority and distribution/native tests. **P2: NONE**; no justified optional second function. Starting state → current shipped post-run judge → proposed constructor → required integration and native negative tests: see [technical contract](https://github.com/opensiro-contributions/browser-use/blob/opensiro/meta/.opensiro/issues/browser-run-independent-audit-20261118/constructor-sufficiency.md) and [acceptance cases](https://github.com/opensiro-contributions/browser-use/blob/opensiro/meta/.opensiro/issues/browser-run-independent-audit-20261118/constructor-acceptance.md). This is a conditional design, not implemented C.

## Implementation options
Prefer an adapter to existing native judge and eventually accepted #6414/#6415/#6446 primitives, adding only independently composable reviewer and downstream hold/release semantics where missing. A simple result.judgement wrapper is the default cheapest counterfactual. Do not duplicate audit logging, claim tool hooks shipped, or treat a hook alone as independent audit. Design verdict **DECISION_READY conditional**; block implementation until minimality/demand and current PR outcome are confirmed.

## Specification and domain alternatives
A Profile/Skills clarification belongs to its normative owner, not an automatic semantic update. A separate MIT-compatible experimental domain fork can test the API but cannot be called an adopted original feature or new Index grade. Existing company/site policy stays external.

## Cost experiment
Compare matched tasks using default judge+caller guard, accepted native audit hooks, and proposed verified-run API; measure false release/hold, operator usefulness, LOC, integration and maintenance effort, model/latency cost, privacy and replay integrity.
- Cost status: NOT_MEASURED

## Delivery and publication
- Result: PLAN_ONLY
- Decision verdict: DECISION_READY (conditional source-native construction plan; developer demand and upstream PR integration still unverified)
- External issue: DRAFT — NOT PUBLISHED
- Fork public issue: NOT PUBLISHED; fork Issues disabled and exact current-conversation publication approval absent
- Code implementation: NONE
- Native tests executed: NONE
- Index grade changed: NO
- Next decision: inspect which native hook/audit PR becomes accepted, establish actual need beyond caller-side gate, then separately authorize Upgrade or choose NO_USEFUL_CHANGE
- AI disclosure: prepared with AI assistance, no independent human audit or demonstrated cost advantage.
