# Requirements — gotham

This package turns the public [workflow](../docs/architecture.en.md) into a proposed implementation design. The current public edition is an editorial workflow and reference contracts. It contains no autonomous sender, ticket-system integration or measured response SLA. The modules, stricter contract and checks below are proposed behavior, not a claim of an implemented private or public support platform.

## Outcome and scope

A support specialist receives a complaint, preserves what the customer reported, checks relevant evidence and contact history, assigns an accountable operational role, drafts a response and obtains human review. The output is a reviewed draft with evidence provenance and a clear next step. Sending a message, issuing refunds, changing customer records and deciding legal responsibility are separate actions outside this package.

Customer statements are evidence that a report was made; they are not automatically evidence that the reported event occurred. Conversely, missing internal evidence does not prove the customer is wrong. The workflow must preserve uncertainty instead of resolving it by persuasive wording.

| ID | Proposed required behavior | Failure behavior |
| --- | --- | --- |
| G01 | Capture a synthetic case reference, channel, issue summary and prior contact attempts, preserving attribution. | Reject missing required context; request clarification instead of inventing dates or events. |
| G02 | Maintain claim entries classified as `reported`, `verified`, `disputed` or `unknown`. A verified claim references reviewed evidence and a verifier role. | Unsupported verification cannot pass review; retain the claim as reported/unknown. |
| G03 | Track evidence source reference, review status and relation to each claim. Distinguish an approved source from the truth of every statement in it. | Contradictory evidence enters investigation; never silently discard a contradictory source. |
| G04 | Read previous contact outcomes before proposing an action. If a channel repeatedly failed, address the impasse and propose an owned alternative. | A repeated ineffective instruction requires revision or an explicit justified exception. |
| G05 | Assign one accountable owner role before review. Any promised action requires a confirmed commitment with an owner, due text and evidence reference. | Unconfirmed promises and invented deadlines block approval. No SLA is inferred from this specification. |
| G06 | Tie each factual sentence in a draft to claim references; explicitly attribute unresolved reports. Empathy must not imply verified liability or a guaranteed outcome. | Missing or overstated grounding returns the draft to revision. |
| G07 | Require human approval of the exact case revision and draft revision. The reviewer role must differ from the author role in the proposed demo. | Stale approval, self-review or an unresolved blocker prevents the `approved` state. |
| G08 | Separate approval from delivery; no workflow transition sends externally. Subsequent edits invalidate approval and require another review. | Never label a reviewed draft as sent or resolved without separate observed evidence. |
| G09 | Keep public fixtures and technical evidence entirely synthetic. Logs contain coarse transition/reason codes and references rather than message bodies. | Sensitive content in a fixture blocks publication; redact through a separate reviewed process. |

## Product behavior

The case workspace should display reported content separately from verified findings, show prior contact attempts, identify missing facts and place owner and commitments beside the draft. A review screen must show the exact text and revisions being approved. Allow revision requests with actionable reasons such as `MISSING_EVIDENCE`, `REPEATED_FAILED_CONTACT`, `UNCONFIRMED_COMMITMENT` and `STALE_REVIEW`.

A complaint can be acknowledged while facts remain unresolved: attribution and uncertainty must be explicit, and no unsupported remedy or date may appear. Closing preparation means a reviewed draft exists; it does not mean the service issue was solved.

## Open policy decisions

Before a real implementation, assign owners for evidence freshness, authorized sources, identity/access control, escalation thresholds, retention, language review and sensitive-case handling. The proposed separation of author and reviewer is a design safeguard, not a verified operational staffing policy. Compensation authority, external-channel integrations and delivery authorization remain unspecified and must not be guessed by implementers.


[Engineering index](index.en.md)
