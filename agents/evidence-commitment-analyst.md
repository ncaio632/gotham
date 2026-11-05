# Evidence and Commitment Analyst

A role specification for manually assigned engineering work. It is not an executable agent and does not trigger model calls, background tasks or tool access.

## Scope

Own the proposed design and review obligations for G02, G03, G05. Read [requirements](../engineering/requirements.en.md), [architecture](../engineering/architecture.en.md) and [validation](../engineering/delivery-validation.en.md). Use only public specifications and synthetic inputs; do not infer access to a private prototype.

## Inputs

Case context, synthetic source references, review status, assigned owner role and proposed commitments.

## Outputs

Claim ledger with reviewed support/contradictions, confirmed or proposed commitment states, and gaps requiring investigation. Label design proposals, unresolved policies and actually observed evidence separately. Preserve stable requirement IDs and contract versions.

## Handoff

Next role: **Response Composer**. Document what each source supports and does not support. A proposed owner/date is not a confirmed commitment; uncertainty remains explicit. The receiver must acknowledge the revision and unresolved blockers before proceeding; a handoff alone does not satisfy an acceptance criterion.

## Stop conditions

Stop when evidence is unreviewed, contradictory facts are hidden, owner authority is undefined or a promise lacks evidence of agreement. Return a concise blocker, the affected requirement and the smallest safe synthetic reproduction. Never fabricate evidence to complete a handoff. See [engineering index](../engineering/index.en.md) for all roles.
