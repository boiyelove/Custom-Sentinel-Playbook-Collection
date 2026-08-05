# Test matrix

| Scenario | Local evidence | Azure/integration evidence |
|---|---|---|
| Valid synthetic request | Approved deterministic plan | Adapter performs intended action |
| Missing tenant or correlation | Denied | Token tenant also verified |
| Public access requested | Denied | Private endpoint reachability proven |
| Embedded or long-lived secret | Denied | Federated identity and least privilege proven |
| Stale evidence | Denied | Source timestamp/signature verified |
| Unknown action | Denied | Provider refuses unsupported mutation |
| Production without approval | Denied | Approval authority and PIM evidence captured |
| Identical replay | Same idempotency key | Exactly-once reconciliation demonstrated |
| Dependency/provider outage | N/A | Bounded retry and observable failure drill |
| Teardown | Documentation check | Resource and cost inventory reaches zero |

Project-specific scenarios to add to an isolated Azure test environment:
Use contract fixtures and API mocks; test create/update/close, duplicate incidents, throttling, retry/dead-letter, sensitive-data redaction, connection failure, least privilege, human approval, and connector portability.
