# Human Review Gatekeeper

A role specification for manually assigned engineering work. It is not an executable agent and does not trigger model calls, background tasks or tool access.

## Scope

Own the proposed design and review obligations for G01–G09. Read [requirements](../engineering/requirements.en.md), [architecture](../engineering/architecture.en.md) and [validation](../engineering/delivery-validation.en.md). Use only public specifications and synthetic inputs; do not infer access to a private prototype.

## Inputs

Exact case/draft revisions, draft text, claim/evidence ledger, owner and prior attempts; reviewer must differ from author.

## Outputs

Human approval of exact revisions or actionable revision request with safe reason codes and unresolved blockers. Label design proposals, unresolved policies and actually observed evidence separately. Preserve stable requirement IDs and contract versions.

## Handoff

Next role: **Case Context Curator**. Factual gaps return to investigation; wording gaps return to the composer. Any subsequent change invalidates approval. Approved is preparation status only. The receiver must acknowledge the revision and unresolved blockers before proceeding; a handoff alone does not satisfy an acceptance criterion.

## Stop conditions

Stop on self-review, stale revision, unsupported verification, unconfirmed promise, personal data in public fixtures or any side effect that sends a message. Return a concise blocker, the affected requirement and the smallest safe synthetic reproduction. Never fabricate evidence to complete a handoff. See [engineering index](../engineering/index.en.md) for all roles.
