# My Voice — Architecture

```mermaid
flowchart LR
    U[User] -->|Voice / Text / Tap| A[Simulated Alexa+ Interface]

    A --> R[Intent Router]

    R --> E[Explain Engine]
    R --> M[Memory Engine]
    R --> S[Speak-for-Me Engine]
    R --> K[Safety / Risk Engine]
    R --> T[Trusted Contact Flow]
    R --> W[Waiting / Resolution Engine]

    E --> X[Structured Fact Extractor]
    K --> Y[Weighted Risk Rules]
    S --> C[Consent Gate]
    T --> C

    M --> D[(Persistent User State)]
    X --> D
    Y --> D
    C --> D
    W --> D

    D --> L[Audit / Timeline]
    D --> A

    C -->|Only after explicit confirmation| Q[Simulated Share]

    subgraph Production Alexa+ Path
      P[Alexa+ Add-on] --> O[OAuth Account Linking]
      O --> B[User-owned Backend]
      B --> D2[(Secure Cloud State)]
      B --> I[Optional Authorised Integrations]
    end
```

## Current prototype
- Runs locally in the browser.
- No paid API dependencies.
- Voice input uses browser speech recognition where supported.
- All workflows also work with text input.
- Persistence uses local browser storage.
- External sending is simulated.

## Production path
A production version could replace the simulated interface with an Alexa+ add-on, use the account-linking method required for its integration path, and move persistent user data into a secure backend. None of that production path is implemented in this prototype. Alexa+ add-on tooling is currently available only to selected partners, and a real release would require certification and on-device testing.

Consent, sharing permissions and safety rules should remain deterministic and auditable even if an LLM is later introduced for language understanding.
