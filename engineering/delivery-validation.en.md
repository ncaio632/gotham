# Implementation backlog and validation — gotham

## Ordered work packages

These packages define a buildable sequence, not an implemented roadmap with dates. A human may first exercise the contracts manually. Each item needs observed evidence before it is marked complete.

| Order | Work package | Acceptance criteria and dependency |
| --- | --- | --- |
| B1 | Define a synthetic case and policy vocabulary | Establish allowed evidence states, owner roles, revision rules and unresolved policies. No dependency. Fixture source limitations are written explicitly. |
| B2 | Implement intake and evidence ledger | After B1, preserve report attribution and prior contact history; resolve references; reject verified claims without reviewed support; retain contradictions. |
| B3 | Implement ownership and commitment handling | After B2, require one owner for review; distinguish proposed from confirmed commitments; block invented dates and unauthorized promises. |
| B4 | Implement draft composition and traceability | After B3, map factual sentences to claim references, show uncertainty, surface previous failed contacts and allow actionable revision requests. |
| B5 | Implement human review and concurrency guard | After B4, compare exact case/draft revisions atomically, prevent author self-review, invalidate approval on any change and emit no delivery action. |
| B6 | Execute rehearsal and independent editorial review | After B5, populate every validation row with observed outcome or explicit blocker; inspect sanitized logs and confirm no integration or outcome claims were added. |

Do not add a mail or ticket adapter to satisfy B5. Approval is intentionally a preparation boundary. Any future delivery capability requires a separately reviewed contract and explicit authorization for recipients and purpose.

## Requirements-to-validation traceability

All following product checks are **planned, not executed** by publishing this specification. Editorial correctness needs human judgment in addition to structural validation.

| Requirement | Proposed check | Acceptance observation |
| --- | --- | --- |
| G01 | Omit context; provide attributed report and prior attempts | Request clarification without inventing chronology; preserve the original reported status. |
| G02 | Verified claim without evidence/verifier; uncertain complaint | Reject unsupported verification; keep complaint attributed. |
| G03 | Unreviewed, missing and contradictory evidence | Resolve references; block unsupported assertion; retain conflict for investigation. |
| G04 | Two failed contacts followed by the same instruction | Return revision request unless a reviewed reason justifies repeating it. |
| G05 | Missing owner; proposed commitment used as promise | Block review/approval; require authorized confirmed commitment. |
| G06 | Draft overstates a limited source or implies liability | Human reviewer requests correction and records the unsupported sentence. |
| G07 | Author self-review; stale case/draft revisions; concurrent edit | Reject self-review or stale approval; no approved state for mismatched revisions. |
| G08 | Approve then edit; inspect side effects | Approval invalidated; zero external sends and no inferred resolution. |
| G09 | Inspect all fixture and technical evidence fields | Only fictional content and safe references; no real message bodies in logs. |

## Contract fixtures and limitations

Use Draft 2020-12 to validate the [schema](../contracts/case-review.schema.json). [Valid review](../examples/review.valid.json) contains an attributed claim, limited verified facts, reviewed fictional evidence and approval of matching revisions by a distinct role. It demonstrates contract shape, not actual support quality or communication.

[Invalid schema example](../examples/review.invalid-schema.json) removes evidence references from a verified claim and must fail at `claims[1].evidence_refs`. [Invalid semantic example](../examples/review.invalid-semantic.json) keeps valid shape but sets the reviewer to the author role and approves an older draft revision. It should pass JSON Schema and then fail domain checks `SELF_REVIEW` and `STALE_REVIEW`. A validator that reports that fixture structurally valid is behaving as intended.

Schema cannot verify that a source supports a sentence, compare cross-field revision values, prove owner authority, detect a tactless or misleading sentence or establish whether an action happened outside the system. Reference resolution, commitment authorization and review policy belong to the application/domain layer; factual fidelity and tone also require a person. Keep these validation layers distinct in reports.

## Evidence and exit criteria

Each future record must include check ID, requirement ID, build and fixture revisions, environment, case/draft revisions, expected behavior, observed behavior, verdict and reviewer role. Keep status explicitly `not_run`, `pass`, `fail` or `blocked`; fixture existence is not a passed workflow check. Do not include private complaints in reproducibility artifacts.

Exit requires all invariant checks observed and independently reviewed in a synthetic implementation, with open policy decisions assigned. Real operation still requires access controls, retention rules, escalation ownership and an approved integration/delivery boundary. No customer satisfaction, turnaround time, production readiness or SLA can be claimed from these documentation checks.


[Engineering index](index.en.md)
