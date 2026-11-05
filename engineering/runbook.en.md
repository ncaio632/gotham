# End-to-end case rehearsal — gotham

This is a planned manual or future local-harness rehearsal using fictional service issues. There is no application or command line to execute in this repository. Do not import actual messages, customer records, screenshots or operational identifiers. A human can walk through the states before a builder implements storage or UI.

## Prepare a case packet

Create `SYN-CASE-A` with a reported issue: “The status is unclear after two unsuccessful support attempts.” Seed two synthetic contact attempts: support form had no acknowledged outcome, and chat could not establish the next owner. Record those as customer-reported outcomes until verified. Assign `support-owner` to coordinate an investigation; this assignment is not a promise of resolution.

Add `SYN-EVIDENCE-A`, a reviewed fictional status record that supports only the claim “a status inquiry was recorded.” It does not establish why service failed or who was responsible. Give that limited claim status `verified` and preserve the broader complaint as `reported`. Have the verifier role explain that boundary. Add a separate reviewed fictional ownership entry `SYN-EVIDENCE-B` supporting only that the unresolved next step is assigned to the support owner for internal review. Verify that limited assignment fact; do not interpret it as proof of a completed review. Add no deadline commitment for the first rehearsal.

## Draft and review

1. Record current case revision and all unknowns. Confirm previous attempts were considered. A draft must not simply direct the customer back to the same unsuccessful route.
2. Compose an acknowledgment with attributed context, limited verified facts and an owned investigation next step. Example: “You reported two unsuccessful attempts to obtain a clear status. A status inquiry is recorded. The support owner will review the unresolved routing question.” The final sentence may appear only if that action is a confirmed commitment; otherwise state that owner confirmation is pending and request confirmation internally before review.
3. For the canonical fixture, avoid a future promise: “You reported two unsuccessful support attempts. A status inquiry is recorded. The unresolved next step is assigned to the support owner for internal review.” Link each factual sentence to its claim. This is a synthetic wording example, not an instruction to send it.
4. Freeze `draft_revision`, transition to `review_pending`, and give a distinct human reviewer the exact draft, claim ledger, prior attempts, owner and revision pair.
5. The reviewer checks attribution, evidence scope, empathy, failed-contact handling and every commitment. Approve only if no blocker remains and the versions match. Record reviewer role and approved case/draft revisions. Inspect state: `approved` must not trigger a message or mark the problem resolved.

## Failure and recovery rehearsal

Change a claim after approval; require `revision_required` and a fresh review. Attempt approval by the author role; require `SELF_REVIEW`. Review an old draft after a concurrent edit; require `STALE_REVIEW`. Mark a claim verified while removing evidence references; schema must reject it. Keep references but change evidence to unreviewed; domain validation must reject it. Add a promised deadline without a confirmed owner's agreement; reject approval even if JSON is structurally valid.

Add a conflicting source. The correct response is to preserve both sources, change the claim to disputed or unknown, and request investigation. Do not select the more convenient source to make the draft easier to approve. Repeat the previously ineffective contact instruction without a justified alternative; return the draft with `REPEATED_FAILED_CONTACT`.

## Evidence and stopping

Record requirement/check IDs, fixture revision, context and draft revisions, expected outcome, actual observation, reviewer role and `not_run/pass/fail/blocked`. Capture only synthetic text. Stop if real case content appears, a review initiates sending, or unsupported factual claims can reach approved state. Preserve sanitized findings and return to investigation rather than editing evidence to fit the draft. Rehearsal completion demonstrates only the observed local workflow; it cannot establish customer outcomes, channel integration or service performance.


[Engineering index](index.en.md)
