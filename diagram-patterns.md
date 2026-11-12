# SOC Diagram Patterns

Reusable diagram patterns. Adapt labels to the actual lesson and explain every component in Bangla.

## A. SOC alert triage

```mermaid
flowchart TD
    A[Alert arrives] --> B[Read alert metadata]
    B --> C[Validate host, user, time, source]
    C --> D[Review supporting telemetry]
    D --> E{Benign explanation found?}
    E -->|Yes| F[Document evidence and disposition]
    E -->|No| G[Assess scope and impact]
    G --> H{Needs escalation?}
    H -->|Yes| I[Escalate with timeline and evidence]
    H -->|No| J[Continue Tier 1 investigation]
```

## B. SIEM data pipeline

```mermaid
flowchart LR
    A[Log sources] --> B[Collection]
    B --> C[Parsing]
    C --> D[Normalization]
    D --> E[Correlation / Detection]
    E --> F[Alert]
    F --> G[Analyst triage]
```

## C. TCP three-way handshake

```mermaid
sequenceDiagram
    participant C as Client
    participant S as Server
    C->>S: SYN
    S-->>C: SYN-ACK
    C->>S: ACK
    Note over C,S: TCP connection established
```

## D. Incident response lifecycle

```mermaid
flowchart TD
    A[Preparation] --> B[Detection and Analysis]
    B --> C[Containment]
    C --> D[Eradication]
    D --> E[Recovery]
    E --> F[Lessons Learned]
    F --> A
```

Note: Framework terminology and phase groupings can vary. Name the framework/source when teaching a specific formal lifecycle.

## E. Evidence confidence ladder

```mermaid
flowchart TD
    A[Single indicator] --> B[Correlate with independent evidence]
    B --> C[Check benign explanations]
    C --> D[Build event timeline]
    D --> E[State confidence and remaining unknowns]
```

Do not treat this as a universal mathematical scoring model. It is a teaching aid for disciplined reasoning.
