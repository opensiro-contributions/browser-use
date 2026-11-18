# Browser Use — independent S3* run-audit constructor contract

[Human decision Issue](https://github.com/opensiro-contributions/browser-use/blob/opensiro/meta/.opensiro/issues/browser-run-independent-audit-20261118/issue.md) · [Acceptance cases](https://github.com/opensiro-contributions/browser-use/blob/opensiro/meta/.opensiro/issues/browser-run-independent-audit-20261118/constructor-acceptance.md) · [Receipt](https://github.com/opensiro-contributions/browser-use/blob/opensiro/meta/.opensiro/issues/browser-run-independent-audit-20261118/roadmap.md) · **PLAN_ONLY; not implemented**.

## 1. Scope, assessment, boundary

Historical accepted Index: **S1=A · S2=— · S3=— · S3*=— · S4=— · S5=—**, [assessment at fixed Index commit](https://github.com/opensiro/vsm-harness-index/blob/5f6ea0c777733813ca42e3f210390a719488dcfb/assessments/br/browser-use.md), blob ae39d03d98023d1da055f3b7c215cdbad4009273, reviewed 2026-09-15, original review ref 50f205533fe10ba35b553d2a3689c77b87bd5d0a, Profile 0.2.1 / procedure 0.3.1. Live source [ccbdb8095fbaf903c748880a600054a34c7b6191](https://github.com/browser-use/browser-use/commit/ccbdb8095fbaf903c748880a600054a34c7b6191), inspected 2026-11-18; old grades are historical, not a new 1.0 classification. More than 30 days stale: recommend an Index-owned pin/reassessment. System-in-focus: one Agent.run result and a **distinct complementary independent acceptance authority**; not a fleet S3 owner, not agent-loop S1 judgment, not a S5 policy rewrite.

P0 **S3*=C** opt-in developer-composed independent review-and-release. P1 evidence, authority and supported distribution needed for P0. P2 **NONE**: no independent validated optional S2/S3/S4/S5 target. No compulsory C → C(P) → A(P) path.

## 2. Current shipped behavior, exact code ownership

- **SHIPPED**: [Agent.run and _judge](https://github.com/browser-use/browser-use/blob/ccbdb8095fbaf903c748880a600054a34c7b6191/browser_use/agent/service.py), including the API and result.judgement. The _judge docstring explicitly says judge failure **never fails a run**; it calls judge_run using the same agent model. [tests/ci/test_judge.py](https://github.com/browser-use/browser-use/blob/ccbdb8095fbaf903c748880a600054a34c7b6191/tests/ci/test_judge.py) tests that invalid judge output leaves result status completed. [merged PR #6398](https://github.com/browser-use/browser-use/pull/6398) provides current judge.
- **SHIPPED**: [agent/judge.py](https://github.com/browser-use/browser-use/blob/ccbdb8095fbaf903c748880a600054a34c7b6191/browser_use/agent/judge.py) caps/redacts trace, views last screenshots and outputs Judgement(success, failure_reason, gotchas, flags). This is optional in the producer and not independent authorized release.
- **SHIPPED**: [agent/loop.py](https://github.com/browser-use/browser-use/blob/ccbdb8095fbaf903c748880a600054a34c7b6191/browser_use/agent/loop.py) runs Pydantic AI + persistent Python REPL with Session and internal after_tool evaluation observer; the latter is not a supported independent review/release constructor. [agent/views.py](https://github.com/browser-use/browser-use/blob/ccbdb8095fbaf903c748880a600054a34c7b6191/browser_use/agent/views.py) carries status, success, messages, judgement. [telemetry/recorder.py](https://github.com/browser-use/browser-use/blob/ccbdb8095fbaf903c748880a600054a34c7b6191/browser_use/telemetry/recorder.py) is run metrics, not independently controlled complete evidence.
- **SHIPPED**: [domains.py](https://github.com/browser-use/browser-use/blob/ccbdb8095fbaf903c748880a600054a34c7b6191/browser_use/domains.py) and [browser.py](https://github.com/browser-use/browser-use/blob/ccbdb8095fbaf903c748880a600054a34c7b6191/browser_use/browser/browser.py) provide externally supplied domain and browser limits. Explicit limitations of domain guard and Python networking must be preserved and disclosed; **do not** claim comprehensive containment.

## 3. Original work, overlap and legal preflight

| Original item | Checked 2026-11-18 | Relevance and limit |
| --- | --- | --- |
| [PR #6398](https://github.com/browser-use/browser-use/pull/6398) | MERGED; head 30a15d6703cad1cd7773027488e63a1a371a3c47 | Default judge using own model; preserve shipped behavior |
| [PR #6414](https://github.com/browser-use/browser-use/pull/6414) | OPEN / DRAFT; head f25e90dc96473b96e88285a753befa1d721178aa; 8 files, patch inspected | Action hooks for refusal and observation; possible P1 dependency, not S3* release contract |
| [PR #6415](https://github.com/browser-use/browser-use/pull/6415) | OPEN / DRAFT; head 4882a0469783a85d9f58de8a1b490da186894f0d; 5 files, patch inspected | Redacted hash-chained run audit; may supply P1 evidence; incompatible/overlap risk with #6446 |
| [PR #6446](https://github.com/browser-use/browser-use/pull/6446) | OPEN / NOT DRAFT; head b8e2182a2740fc8aebeece4752fe8ab9232eccd5; 11 files, patch inspected | Opt-in audit log/file guards alternate overlapping implementation |
| [PR #6423](https://github.com/browser-use/browser-use/pull/6423) | OPEN / DRAFT; head 52b37ebfb1dbc75c864a6e12fb66568a55e9a98e | Prompt-injection critic before actions: different risk gate, not independent post-run review |
| [PR #6421](https://github.com/browser-use/browser-use/pull/6421) | OPEN / DRAFT; head 4c840039c1b566e79bde78a88888a1d28084ae5b | Stricter browser host guard: parent-policy boundary; not S5= C |
| [PR #4927](https://github.com/browser-use/browser-use/pull/4927) | CLOSED / NOT MERGED; head ee3a2bd5a190555569a5811e0eaeb51ad6ee09cd | Historic run-trace exporter; verify old-API incompatibility before any reuse |
| [Issue #4860](https://github.com/browser-use/browser-use/issues/4860), [#5137](https://github.com/browser-use/browser-use/issues/5137), [#5293](https://github.com/browser-use/browser-use/issues/5293) | OPEN | Session audit, structured action outcomes, policy needs; proposals, not delivered first-party proof |

Verified target fork: opensiro-contributions/browser-use, GitHub repository id 1451835969, fork parent browser-use/browser-use, write/admin permission present, default HEAD b49a68e4060acb226da8f784194fef301c53a6d7, independent opensiro/meta metadata branch. MIT; [contribution landing](https://github.com/browser-use/browser-use/blob/ccbdb8095fbaf903c748880a600054a34c7b6191/.github/CONTRIBUTING.md); unresolved external contributor CLA/AI restrictions require recheck before publication. GitHub Issues disabled on fork at inspection time. No original nor fork Issue/PR authorization from this plan.

## 4. Function-specific proposed five-link C path

| Link | Source-native existing part | Smallest missing first-party addition | Acceptance proof |
| --- | --- | --- | --- |
| **1. Disturbance/evidence** | Agent.run returns result, transcript, judge and telemetry; PR #6415/#6446 propose logs | Redacted, immutable-for-the-review evidence object with run ID, source, ordered outcome/error/omission provenance, explicit evidence-missing state; avoid collecting forbidden secrets | Corrupt/missing/truncated evidence cannot silently release |
| **2. Alternatives** | Judgement has success flag, failure reason | Reviewer-specified accepted/rejected/needs-rework disposition schema with reason and confidence/evidence references | Same run can lawfully be accepted or held by different independent reviewer policies |
| **3. Bounded independent decision actor** | Built-in same-model judge, only diagnostic | Public developer-constructible AuditReviewer interface separate from producer Agent, selectable policy/model/rules, not reuse of producer's success bit; explicit identity and delegated scope | Remove reviewer → verified mode cannot pretend to accept; replace reviewer → distinct lawful decision |
| **4. Authorized effect** | Caller can manually read result.judgement | Opt-in first-party verified-run boundary: consumer receives accepted output only after reviewer accept; otherwise hold/rework receipt; no retroactive browser or secret-policy override | Downstream callback/output absent on hold, present on accept, stable on retries |
| **5. Durable feedback to future work** | Result history and telemetry; PR #6415 audit proposal | Link verdict and evidence hashes/IDs to downstream accepted/held status, reproducible final record, optional permitted retrigger | Query/replay receipt shows exactly what reviewer decided and whether consumer applied it |

**S3* sufficiency condition:** the actor has distinct assessment authority, independent evidence access, a permitted actionable effect on acceptance, and return feedback. A copied prompt, internal judge retry, observability-only export or hardcoded gate does **not** meet C. This is proposed first-party API architecture; no code or tests are claimed to exist. A domain permission or original user approval belongs to parent authority (not fabricated autonomous S5).

## 5. Proposed minimum integration sequence

1. Pin/compare main vs outstanding #6414, #6415 and #6446 including conflicts; **do not** reproduce logging/hooks. Choose an existing shipped or accepted first-party evidence basis. If PRs are rejected or replaced, re-evaluate minimal adapter independently.
2. Define opt-in run evidence scope and redaction at immutable review boundary. Prefer existing run messages + judge and selected audit PR; document what cannot be verified (e.g. remote HTTP, in-page JS, screenshots or hidden page effects).
3. Expose one developer-constructible independent reviewer contract and a result-release owner with explicit fail-closed verified mode. The basic Agent.run and judge=True keep old behavior and cost.
4. Add native positive, alternative, missing actor, reviewer-failure, tampered evidence, unauthorized, privacy and compatibility tests, including a real second-step result consumer. Run source-native tests separately if implementation ever authorized.
5. Measure net value vs minimal caller-side check; if none, stop with NO_USEFUL_CHANGE. Any later original Issue/PR and Index reassessment are separate approval/authority paths.

## 6. Operator decision, authority and no-go

- Developer/operator selects scope, reviewer, policy, and whether to use verified-run API; existing allowed/prohibited domains, secrets and user rights are **parent-owned** and must not be weakened.
- Reviewer can accept, hold or **request** a rework within the configured mode; it cannot invent a domain whitelist, execute browser operations, grant new permissions, or undo web actions. Rework execution, if any, belongs to the preauthorized normal Agent owner.
- External original work remains optional; confirm upstream maintainers prefer a central release gate rather than a documented wrapper. If official built-in judge + simple consumer check gives the same guarantee, choose NO_USEFUL_CHANGE.
- **Proof still missing:** real independent developer demand for a built-in release gate, merged outcome of competing draft PRs, durable evidence semantics across the 1.0 Python-cell engine, and measured advantage vs wrapper. These are conditional implementation gates, not hidden reasons to claim C today.

## 7. Native test and counterfactual

See [AC-01..AC-08](https://github.com/opensiro-contributions/browser-use/blob/opensiro/meta/.opensiro/issues/browser-run-independent-audit-20261118/constructor-acceptance.md). Real first-party fixture should run controlled local browser activity with scripted model, then pass an evidence snapshot to a separate test reviewer; verify an actual downstream consumer's accept/hold state. Keep tests in tests/ci using local resources and scripted FunctionModel as [AGENTS.md](https://github.com/browser-use/browser-use/blob/ccbdb8095fbaf903c748880a600054a34c7b6191/AGENTS.md) requires. **No native test was executed for this PLAN_ONLY assessment.**

## 8. Independent paths, cost and governance

Original-native PR or Issue is separately approved and should avoid duplicating #6414/#6415/#6446; Profile/Skills methodology feedback belongs to their owners; legally scoped experimental fork is optional. Run matched baseline and proposed tasks to quantify review decisions, wrapper LOC, integration/maintenance hours, tokens, added latency, false releases, privacy cost. **Cost status: NOT_MEASURED**. No grade, maintainer acceptance, functional implementation or public Issue/PR has occurred. **AI disclosure:** prepared with AI assistance, not an independent audit of production behavior. [Back to Human Issue](https://github.com/opensiro-contributions/browser-use/blob/opensiro/meta/.opensiro/issues/browser-run-independent-audit-20261118/issue.md).
