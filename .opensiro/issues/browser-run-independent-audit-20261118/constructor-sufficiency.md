# Browser Use — minimal independent S3* constructor sufficiency contract

**Target transition:** S3*=— -> S3*=C
**Proposal-stage decision:** GO
**Research disposition:** NEEDS_EVIDENCE

Human [issue.md](issue.md) · canonical [roadmap.md](roadmap.md) · existing [constructor-acceptance.md](constructor-acceptance.md) (historical non-implementation tests).

## Contract boundary and first-party facts

- Original: https://github.com/browser-use/browser-use/commit/ccbdb8095fbaf903c748880a600054a34c7b6191
- Accepted Index: https://github.com/opensiro/vsm-harness-index/blob/c2e43bf4750841277b3e58d8ba80314121734764/assessments/br/browser-use.md ; historical S3*=—, not a live grade.
- Shipped Agent.run: https://github.com/browser-use/browser-use/blob/ccbdb8095fbaf903c748880a600054a34c7b6191/browser_use/agent/service.py ; same-model judge runs after task, failure never aborts run.
- Shipped reviewer input: https://github.com/browser-use/browser-use/blob/ccbdb8095fbaf903c748880a600054a34c7b6191/browser_use/agent/judge.py (redacted truncated trace plus up to four screenshots) and https://github.com/browser-use/browser-use/blob/ccbdb8095fbaf903c748880a600054a34c7b6191/browser_use/agent/views.py (result, self-success, messages, judgement). Existing internal after_tool eval observer in loop.py is not a public authority path.
- Parent policy remains external. No secret, domain or arbitrary Python/network containment claim. S1 is shipped, S2/S3/S4/S5 lack independently justified new construction targets for this one-run boundary.

## Minimum function-specific chain, no fixed ports or test count

1. **Independent observation:** acquire immutable, bounded, provenance-linked run evidence (tool/REPL outcomes + final browser state where permitted), redacted and distinguish missing data from clean outcome; evidence is NOT the producer's self-success bit. Reuse shipped trace and any accepted audit/log PR substrate.
2. **Real alternatives:** allow an independently configured reviewing actor to choose ACCEPT, HOLD or REQUEST_REWORK with evidence citations and scoped rationale, not just produce a report.
3. **Decision owner and authority:** developer supplies a reviewer with separate rule/model/identity, allowed scope and allowed acceptance authority; no self-review promotion, no implicit access to secrets, and no invented S5.
4. **Lawful effect:** consumer gets verified result only after ACCEPT; HOLD and reviewer failure cannot release; REQUEST_REWORK starts another run only when separately authorized and bounded. This is after-run result acceptance, not prevention/undo of browser effects.
5. **Closed feedback:** durable review receipt and accepted/held disposition observable by the next consumer/operator, with meaningful replay/provenance and timeout/recovery behavior.

**Native on-top minimality:** experiment with a thin optional adapter and existing APIs first. The absence of native hooks in shipped main is not permission to copy open #6414, #6415, #6446, #6423 or #6416. If external wrapping already achieves the same accepted outcomes and evidence freshness, do not add a product API.

## Track A and competing native work

- SHIPPED: Pydantic Agent.run, session loop, REPL, judge, results; current head anchored above.
- UNMERGED at observation: #6414 action hooks head 252c16a3fd35375e8642158127120f021085a884; #6415 audit log head 728a671cdc4025ec55a9b1ea9af9d2390a4bd32e; #6446 alternative audit head b8e2182a2740fc8aebeece4752fe8ab9232eccd5; #6423 critic head 3b1852c1d0544e466b674fe034988d009b8966bc; #6416 approvals head 40a04f0120913ae65c1d6da2bdcd4dcc5a6941c7. Do not assume they merge.
- Older original Issues #4860 and #5137 concern audit traces/action evidence; source version 0.x differs, so independent S3* maintainer demand is NOT_STATED.

## Test matrix for future validation (NOT_RUN)

- Reviewer ACCEPT when evidence is complete -> one verified consumer release with receipt.
- Same run, authorized HOLD -> no verified consumer output and clear refusal/reason; audit can lawfully disagree with producer or default judge.
- Reviewer absent, timeout, exception or stale authority -> fail-closed hold in verified mode, never silently drop into unverified success.
- Truncated, missing, tampered or redaction-compromised evidence -> hold/explicit insufficient-evidence result, no false verified success.
- REQUEST_REWORK -> bounded permitted follow-up only, not runaway retries.
- Independent evidence -> show at least one adversarial false-positive producer success decision impossible to justify from producer self-report alone.
- Negative boundary -> original browser side effects not retroactively undone; no cross-tab, domain, credential or policy authority escalation.
- Comparator -> default Agent.run(judge=True) + caller guard + separate external auditor on identical task/test input; measure correctness, false holds, cost, latency, LOC/integration complexity and maintenance.

**GO / NEEDS_EVIDENCE** is a falsifiable design outcome, not native test PASS, shipped feature, new Index grade or economic evidence. STOP on equal-or-better simpler caller solution. This rerun keeps the stable original issue identity and does not send any maintainer communication.
