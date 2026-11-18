**OpenSiro pilot · PLAN_ONLY / DECISION_READY (conditional) · DRAFT — NOT PUBLISHED**  
**Repository:** [browser-use/browser-use](https://github.com/browser-use/browser-use) · **working fork:** [opensiro-contributions/browser-use](https://github.com/opensiro-contributions/browser-use) · **case:** [fork-local metadata](https://github.com/opensiro-contributions/browser-use/blob/opensiro/meta/.opensiro/issues/browser-run-independent-audit-20261118/README.md).  
**Two-level package:** this human decision issue + [AI/developer construction contract](https://github.com/opensiro-contributions/browser-use/blob/opensiro/meta/.opensiro/issues/browser-run-independent-audit-20261118/constructor-sufficiency.md), with [acceptance matrix](https://github.com/opensiro-contributions/browser-use/blob/opensiro/meta/.opensiro/issues/browser-run-independent-audit-20261118/constructor-acceptance.md).

## 1. Why OpenSiro and central accepted VSM assessment

OpenSiro tests whether standardizing agent-harness organization with reusable, VSM-informed specifications can lower implementation, integration and maintenance costs. This is a **hypothesis**, not established savings or a request that Browser Use adopt VSM labels. We organize first-party code and existing original Issues/PRs before suggesting the smallest missing user capability.

**STARTING POINT — ACCEPTED INDEX, NOT THE TARGET:** **S1=A · S2=— · S3=— · S3*=— · S4=— · S5=—**. [Accepted assessment](https://github.com/opensiro/vsm-harness-index/blob/5f6ea0c777733813ca42e3f210390a719488dcfb/assessments/br/browser-use.md), accepted file blob SHA ae39d03d98023d1da055f3b7c215cdbad4009273; review ref 50f205533fe10ba35b553d2a3689c77b87bd5d0a; reviewed 2026-09-15; last accepted check 2026-09-17 at d8110c5ff87ccba887aaa726cdb780f2f84bef8d; Profile 0.2.1, assessment procedure 0.3.1.

| Function | Accepted historical grade | What the grade means for this pilot |
| --- | --- | --- |
| S1 Operations | **A** | Browser agent autonomously operates; do not construct S1 again |
| S2 Coordination | **—** | No evidenced *distinct inter-S1* regulatory scope for this single-agent pilot |
| S3 Current management | **—** | No proven whole-system multiple-S1 commitments/resources owner; do not relabel task budgets |
| S3* Complementary independent audit | **—** | Investigate a genuinely independent, authorized run-acceptance/review constructor |
| S4 Future adaptation | **—** | Website memory and run gotchas alone do not prove organizational outside/then choice and S3 dialogue |
| S5 Policy/identity | **—** | Domain/secret permissions remain supplied by developer/operator; preserve that parent authority |

**Current evidence boundary:** original main HEAD [ccbdb8095fbaf903c748880a600054a34c7b6191](https://github.com/browser-use/browser-use/commit/ccbdb8095fbaf903c748880a600054a34c7b6191) observed 2026-11-18. Browser Use 1.0 now has a Pydantic-AI plus persistent-REPL engine, and a default post-run judge; historical Index grades are not live grades. More than 30 days have passed since the accepted review: recommend a separate Index-owned, source-pinned reassessment without blocking this plan. The system in focus is **one Browser Use Agent.run run and its independently reviewed downstream result**. Browser Harness, Cloud private controls, plugins, a fleet-wide manager and higher recursion are excluded. The fork is a verified fork of browser-use/browser-use; metadata branch opensiro/meta is owned by OpenSiro. Original repository and fork license: MIT. Contributor instructions: [CONTRIBUTING](https://github.com/browser-use/browser-use/blob/ccbdb8095fbaf903c748880a600054a34c7b6191/.github/CONTRIBUTING.md); a definitive external CLA/AI policy conclusion is not claimed.

## 2. Proposed user capability and decision

**P0 — S3*=C, opt-in independent run-result gate.** A developer who operates browser agents can construct a **separate reviewer actor** with its own evidence scope, rules/model and delegated decision permission. Following an actual browser task, it receives an immutable, redacted run evidence snapshot (not a summary written only by the producing agent) and chooses **accept / hold / request-rework**. In a verified-run API mode, only **accept** releases the result to its downstream consumer; hold produces a review receipt and does not falsely report success. A request-rework decision may trigger a new permitted run only where authorized. A reviewer failure or missing evidence holds; it never silently accepts.

**User counterfactual:** currently Agent.run can return a completed result even when the built-in judge fails; callers can inspect result.judgement, but there is no first-party composable, independently owned review-and-release contract. This matters to a developer requiring a repeatable acceptance condition across many automated browser tasks. **Do not claim automatic prevention of actions already performed inside a browser**: the proposed gate controls downstream use of the result, not retroactive browser effects or a global security perimeter.

**Best native alternative:** continue to use Agent(judge=True), result.judgement, result.messages and a caller-side if-check. If that simpler wrapper is equally sufficient for the target deployments, stop with NO_USEFUL_CHANGE rather than add an API.

## 3. Existing original-native work vs missing construction

| Concern | First-party and original work | Residual construction gap |
| --- | --- | --- |
| Judge / S3* | [agent/judge.py](https://github.com/browser-use/browser-use/blob/ccbdb8095fbaf903c748880a600054a34c7b6191/browser_use/agent/judge.py), [agent/service.py](https://github.com/browser-use/browser-use/blob/ccbdb8095fbaf903c748880a600054a34c7b6191/browser_use/agent/service.py), [merged PR #6398](https://github.com/browser-use/browser-use/pull/6398): a separate **request** to the producing agent's own model judges the run | The judge is not an independently configured authority; its failure does not block a completed result |
| Actor observation and enforcement | [draft PR #6414](https://github.com/browser-use/browser-use/pull/6414) introduces before_action/after_action; [draft PR #6423](https://github.com/browser-use/browser-use/pull/6423) introduces an injection critic | Action hooks are not a post-run independent audit owner or a release gate; neither draft is shipped |
| Evidence | [open Issue #4860](https://github.com/browser-use/browser-use/issues/4860), [open Issue #5137](https://github.com/browser-use/browser-use/issues/5137); [draft PR #6415](https://github.com/browser-use/browser-use/pull/6415) hash-chained audit, [open PR #6446](https://github.com/browser-use/browser-use/pull/6446) opt-in action/download audit | A redacted, reviewer-consumable run record with provenance, absence detection, bounded scope and durable review linkage remains to be confirmed; do **not** duplicate overlapping PRs |
| Existing partial alternative | [closed-unmerged PR #4927](https://github.com/browser-use/browser-use/pull/4927) proposed trace exports for old-style runs | Must reassess compatibility with the current Python-cell 1.0 engine; do not revive obsolete APIs |
| Parent authority | [browser domains implementation](https://github.com/browser-use/browser-use/blob/ccbdb8095fbaf903c748880a600054a34c7b6191/browser_use/domains.py), [draft PR #6421](https://github.com/browser-use/browser-use/pull/6421) stricter filtering, [open Issue #5293](https://github.com/browser-use/browser-use/issues/5293) governance | Review must respect existing URL/secret/safety boundaries; it does not construct autonomous S5 |

Existing PR and Issue states were checked on 2026-11-18. Merged means shipped only insofar as present at pinned current HEAD; open PR and Issue proposals are not shipped. Full PR head pins and the first-party ownership chain are in [AI companion](https://github.com/opensiro-contributions/browser-use/blob/opensiro/meta/.opensiro/issues/browser-run-independent-audit-20261118/constructor-sufficiency.md).

## 4. Priorities and minimum sufficient result

| Priority | Outcome | Minimum source-native change |
| --- | --- | --- |
| **P0 S3*=C** | Independent developer-composed run review with visible accept/hold/request-rework and actual result release/hold | **Run completion and evidence → independent bounded reviewer decision → authority-checked release/hold → durable audit receipt → observable downstream status** |
| **P1 enables P0** | Evidence and authorization substrate | Reuse merged judge, run history and current telemetry; reconcile #6414, #6415 and #6446 first. Add only missing supported receipt/export and fail-closed invocation/authorization integration |
| **P2 NONE** | No optional extra VSM capability justified | Fleet S3, long-horizon S4 and autonomous S5 need separate independent user evidence |

**Proposed C sufficiency:** a reusable first-party API accepts the developer's independently composed reviewer and explicit release policy, with positive/negative/native tests and a real subsequent consumer observation. Its adequacy is **design-level only**, not a shipped C or an Index grade.

## 5. Acceptance and stop gates

| Check | Success | Stop/failure |
| --- | --- | --- |
| Positive run | Reviewer sees source-backed evidence, accepts, and supported consumer receives the verified result with receipt | A report/comment or default judge value without enforceable downstream disposition |
| Different lawful option | With the same evidence, another independently supplied lawful reviewer holds result; consumer sees hold, not completed verified output | Hardcoded producer verdict or cosmetic label |
| Missing reviewer or evidence | Opt-in verified mode holds/fails closed, no invented approval | Automatic accept or success on reviewer error |
| Authority / compatibility | Scope, secrets and original domain guards preserved; legacy Agent.run behavior unchanged | Reviewer leaks sensitive data, rewrites S1 task, or changes parent rights |
| Cheapest alternative | Measured incremental value over simple result.judgement wrapper | No material difference → **NO_USEFUL_CHANGE** |

Detailed AC-01 to AC-08 live in [acceptance contract](https://github.com/opensiro-contributions/browser-use/blob/opensiro/meta/.opensiro/issues/browser-run-independent-audit-20261118/constructor-acceptance.md). **Tests have not been run.**

## 6. Independent paths

Original-native: review draft PR overlap, select the smallest integration after maintainer direction and separately authorized Upstream Upgrade. Profile/Skills: only raise a separate methodological question if operational evidence reveals semantic ambiguity. Fork-only experiment: optional and independently licensed, not an automatic implementation.

## 7. Cost hypothesis

Compare matched browser tasks with (A) built-in judge + a small caller-side check, (B) any accepted native audit hooks, and (C) the proposed first-party independent verification mode. Measure false releases/holds, engineering and review hours, integration code, maintenance, privacy overhead, task cost and operator intervention. **Cost status: NOT_MEASURED**.

## 8. Decision and handoff

**Verdict:** PLAN_ONLY / DECISION_READY **for a conditional design**, with materiality and open-PR integration still needing evidence. Do not implement a duplicate logging stack; confirm native API and actual operator benefit first. If the native alternative already suffices, explicitly stop. The [AI/developer contract](https://github.com/opensiro-contributions/browser-use/blob/opensiro/meta/.opensiro/issues/browser-run-independent-audit-20261118/constructor-sufficiency.md) is the source-linked next handoff.

**Publication:** only fork metadata files under opensiro/meta are planned. This is not a public GitHub Issue, a fork-local PR, an original maintainer Issue/PR or an Index revision; all public steps require separate exact approval. At observation time, GitHub Issues are disabled for opensiro-contributions/browser-use. **AI disclosure:** prepared with AI assistance; no native execution, independent human approval or cost reduction claimed.
