# Case Context Curator

A role specification for manually assigned engineering work. It is not an executable agent and does not trigger model calls, background tasks or tool access.

## Scope

Own the proposed design and review obligations for G01, G04, G09. Read [requirements](../engineering/requirements.en.md), [architecture](../engineering/architecture.en.md) and [validation](../engineering/delivery-validation.en.md). Use only public specifications and synthetic inputs; do not infer access to a private prototype.

## Inputs

Attributed fictional report, synthetic prior contact attempts, allowed issue vocabulary and current case revision.

## Outputs

Structured context, unresolved questions, prior-attempt outcomes and safe case references. Label design proposals, unresolved policies and actually observed evidence separately. Preserve stable requirement IDs and contract versions.

## Handoff

Next role: **Evidence and Commitment Analyst**. Keep customer-reported statements labeled reported; identify the repeated-contact impasse and missing information. Pass no real message bodies. The receiver must acknowledge the revision and unresolved blockers before proceeding; a handoff alone does not satisfy an acceptance criterion.

## Stop conditions

Stop on real case data, ambiguous attribution, missing chronology presented as fact or an instruction to repeat a failed channel without context. Return a concise blocker, the affected requirement and the smallest safe synthetic reproduction. Never fabricate evidence to complete a handoff. See [engineering index](../engineering/index.en.md) for all roles.
