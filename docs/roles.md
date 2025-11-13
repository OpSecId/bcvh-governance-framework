---
icon: lucide/users
---

# Governed Roles and Policies

This section defines the governed roles that interact with the BCVH WebVH verifiable history registry, outlining responsibilities, onboarding, and lifecycle expectations. Each governed role maps to a decentralized identifier (DID) issued on the network and tied to a specific function. Organizations may add internal policies provided they remain aligned with the principles of this framework.

## Witness

Witnesses are governed participants who operate verifiable history services. They attest to, anchor, and preserve transactions written to BCVH, ensuring that consumers can cryptographically verify state changes over time.

**General Requirements**

- Witnesses must be delegated by a BC Government ministry, Crown agency, or an Indigenous government operating through agreements with the Province.
- Each Witness has a dedicated DID scoped to a single witness service; shared credentials are not permitted.
- Witness infrastructure must satisfy provincial security, availability, and privacy requirements.

**Responsibilities**

- Operate WebVH witness services that observe, validate, and anchor incoming transactions.
- Maintain verifiable history proofs, ensuring immutability and auditability of recorded events.
- Publish attestations and status updates needed by consuming applications and compliance processes.
- Participate in incident response coordination and contribute telemetry that supports network health reporting.

**Onboarding**

- Sponsoring organizations submit a witness onboarding request to the BCVH program office, including technical architecture, security controls, and operational contacts.
- Approved Witnesses receive configuration packages and credentials for their witness service DID.
- Prior to production activation, Witnesses must complete interoperability testing and provide evidence of monitoring and alerting coverage.

**Offboarding**

- When a Witness retires or transitions to another organization, the sponsor must notify the BCVH program office and revoke associated credentials.
- Witness data and attestations must be archived or transferred according to BCVH retention policies to preserve verifiable history continuity.

## Controller

Controllers author transactions that become part of the verifiable history. They represent ministries, agencies, Indigenous governments, and other approved public sector entities operating within their legislated mandates and act as the issuers of verifiable credentials within BCVH.

**General Requirements**

- Controllers must hold a unique Controller DID provisioned through BCVH onboarding.
- Controller solutions must implement WebVH interfaces, support credential issuance and revocation operations, and align with privacy-by-design expectations.
- Controllers remain accountable for the legal authority underpinning the statements and credentials they publish.

**Responsibilities**

- Publish schemas, credential definitions, and other governing artifacts that comply with applicable legislation and policy.
- Issue credentials and manage associated revocation registries, ensuring state changes are endorsed by designated Witnesses before anchoring.
- Maintain accurate metadata for their Controller DID, including contact details and legal authority statements.
- Implement revocation or correction processes that interoperate with Witness records and provide timely updates to consuming systems.

**Onboarding**

- Eligibility is limited to entities recognized under provincial legislation or through formal agreements with the Province of British Columbia.
- Applicants provide architecture diagrams, data classification assessments, and compliance attestations for review.
- Upon approval, the BCVH program office provisions a Controller DID and shares technical integration guides.

**Offboarding**

- Controller DIDs remain part of the verifiable history. When a Controller exits the program, their ability to submit new transactions is revoked, and relevant relying parties are notified.
- Historical records must be retained in accordance with provincial records management standards.

## Watcher

Watchers provide independent observation, caching, and analytics on BCVH activity. They consume attested history data from WebVH services to enable transparency, audit, and operational insights without modifying the ledger.

**General Requirements**

- Watchers must operate under agreements with the BCVH program office, ensuring compliance with privacy and acceptable use policies.
- Watchers maintain a registry of resources (e.g., controllers, schemas, credential definitions) that they monitor and cache; Controllers may publicly list the Watchers observing their resources to improve transparency.

**Responsibilities**

- Monitor witness attestations and controller activity for anomalies, availability, and policy compliance.
- Cache WebVH state snapshots and proofs to provide rapid access, redundancy, and historical replay capabilities for consuming services.
- Keep the registry of watched resources current, ensuring handoffs or retirements do not leave gaps in observability.
- Produce reports and dashboards that inform BCVH program governance, risk management, and transparency commitments.
- Coordinate with Witnesses and Controllers when findings indicate operational or compliance issues.

**Onboarding**

- Applicants describe their monitoring objectives, caching architecture, tooling, data handling controls, and initial watch list.
- The BCVH program office validates alignment with provincial oversight mandates and confirms that Controllers can reference the Watcher in resource registries where applicable.

**Offboarding**

- When a Watcher’s mandate concludes or is revoked, credentials are disabled and data retention obligations are reviewed with the program office.

## Supporting Stakeholders

- **Technical Integrators:** Vendors and solution providers that connect applications or wallets to BCVH. They must align with interoperability specifications and security requirements.
- **BCVH Program Office:** The provincial governance body that interprets this framework, approves changes, and coordinates dispute resolution.

## Policy Exceptions

Participants seeking temporary deviation from these policies must submit a written request to the BCVH program office, outlining scope, rationale, compensating controls, and sunset dates. Approved exceptions are logged and reviewed quarterly.

