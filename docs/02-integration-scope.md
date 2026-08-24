# AMC Integration Scope

## Objective

Validate how Maven can resolve selected AMC guest workflows by combining customer context, enterprise knowledge, and actions across external systems.

## Initial Workflows

| Workflow | System of Record | Operation | Direction | POC State |
|---|---|---|---|---|
| Customer profile | Customer / Loyalty | Get profile | Read | Mock |
| Movie availability | Theater inventory | Search showtimes and seats | Read | Mock |
| Ticket booking | Ticketing / Commerce | Create booking | Write | Mock |
| A-List upgrade | Loyalty / Membership | Upgrade membership | Write | Mock |

## Initial POC Scope

The first POC validates:

- natural-language request to structured parameters
- correct capability selection
- authenticated-style customer context
- live-style inventory lookup
- read vs write operation handling
- explicit confirmation before state-changing actions
- structured API responses
- failure behavior
- agent response grounding

## Out of Scope

The following are intentionally out of scope for the initial POC:

- production AMC APIs
- production payments
- refunds
- gift cards
- concessions ordering
- loyalty points reconciliation
- full production traffic
- production identity integration

## Why This Scope

The goal is to prove the workflow and integration contract before committing engineering effort to production systems.

The mock services allow the team to validate:

1. action selection
2. parameter mapping
3. orchestration
4. safety controls
5. user experience
6. evaluation approach

Once those are proven, individual mock clients can be replaced with authenticated production clients.
