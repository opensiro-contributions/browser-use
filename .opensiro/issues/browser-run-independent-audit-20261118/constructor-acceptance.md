# Browser Use — proposed S3* independent review acceptance matrix

[Human Issue](https://github.com/opensiro-contributions/browser-use/blob/opensiro/meta/.opensiro/issues/browser-run-independent-audit-20261118/issue.md) · [Developer contract](https://github.com/opensiro-contributions/browser-use/blob/opensiro/meta/.opensiro/issues/browser-run-independent-audit-20261118/constructor-sufficiency.md). **PROPOSED ONLY — no tests executed.** All references to C are construction targets, not accepted Index grade.

**Fixture:** scripted local test Agent runs one controlled browser task, emits a redacted evidence snapshot and a candidate result. A separately registered developer reviewer receives that snapshot. A downstream consumer captures a released result or a hold receipt. The reviewer is not the same Agent instance, not a rewrite of its prompt, and owns only the declared post-run acceptance decision.

| Test | Stimulus and actor | Observable downstream assertion | Must fail if |
| --- | --- | --- | --- |
| **AC-01 Positive** | One completed run with verifiable evidence; independently composed reviewer chooses accept | Verified consumer gets run result; durable receipt links evidence hash, reviewer decision and actual release | Only model recommendation or judge flag exists |
| **AC-02 Different lawful choice** | Same evidence, separately supplied reviewer policy chooses hold or request-rework | No verified release; durable hold/rework reason and status visible to consumer | Decision is hardcoded to agent's success bit |
| **AC-03 Missing independent actor** | Verified mode requested with no reviewer | Explicit configuration failure or hold, no fabricated approval | Fallback to producing agent's default judge counts as independent |
| **AC-04 Missing or tampered evidence** | Remove ordered action/terminal evidence, change receipt bytes, or truncate run | Fail closed, evidence insufficiency identified; cannot release | Silent promotion of a partial transcript to complete proof |
| **AC-05 Reviewer failure** | Reviewer raises, times out or emits invalid disposition | Hold or fail-closed typed error; normal result preserved without claiming verification | Failure is swallowed and success reported |
| **AC-06 Parent rights and secrets** | Evidence includes sensitive fields or agent tries out-of-domain site | Reviewer receives only correctly scoped redacted evidence; parent controls remain enforced; no browser action by reviewer | Sensitive text leaks, reviewer grants navigation authority, or claims global sandbox |
| **AC-07 Compatibility and concurrency** | Ordinary Agent.run with judge true/false and two runs under separate reviewers | Original public API behavior preserved; independent review receipts correlate by run ID, no cross-run bleed | Verified mode changes ordinary tasks or misattributes runs |
| **AC-08 Cheapest native alternative** | Run same supported tasks with built-in judge+caller-side gate and proposed first-party verification | Demonstrated material improvement in correctness/maintainability/integration overhead; count added model cost | Equal or worse result at greater total cost ⇒ NO_USEFUL_CHANGE |

**No claim of full browser effect rollback:** a hold prevents only downstream verified-result release, not a web form already submitted by S1. Do not classify audit-only logging as S3*=C; positive decision plus enforced permitted consequence and returned feedback are mandatory.

**Dependency condition:** #6414, #6415 and #6446 are open/unmerged at the 2026-11-18 audit; tests must target the eventually accepted native source before any implementation. Maintain pin and fail-closed negative cases. **P0 S3*=C**, **P1 required evidence/authority substrate**, **P2 NONE**.
