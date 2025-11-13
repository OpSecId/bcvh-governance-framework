---
icon: lucide/book-open-check
---

# Glossary

> **Note:** This glossary is a living document curated by the BCVH program office. Definitions will evolve as the WebVH platform matures and as BC policy language is refined. When terms trace back to Trust over IP (ToIP), Hyperledger, or other authoritative sources, citations are noted.

## A

### Administering Authority
The organization responsible for operating and maintaining the BCVH governance framework on behalf of the Province of British Columbia.  
_Source: Adapted from Trust over IP Glossary_

### Agent
Software or services that perform automated actions—such as message exchange or credential handling—on behalf of a participant. Agents used with BCVH must comply with provincial privacy and security policies.  
_Source: Hyperledger Foundation_

### AnonCreds
Privacy-preserving credential format that allows selective disclosure of attributes during verification. BCVH Controllers may issue AnonCreds where supported by their credential pipelines.  
_Source: Hyperledger Foundation_

## C

### Cache Registry
A list maintained by a Watcher detailing the WebVH resources it observes and caches, including controllers, schemas, credential definitions, and revocation registries.

### Controller
An approved issuer within BCVH that can publish schemas, issue credentials, and manage revocation registries in coordination with Witness services.

### Credential
A digitally signed assertion representing claims about a subject. In BCVH, credentials follow W3C Verifiable Credential data models and may use AnonCreds cryptography.

## D

### Decentralized Identifier (DID)
A URI-based identifier that resolves to a DID Document containing public keys and service endpoints. In BCVH, Controllers and Witnesses use DIDs for authenticated interactions; Watchers are registered services without assigned DIDs.  
_Source: W3C DID Core_

## G

### Governance Framework
The collection of policies, roles, processes, and technical requirements that define how BCVH operates.

## H

### History Document
A JSON-LD document served by a WebVH server that captures an append-only sequence of events for a resource, including proofs that link each event to prior states.

## P

### Program Office
The BC Government team accountable for administering BCVH governance, standards, and operational oversight.

## R

### Revocation Registry
A resource controlled by a Controller that indicates which credentials have been revoked. Witnesses attest to updates before they become authoritative.

## T

### Trust Registry
A machine-readable listing of approved BCVH participants. Entries for Controllers and Witnesses include DIDs; Watcher entries record service metadata without a DID.  
_Source: Trust over IP Glossary_

### Trust over IP (ToIP)
A layered architecture and governance model for decentralized digital trust infrastructure, providing reference models used in BCVH policy design.  
_Source: Trust over IP Foundation_

## W

### Watcher
An organization or service that observes WebVH resources, caches state snapshots, validates proofs, and reports anomalies. Watchers maintain a cache registry that Controllers can reference to understand observability coverage.

### WebVH Server
An HTTP service that exposes verifiable history endpoints for resources governed by BCVH, providing immutable event logs anchored by Witness attestations.

