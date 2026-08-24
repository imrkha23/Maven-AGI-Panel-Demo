# Solution Architecture

## High-Level Architecture

```mermaid
flowchart LR
    A[AMC Guest] --> B[Agent Maven]

    B --> C[AMC Guest Experience Charter]
    B --> D[AMC Knowledge]
    B --> E[Maven Capabilities]

    E --> F[Get Customer Profile]
    E --> G[Find Movie Availability]
    E --> H[Book Movie Tickets]
    E --> I[Upgrade A-List]

    F --> J[Customer / Loyalty System]
    G --> K[Theater Inventory System]
    H --> L[Ticketing / Commerce System]
    I --> M[Membership Platform]
