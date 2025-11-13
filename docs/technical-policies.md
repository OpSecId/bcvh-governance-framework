---
icon: lucide/cpu
---

# WebVH Technical Policies

These policies describe the technical expectations for operating WebVH servers, Witness services, Controllers, and Watchers within the BC Verifiable History (BCVH) program. They adapt best practices from Trust over IP guidance and provincial digital service standards while reflecting the WebVH architecture, which relies on HTTP-based history services rather than distributed ledger nodes.

## Technical Summary

| Item | Details |
| --- | --- |
| Technical Protocol | • W3C DID Core v1.0<br>• DIF DID WebVH v1.0 |
| DID Method | • did:webvh or did:web for Controllers<br>• did:key for Witness services |
| Trust Network Supporters | • Anyone using the published did:webvh universal resolver can resolve a did:webvh DIDDoc |
| Verifiable Credential Supporters | • AnonCreds 1 _(Current State)_ (JSON)<br>• AnonCreds 2 _(Future State)_ (JSON)<br>• W3C Verifiable Credentials v2.0 _(Current State)_ (JSON-LD) |
| Supported Revocation Protocol | • AnonCreds Revocation specification<br>• W3C Bitstring StatusList |
| Interoperability Profiles | • did:webvh DIF Universal Resolver<br>• did:webvh |
| Identity Primitives | • BLS-Signature<br>• X25519<br>• Ed25519 |

## WebVH Server Expectations

- Operate on platform-as-a-service or infrastructure-as-a-service environments that support automated scaling, health checks, and blue/green deployments.
- Enforce TLS termination with certificates issued by provincially approved certificate authorities.
- Publish a service metadata document describing available resources, supported codecs, retention guarantees, and registered Watchers.
- Implement rate limiting, structured logging, and request correlation identifiers to support forensic analysis.

### Provisioning Checklist

1. Document infrastructure-as-code definitions, change management workflow, and rollback strategy.
2. Configure automated tests that validate history append semantics, proof generation, and schema validation before deployment.
3. Register service URLs, contact details, and on-call information with the BCVH program office.
4. Validate integrations with the sponsoring Witness and affected Controllers prior to production promotion.

### Decommissioning Checklist

- Notify the BCVH program office and dependent Controllers and Watchers of retirement plans and migration timelines.
- Export history archives and provide checksum manifests to designated archival repositories.
- Revoke API tokens, rotate secrets, remove DNS entries, and update the BCVH service registry when the server is decommissioned.

## Witness Service Policies

- Maintain dedicated attestation services separate from WebVH servers, ensuring high-availability signing and transparency log publication.
- Use FIPS-compliant hardware security modules or equivalent key protection for Ed25519 signing keys.
- Endorse Controller submissions only after verifying schema governance, credential issuance policies, and revocation updates.
- Publish attestation bundles that include hashlinks to the WebVH events and the Witness transparency log index, enabling Controllers to verify state changes.

## Controller Technical Policies

- Implement automated pipelines for schema publication, credential issuance, and revocation updates that enforce witness approval gates.
- Maintain a manifest of resources exposed through WebVH, including links to controlling legislation or policy authority.
- Support DID-based authentication for integration with Witness services; rotate keys in accordance with provincial cryptographic standards.
- Provide Watchers with machine-readable resource manifests so they can register observation coverage.

## Watcher Technical Policies

- Maintain an inventory of monitored resources, including Controllers, schemas, credential definitions, and revocation lists.
- Cache WebVH events and proofs in tamper-evident storage with configurable retention periods aligned to BCVH recordkeeping guidelines.
- Run integrity checks that validate Merkle proofs, witness signatures, and hashlink continuity at ingest time.
- Emit observability signals (metrics, alerts) to the BCVH program office when anomalies or service degradations are detected.
- Provide evidence of capacity planning and disaster recovery to ensure cached histories remain available during primary service outages.

## Security and Privacy Controls

- Follow BC Government Cloud Security Controls or equivalent for identity, access management, vulnerability management, and incident response.
- Apply zero-trust networking principles: restrict inbound traffic, enforce mutual TLS where feasible, and log all administrative actions.
- Store secrets in managed secret vaults with rotation intervals defined by provincial standards.
- Conduct threat modeling exercises focused on data integrity, replay attacks, and unauthorized history modification attempts.
- Perform third-party security assessments or penetration tests when major architectural changes are introduced.

## Monitoring and Incident Response

- Implement shared alerting channels across WebVH operators, Witnesses, Controllers, and Watchers (e.g., dedicated incident bridge and notification platform).
- Define severity levels and response playbooks covering availability degradation, data integrity issues, credential issuance faults, and cache inconsistencies.
- Record incidents in a shared post-incident review system within five business days, including corrective actions and timelines.
- Maintain synthetic monitoring that exercises representative WebVH endpoints, signature verification, and Watcher cache retrieval.

## Change Management and Governance

- Material changes to WebVH APIs, data schemas, or Witness attestation formats require advance notice (minimum 15 business days) to the BCVH program office and registered Controllers.
- All participants must document change approvals, test evidence, and rollback plans in an auditable system.
- Emergency changes must be retrospectively reviewed within two business days, with compensating controls documented when formal approvals are bypassed.

## Alignment and Evolution

These technical policies will evolve alongside the WebVH specification and BC Government digital standards. The BCVH program office will review and update them quarterly or upon major program milestones, engaging Controllers, Witnesses, Watchers, and platform partners to ensure continued alignment with operational realities and provincial policy.

