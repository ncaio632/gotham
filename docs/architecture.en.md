# Architecture

[README](../README.md)

## Processing flow

```text
Inbound report → facts versus allegations → context review → owner assignment → draft → human approval
```

## Invariants

1. Distinguish the customer report from independently verified facts.
2. Read previous contact attempts before suggesting the same channel again.
3. Do not promise a payment date, investigation outcome or follow-up without a verified owner and commitment.
4. Keep personal case details out of public examples and technical logs.
5. Human approval is a required boundary for external communication.

## Implementation boundary

Editorial workflow and reference contracts. No autonomous sending engine, ticket integration or measured response SLA is claimed.
