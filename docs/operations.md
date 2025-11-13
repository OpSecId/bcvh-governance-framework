---
icon: lucide/server-cog
---

# Operational Policies

Operational policies define how the Province manages the BCVH WebVH verifiable history infrastructure, assesses risk, and ensures ongoing compliance. These policies apply to Witnesses, Controllers, and Watchers and provide the baseline for safe, resilient registry operations.

## WebVH Server Management

### Service Composition

- WebVH servers are standard web services. Operators apply prevailing best practices for availability and scaling (e.g., load balancing, auto-scaling groups, container orchestration) based on demand and service-level objectives.
- WebVH servers are distinct from Witness services. Witnesses operate their own attestation services and integrate with one or more WebVH servers through approved interfaces.
- Organizations are not required to host a WebVH server to participate in governance, but those that do must ensure operational support in line with BC Government service expectations.

### Provisioning Servers

1. Sponsors submit a deployment plan to the BCVH program office, outlining hosting model, security posture, WebVH server topology, and operational contacts.
2. Operators implement standard change management, including infrastructure-as-code reviews, security hardening, and monitoring integration prior to launch.
3. The BCVH technical team validates connectivity with Witness and Watcher services before the WebVH server is promoted to production.

### Retiring Servers

- Sponsors provide notice before decommissioning a WebVH server, unless emergency shutdown is required for security reasons.
- Operational teams coordinate data migration, redirect traffic to alternate endpoints, and ensure continuity for Witness and Watcher integrations.
- After decommissioning, access credentials, DNS entries, and supporting infrastructure are removed from service inventories.
- If an organization exits BCVH entirely, the program office coordinates the decommissioning of related WebVH servers alongside witness credentials and integration endpoints.

## Change Management

- All protocol upgrades, critical configuration changes, or major policy shifts require BCVH program office approval.
- Witness operators schedule maintenance windows and notify Controllers, Watchers, and the BCVH operations channel at least five business days in advance.
- Emergency changes follow an incident response workflow but must be documented retroactively within two business days.

## Risk Management

- Sponsors maintain risk registers covering witness operations, controller pipelines, and integration points.
- Shared risks (e.g., protocol vulnerabilities) are escalated to the BCVH program office for coordinated mitigation.
- Organizations share best practices and lessons learned, subject to confidentiality obligations, to improve collective security posture.

## Incident Response

- Sponsors must maintain incident response playbooks addressing cybersecurity events, privacy breaches, and availability incidents.
- Initial incident notifications must be issued to the BCVH operations channel and affected Controllers and Watchers within one hour of detection for high-severity events.
- Post-incident reports summarize root cause, impact, remediation, and corrective actions and are presented at the next BCVH governance review.

## Audits and Compliance

- Sponsors are encouraged to align with recognized standards (e.g., ISO/IEC 27001, SOC 2) for their infrastructure and operations.
- The BCVH program office may commission independent audits of network health, security, or compliance obligations.
- Findings are tracked in a shared remediation register, with due dates and accountable leads.

## Confidentiality and Data Handling

- Discussions of sensitive operational details (software versions, vulnerabilities, credentials) fall under provincial confidentiality agreements.
- Participants must use secure channels for sharing operational data and apply classification markings consistent with provincial policy.
- Witness operators redact personally identifiable information from reports unless explicit consent is granted for disclosure.
- Watchers must protect cached WebVH state data with controls equivalent to the originating systems and honour retention limits set by the BCVH program office.

## Localization

- The framework, reference policies, and public communications are maintained in English and French.
- Organizations publishing amendments must provide translations before adoption.
- Terminology follows the BCVH glossary, maintained in collaboration with Indigenous language advisors and aligned with the Canadian Digital Trust and Credentials Collaboration taxonomy.

