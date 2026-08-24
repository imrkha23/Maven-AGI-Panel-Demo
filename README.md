# Maven AGI × AMC Theatres — Enterprise Integration POC

This repository demonstrates how I approach a customer integration as a Solutions Engineer: from technical discovery through API design, authentication, working proof of concept, testing, and production readiness.

## Business Use Cases

This AMC proof of concept focuses on four workflows:

1. Retrieve authenticated guest context
2. Find alternative movie and seat inventory
3. Book tickets after explicit customer confirmation
4. Upgrade an eligible guest to AMC Stubs A-List

## POC Architecture

Customer Request  
→ Agent Maven  
→ Charter + Knowledge + Customer Context  
→ Maven Capability  
→ External System / Mock API  
→ Structured Response  
→ Customer Resolution

## What This Repo Demonstrates

- Technical discovery
- Systems-of-record mapping
- REST API design
- Authentication strategy
- JSON payload mapping
- TypeScript integrations
- Postman testing
- Error handling
- Retry logic
- Rate-limit handling
- Idempotent write operations
- Security and least privilege
- Agent evaluation
- Observability
- POC success criteria
- Production readiness

## Integration Approach

Customer Requirement  
→ Technical Discovery  
→ System of Record  
→ API Documentation  
→ Authentication  
→ Schema Mapping  
→ Postman Validation  
→ Maven Capability  
→ Testing  
→ Evaluation  
→ Production Readiness

## Current AMC Capabilities

### Get AMC Customer Profile
Retrieves authenticated guest context such as membership status, preferred theater, seating preferences, and masked payment information.

### Find AMC Movie Availability
Searches available movie inventory using movie title, format, date, time, seat count, theater preference, and seating preference.

### Book AMC Movie Tickets
Completes a ticket purchase only after explicit customer confirmation.

### Upgrade AMC A-List Membership
Upgrades an eligible guest to AMC Stubs A-List after benefits are explained and the guest confirms the account change.

## POC Data Strategy

AMC production APIs are not used in this lab.

External AMC systems are represented using deterministic mock integrations so the POC can validate:

- capability selection
- parameter mapping
- orchestration
- customer context
- safety controls
- confirmation logic
- structured responses
- failure handling

The mock integrations are designed so they can later be replaced by authenticated production API clients without changing the agent-facing contract.

## Architecture

```mermaid
flowchart LR
A[AMC Guest] --> B[Agent Maven]

B --> C[AMC Guest Experience Charter]
B --> D[AMC Knowledge]
B --> E[Maven Capabilities]

E --> F[Customer Profile]
E --> G[Movie Inventory]
E --> H[Ticket Booking]
E --> I[A-List Membership]

F --> J[Customer / Loyalty System]
G --> K[Theater Inventory System]
H --> L[Ticketing / Commerce System]
I --> M[Membership Platform]
