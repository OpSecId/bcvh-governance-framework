---
icon: lucide/file-stack
---

# Appendices

## Appendix A — Governed Roles Summary

The table below summarizes governed and supporting participants in British Columbia's WebVH Verifiable History implementation.

| Role | Status | DID Assignment | Key Responsibilities |
| --- | --- | --- | --- |
| **Witness** | Governed role | 1 DID per witness service | Operates WebVH witness infrastructure, anchors transactions, publishes attestations, coordinates incident response |
| **Controller** | Supporting role | 1 DID per authorized entity | Authors verifiable history records, submits transactions to Witnesses, maintains controller metadata and correction workflows |
| **Watcher** | Supporting role | Resource registry per monitoring service | Observes and caches WebVH state, maintains watched-resource lists, produces compliance and transparency reports, escalates anomalies |

## Appendix B — Role Interaction Diagram

``` mermaid
flowchart LR
    subgraph Authorized Organization
        Controller -->|Submits txn| Witness
    end

    Witness -->|Anchors| History[(WebVH History Ledger)]
    Watcher -->|Observes| History
    History -->|Serves proofs| Consumers

    classDef watcher fill:#e0d7ff,stroke:#4c35a3,stroke-width:1px;
    classDef witness fill:#c9f1ff,stroke:#00668c,stroke-width:1px;
    classDef controller fill:#fcebba,stroke:#8c6d00,stroke-width:1px;
    classDef consumer fill:#f3f3f3,stroke:#999,stroke-width:1px;

    class Witness witness;
    class Controller controller;
    class Watcher watcher;
    class History,Consumers consumer;
```

## Appendix C — Document Change Control

- **Version 0.1 (Draft):** Initial release aligned with BCVH launch, capturing governance, role policies, and operational guidance.
- **Update Cycle:** Reviewed quarterly by the BCVH program office, or sooner in response to major protocol, legislative, or risk changes.
- **Amendment Process:** Proposed changes are circulated for provincial stakeholder comment (minimum 10 business days), ratified by the BCVH governance authority, and published with bilingual support.

## Appendix D — WebVH Deployment Diagram

``` mermaid
flowchart LR
    User[Issuer / Verifier Admin] --> UIFrontend["Tenant UI Frontend"]
    UIFrontend --> TenantProxy["Tenant Proxy"]
    TenantProxy --> ACApy["Traction ACA-Py Agent"]

    subgraph Traction["Traction Platform"]
        UIFrontend
        TenantProxy
        ACApy
    end

    subgraph WitnessService["Witness Service"]
        EndorserAPI["Endorser API"]
        WitnessAgent["Witness Agent"]
    end

    subgraph WebVH["WebVH Server"]
        WebVHService["WebVH API"]
    end

    subgraph WatcherLayer["Watcher Service"]
        Watcher["Watcher Worker"]
    end

    EndorserAPI --> WitnessAgent
    WitnessAgent -. webhooks .-> EndorserAPI
    WitnessAgent -. "DIDComm connection" .- ACApy
    ACApy --> WebVHService
    ACApy --> Watcher
    Watcher --> WebVHService
```

