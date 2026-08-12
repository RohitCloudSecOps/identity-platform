# Enterprise Leaver Identity Lifecycle

## Executive Summary

The Enterprise Leaver Identity Lifecycle defines the standardized process for removing or disabling identity access when an employee, contractor, or workforce member leaves the organization.

The Leaver process is designed to ensure that access is revoked in a controlled and timely manner across enterprise directories, cloud identity platforms, applications, privileged access systems, and connected infrastructure.

The process begins with an authoritative workforce termination event and continues through identity disablement, session revocation, application deprovisioning, privileged access removal, credential handling, reconciliation, and audit validation.

---

# Business Scenario

A workforce member leaves the organization and must no longer retain access to enterprise resources after the approved termination point.

| Requirement | Expected Outcome |
|-------------|------------------|
| Termination Detection | Authoritative termination event is received. |
| Identity Protection | Identity is disabled according to policy. |
| Authentication Revocation | Active authentication sessions and tokens are revoked where supported. |
| Application Deprovisioning | Application accounts are disabled or removed. |
| Access Revocation | Assigned permissions are removed. |
| Privileged Access Removal | Administrative access is revoked immediately according to policy. |
| Credential Protection | Managed credentials and secrets are rotated where required. |
| Auditability | All termination activities are recorded. |
| Reconciliation | Downstream systems reflect the expected terminated state. |

---

# Source of Authority

The Leaver process should originate from an authoritative workforce lifecycle event.

| System | Responsibility |
|--------|----------------|
| HR System | Provides authoritative termination information. |
| Identity Governance Platform | Orchestrates lifecycle and access revocation policies. |
| Enterprise Directory | Disables the enterprise identity. |
| Cloud Identity Provider | Revokes cloud authentication and access. |
| Provisioning Platform | Deprovisions connected application accounts. |
| PAM Platform | Removes privileged access and administrative permissions. |
| Application Platforms | Disable or remove application accounts. |
| SIEM / Audit Platform | Records termination and access-revocation events. |

---

# Leaver Identity Attributes

| Attribute | Purpose |
|-----------|---------|
| Employee ID | Maintains identity correlation. |
| Employment Status | Indicates active or terminated state. |
| Termination Date | Defines the approved lifecycle transition point. |
| Termination Type | Supports applicable offboarding policy. |
| Department | Provides organizational context. |
| Manager | Supports ownership and offboarding coordination. |
| Employment Type | Determines applicable lifecycle rules. |
| User Identity | Identifies enterprise accounts requiring action. |
| Privileged Status | Identifies elevated accounts requiring enhanced controls. |

---

# Leaver Lifecycle Workflow

```text
HR Termination Event
        │
        ▼
Termination Validation
        │
        ▼
Identity Correlation
        │
        ▼
Authentication Revocation
        │
        ▼
Directory Disablement
        │
        ▼
Cloud Identity Disablement
        │
        ▼
Application Deprovisioning
        │
        ▼
Privileged Access Revocation
        │
        ▼
Credential / Secret Handling
        │
        ▼
Reconciliation
        │
        ▼
Audit & Monitoring
```

---

# Leaver Processing Stages

| Stage | Process | Expected Result |
|-------|---------|-----------------|
| 1 | Receive termination event | Authoritative Leaver event exists. |
| 2 | Validate termination data | Required lifecycle attributes are valid. |
| 3 | Correlate identity | Correct enterprise identity is identified. |
| 4 | Determine termination timing | Revocation timing is established according to policy. |
| 5 | Revoke authentication | Active authentication sessions and tokens are invalidated where supported. |
| 6 | Disable directory identity | Enterprise directory account is disabled. |
| 7 | Disable cloud identity | Cloud account access is revoked. |
| 8 | Deprovision applications | Connected application accounts are disabled or removed. |
| 9 | Revoke privileged access | Administrative permissions and PAM access are removed. |
| 10 | Handle credentials | Relevant credentials and secrets are rotated or secured. |
| 11 | Reconcile systems | Downstream systems match expected terminated state. |
| 12 | Record audit events | Complete termination evidence is captured. |

---

# Termination Timing Model

Leaver processing should distinguish between termination timing and access-revocation requirements.

| Termination Type | Example | Access Handling |
|------------------|---------|-----------------|
| Immediate Termination | Security-sensitive termination | Revoke access immediately according to policy. |
| Scheduled Termination | Planned employee departure | Revoke access at approved termination time. |
| Contract Expiration | Contractor engagement ends | Disable access according to contract end policy. |
| Retirement | Employee retires | Execute standard termination workflow. |
| Internal Transfer | Employee moves internally | Use Mover lifecycle instead of Leaver where identity remains active. |

---

# Access Revocation Model

| Access Category | Leaver Action |
|----------------|---------------|
| Corporate Identity | Disable |
| Cloud Identity | Disable / revoke access |
| Authentication Sessions | Revoke where supported |
| Application Accounts | Disable or remove |
| Group Memberships | Remove |
| Role Assignments | Remove |
| SaaS Access | Deprovision |
| Cloud Permissions | Remove |
| Privileged Access | Revoke immediately according to policy |
| PAM Accounts | Disable / remove |
| Service Ownership | Transfer where required |
| API Tokens | Revoke or rotate where applicable |
| Certificates | Revoke or replace where applicable |

---

# Leaver Security Controls

| Security Control | Description | Objective |
|------------------|-------------|-----------|
| Authoritative Termination | Process only validated workforce termination events. | Prevent unauthorized identity actions. |
| Immediate Revocation | Revoke access according to termination policy. | Prevent continued access. |
| Session Revocation | Invalidate active sessions and tokens where supported. | Limit active session exposure. |
| Directory Disablement | Disable enterprise identity. | Prevent authentication. |
| Application Deprovisioning | Remove or disable application accounts. | Prevent residual access. |
| Privileged Access Revocation | Remove administrative permissions. | Protect critical resources. |
| Credential Rotation | Rotate credentials or secrets associated with departing identities where required. | Reduce credential exposure. |
| Audit Logging | Record all revocation operations. | Support compliance and investigation. |
| Reconciliation | Validate downstream systems. | Detect residual access. |

---

# Leaver Success Criteria

| Validation Area | Success Condition |
|----------------|-------------------|
| HR Event | Valid termination event received. |
| Identity Correlation | Correct identity identified. |
| Authentication | Active sessions and authentication access revoked where supported. |
| Directory | Account disabled according to policy. |
| Cloud Identity | Cloud access disabled. |
| Applications | Application accounts deprovisioned. |
| Groups | Group memberships removed. |
| Roles | Role assignments removed. |
| Privileged Access | Administrative permissions revoked. |
| Credentials | Required credentials and secrets handled securely. |
| Reconciliation | Downstream systems match terminated state. |
| Audit | Complete lifecycle evidence captured. |

---

# Termination Governance Model

Leaver processing should be governed according to termination type, timing, risk, and organizational policy.

| Termination Category | Access Action | Governance Requirement |
|----------------------|---------------|------------------------|
| Standard Termination | Revoke access at approved termination time | Standard lifecycle policy |
| Immediate Termination | Revoke access immediately | Enhanced monitoring |
| Contractor Expiration | Disable access at contract end | Contract/lifecycle policy |
| Security-Sensitive Termination | Immediate access revocation | Security team coordination |
| Privileged User Termination | Immediate privileged access revocation | PAM/security controls |
| Internal Transfer | Use Mover lifecycle | Do not terminate enterprise identity |

---

# Revocation Sequence

The order of operations should minimize the period during which a terminated identity could retain access.

| Sequence | Action | Expected Result |
|----------|--------|-----------------|
| 1 | Receive termination event | Authoritative event is available |
| 2 | Validate termination information | Event passes validation |
| 3 | Correlate identity | Correct identity is identified |
| 4 | Determine revocation timing | Policy determines execution time |
| 5 | Revoke active sessions | Existing sessions are invalidated where supported |
| 6 | Revoke authentication | Authentication access is blocked |
| 7 | Disable directory account | Enterprise identity becomes inactive |
| 8 | Disable cloud identity | Cloud authentication is blocked |
| 9 | Remove group memberships | Group-based access is removed |
| 10 | Deprovision applications | Application access is disabled |
| 11 | Revoke privileged access | Administrative access is removed |
| 12 | Handle credentials and secrets | Relevant credentials are rotated or secured |
| 13 | Reconcile downstream systems | Residual access is identified |
| 14 | Complete audit processing | Termination evidence is recorded |

---

# Access Revocation Matrix

| Resource Type | Revocation Action | Priority |
|---------------|-------------------|----------|
| Enterprise Directory | Disable account | Critical |
| Cloud Identity | Disable / revoke access | Critical |
| Active Sessions | Revoke where supported | Critical |
| Privileged Accounts | Disable / revoke | Critical |
| PAM Access | Remove access and active sessions | Critical |
| SaaS Applications | Deprovision account | High |
| Cloud Roles | Remove assigned permissions | High |
| Directory Groups | Remove membership | High |
| Application Roles | Remove assignments | High |
| API Tokens | Revoke or rotate where applicable | High |
| Certificates | Revoke or replace where applicable | High |
| Collaboration Services | Disable access | High |

---

# Error Handling

Leaver processing must safely handle failures without assuming that downstream access has been successfully revoked.

| Failure | Potential Cause | Recommended Action |
|--------|-----------------|--------------------|
| Invalid Termination Event | Missing or inconsistent HR information | Hold processing and validate source event. |
| Identity Correlation Failure | Identity cannot be matched | Stop automated action and investigate. |
| Session Revocation Failure | Target service does not respond | Retry and escalate according to policy. |
| Directory Disablement Failure | Directory service unavailable | Retry and alert IAM operations. |
| Cloud Disablement Failure | Cloud identity service issue | Retry and monitor until confirmed. |
| Application Deprovisioning Failure | Connector or application unavailable | Queue operation for retry. |
| PAM Revocation Failure | PAM service or target unavailable | Escalate immediately to privileged access team. |
| Credential Rotation Failure | Target credential system unavailable | Apply incident response and compensating controls. |
| Reconciliation Failure | Downstream state differs from expected state | Investigate residual access immediately. |

---

# Exception Management

Exceptions must remain visible and accountable until the identity reaches the required terminated state.

| Exception | Handling Approach | Owner |
|-----------|-------------------|-------|
| Missing Termination Data | Correct authoritative HR information. | HR |
| Unknown Identity | Perform identity correlation investigation. | IAM Operations |
| Failed Directory Disablement | Retry and escalate if unresolved. | IAM Operations |
| Failed Application Deprovisioning | Retry and coordinate with application owner. | IAM / Application Team |
| Failed Privileged Revocation | Escalate immediately to PAM/Security. | PAM / Security |
| Residual Access Detected | Investigate and remove remaining access. | IAM / Application Owner |
| Credential Exposure Risk | Rotate or revoke affected credentials. | Security / Application Team |
| Partial Completion | Track completed and failed operations separately. | IAM Operations |

---

# Audit Events

Every significant Leaver operation should generate an auditable event.

| Event | Audit Information |
|-------|-------------------|
| Termination Event Received | Employee ID, source, timestamp |
| Termination Validated | Validation result |
| Identity Correlated | Identity identifier and correlation result |
| Session Revoked | Session identifier and timestamp where available |
| Authentication Revoked | Identity and revocation timestamp |
| Directory Disabled | Account identifier and timestamp |
| Cloud Identity Disabled | Cloud identity and timestamp |
| Group Membership Removed | Group and identity information |
| Application Deprovisioned | Application and account identifier |
| Privileged Access Revoked | Resource, privilege, timestamp |
| Credential Rotated | Credential category and target system |
| Reconciliation Completed | Expected versus actual state |
| Leaver Completed | Overall lifecycle result |

---

# Operational Monitoring

| Monitoring Area | Indicator | Operational Response |
|----------------|-----------|----------------------|
| Termination Events | Pending termination events | Investigate lifecycle processing. |
| Identity Disablement | Failed account disablements | Escalate to IAM operations. |
| Session Revocation | Active sessions remaining | Revoke or terminate sessions. |
| Application Deprovisioning | Failed application removals | Retry and coordinate with application owner. |
| Privileged Access | Active privileged permissions | Escalate immediately. |
| Credential Handling | Rotation or revocation failures | Apply compensating controls. |
| Residual Access | Access remaining after termination | Investigate and remediate. |
| Processing Time | Delayed termination completion | Identify workflow bottleneck. |
| Exceptions | Open termination exceptions | Prioritize until closure. |

---

# End-to-End Leaver Scenario

## Scenario

A full-time employee leaves the organization following an approved termination event. The employee has standard SaaS access, cloud access, and limited administrative privileges.

| Attribute | Example Value |
|-----------|---------------|
| Employee Status | Terminated |
| Employment Type | Full-time |
| Department | Engineering |
| Business Role | Cloud Platform Engineer |
| Privileged Access | Limited |
| Cloud Access | Enabled before termination |
| SaaS Applications | Multiple |
| Termination Type | Standard termination |
| Termination Time | Approved termination time |

---

# End-to-End Processing

| Step | Action | Result |
|------|--------|--------|
| 1 | HR records termination. | Authoritative Leaver event generated. |
| 2 | IAM platform receives event. | Leaver workflow initiated. |
| 3 | Termination information validated. | Event passes validation. |
| 4 | Existing identity correlated. | Correct enterprise identity identified. |
| 5 | Revocation timing evaluated. | Approved termination time confirmed. |
| 6 | Active sessions revoked. | Existing sessions invalidated where supported. |
| 7 | Authentication access revoked. | New authentication blocked. |
| 8 | Directory account disabled. | Enterprise identity becomes inactive. |
| 9 | Cloud identity disabled. | Cloud authentication blocked. |
| 10 | Group memberships removed. | Group-based permissions revoked. |
| 11 | SaaS accounts deprovisioned. | Application access removed. |
| 12 | Cloud permissions revoked. | Cloud roles removed. |
| 13 | PAM access revoked. | Administrative access removed. |
| 14 | Relevant credentials handled. | Credentials rotated or secured as required. |
| 15 | Reconciliation executed. | Residual access identified and remediated. |
| 16 | Audit events recorded. | Complete termination evidence captured. |

---

# Leaver Completion Checklist

| Validation | Expected Result |
|------------|-----------------|
| HR Termination Event | Valid and authoritative |
| Identity Correlation | Correct identity identified |
| Active Sessions | Revoked where supported |
| Authentication | Access blocked |
| Directory Account | Disabled |
| Cloud Identity | Disabled |
| Group Memberships | Removed |
| Application Accounts | Disabled or removed |
| Cloud Roles | Revoked |
| Privileged Access | Revoked |
| PAM Sessions | Terminated where supported |
| Credentials | Rotated or secured where required |
| Residual Access | None identified |
| Reconciliation | Successful |
| Audit Trail | Complete |
| Lifecycle Status | Successfully completed |

---

# Roles and Responsibilities

The Leaver lifecycle requires coordination between HR, IAM, security, application owners, and privileged access teams.

| Role | Responsibility |
|------|----------------|
| HR | Maintains authoritative termination information. |
| IAM Operations | Executes identity disablement, access revocation, and exception handling. |
| IAM Engineering | Maintains lifecycle integrations, workflows, policies, and automation. |
| Manager | Confirms employee departure and coordinates business offboarding activities. |
| Application Owner | Ensures application access is revoked and required data ownership is transferred. |
| Security Team | Monitors security-sensitive terminations and investigates anomalies. |
| PAM Team | Revokes privileged access and administrative sessions. |
| Service Desk | Supports user and access-related offboarding issues. |
| Legal / Compliance | Provides guidance where regulatory, legal, or retention requirements apply. |

---

# Responsibility Matrix

| Activity | HR | IAM | Manager | App Owner | Security |
|----------|----|-----|---------|-----------|----------|
| Termination Record | R | I | C | I | I |
| Termination Validation | R | R | C | I | C |
| Identity Correlation | I | R | I | I | I |
| Identity Disablement | I | R | I | I | C |
| Application Deprovisioning | I | R | C | A | C |
| Privileged Access Revocation | I | C | I | C | A |
| Credential Handling | I | R | I | C | A |
| Residual Access Review | I | R | C | C | A |
| Exception Resolution | C | R | C | C | C |
| Audit Review | I | R | C | C | A |

**R = Responsible, A = Accountable, C = Consulted, I = Informed**

---

# Key Engineering Decisions

| Decision Area | Engineering Decision | Rationale |
|---------------|----------------------|-----------|
| Source of Authority | HR remains authoritative for termination events. | Prevents unauthorized lifecycle changes. |
| Revocation Timing | Access revocation follows defined termination policy. | Minimizes unauthorized access exposure. |
| Identity Disablement | Disable the existing identity rather than deleting it immediately. | Preserves auditability and supports controlled retention. |
| Session Revocation | Revoke active sessions where supported. | Limits continued access through existing sessions. |
| Application Deprovisioning | Automate account disablement and access removal. | Reduces residual access. |
| Privileged Access | Revoke privileged permissions through PAM controls. | Protects critical infrastructure. |
| Credential Handling | Rotate or revoke credentials and secrets where required. | Reduces credential exposure. |
| Reconciliation | Validate downstream systems after revocation. | Detects residual access. |
| Auditability | Preserve complete termination evidence. | Supports security investigations and compliance. |

---

# Key Performance Indicators

Leaver performance should be measured using security, operational, and governance metrics.

| KPI | Description | Target Direction |
|-----|-------------|------------------|
| Leaver Completion Rate | Percentage of termination workflows completed successfully. | Increase |
| Access Revocation Success Rate | Percentage of required access successfully revoked. | Increase |
| Revocation Time | Time between termination event and completion of access revocation. | Decrease |
| Residual Access Rate | Percentage of terminated identities with remaining access. | Decrease |
| Privileged Revocation Rate | Percentage of privileged access successfully revoked. | Increase |
| Application Deprovisioning Rate | Percentage of application accounts successfully disabled or removed. | Increase |
| Exception Rate | Percentage of Leaver events requiring manual intervention. | Decrease |
| Reconciliation Success Rate | Percentage of terminated identities matching expected final state. | Increase |
| Audit Completeness | Percentage of termination events with complete evidence. | Increase |

---

# Implementation Considerations

| Consideration | Engineering Requirement |
|---------------|-------------------------|
| Termination Events | Establish reliable event delivery from the authoritative HR platform. |
| Revocation Timing | Define precise policies for standard and immediate termination. |
| Identity Correlation | Maintain deterministic employee-to-identity matching. |
| Session Management | Integrate with identity providers capable of session/token revocation. |
| Directory Integration | Automate account disablement. |
| Application Integration | Standardize SCIM, API, or connector-based deprovisioning. |
| PAM Integration | Ensure privileged identities and sessions can be revoked rapidly. |
| Credential Management | Define handling requirements for credentials, API keys, and secrets. |
| Data Ownership | Define processes for transferring business-owned data and resources. |
| Exception Handling | Maintain visible operational queues for failed revocations. |
| Reconciliation | Validate identity state across connected systems. |
| Audit | Preserve lifecycle and access-revocation evidence. |
| Recovery | Support controlled recovery from partial workflow failures. |

---

# Leaver Control Model

The Leaver lifecycle can be represented as a controlled access-revocation pipeline.

| Layer | Responsibility | Example Control |
|-------|----------------|-----------------|
| Workforce Layer | Detect termination | HR termination event |
| Identity Layer | Identify affected identity | Identity correlation |
| Authentication Layer | Block authentication | Session and token revocation |
| Directory Layer | Disable enterprise account | Directory disablement |
| Authorization Layer | Remove permissions | Role and group removal |
| Application Layer | Deprovision applications | SCIM / API |
| Cloud Layer | Remove cloud permissions | Cloud role revocation |
| Privileged Layer | Remove administrative access | PAM |
| Credential Layer | Secure credentials and secrets | Rotation / revocation |
| Reconciliation Layer | Verify final state | Identity and access reconciliation |
| Audit Layer | Preserve evidence | Audit logging |

---

# Residual Access Detection

After the primary Leaver workflow completes, the identity should be checked for access that may remain outside the standard provisioning path.

| Residual Access Area | Detection Method | Remediation |
|----------------------|------------------|------------|
| Directory Groups | Group membership query | Remove membership |
| SaaS Applications | Application account inventory | Disable or remove account |
| Cloud Roles | Cloud IAM inventory | Remove role assignment |
| PAM Accounts | PAM inventory | Disable privileged identity |
| API Tokens | Token inventory | Revoke tokens |
| Service Ownership | Application ownership review | Transfer ownership |
| Certificates | Certificate inventory | Revoke or replace where required |
| Shared Resources | Resource ownership review | Transfer ownership |

---

# Engineering Outcome

A successfully implemented Leaver lifecycle should ensure that a departing workforce member no longer retains unauthorized access to enterprise resources.

| Outcome | Expected State |
|---------|----------------|
| Identity | Correct identity identified and disabled. |
| Authentication | Authentication access revoked. |
| Sessions | Active sessions terminated where supported. |
| Applications | Application accounts deprovisioned. |
| Authorization | Roles, groups, and permissions removed. |
| Cloud | Cloud access and permissions revoked. |
| Privileged Access | Administrative access removed. |
| Credentials | Relevant credentials and secrets secured. |
| Residual Access | No unauthorized access remains. |
| Audit | Complete termination evidence exists. |
| Operations | Exceptions are visible and actionable. |

---

# Related Architecture References

| Reference | Relationship to Leaver Lifecycle |
|-----------|----------------------------------|
| Enterprise IAM Reference Architecture | Defines the overall enterprise identity platform. |
| Identity Lifecycle Reference Architecture | Defines Joiner, Mover, and Leaver lifecycle principles. |
| Authentication Architecture | Defines authentication and session controls. |
| Authorization Architecture | Defines authorization and permission enforcement. |
| Access Governance Architecture | Defines access governance and certification. |
| RBAC Model | Defines role and permission management. |
| SCIM Provisioning Architecture | Defines application provisioning and deprovisioning. |
| PAM Architecture | Defines privileged access revocation and management. |
| Zero Trust Identity | Defines continuous identity security controls. |
| Hybrid Identity Reference | Defines identity synchronization across hybrid environments. |

---

# Summary

The Enterprise Leaver Identity Lifecycle provides a standardized and auditable approach for removing access when workforce members leave the organization.

The lifecycle combines authoritative termination events, authentication revocation, identity disablement, application deprovisioning, privileged access removal, credential handling, residual access detection, reconciliation, and audit controls.

The resulting process reduces the risk of orphaned accounts, residual permissions, active sessions, and unmanaged privileged access while providing a consistent enterprise offboarding model.

---

# Document Information

| Property | Value |
|----------|-------|
| Document Type | Enterprise IAM Example |
| Domain | Identity & Access Management |
| Repository | identity-platform |
| Example Category | Leaver |
| Architecture Relationship | Identity Lifecycle |
| Version | 1.0 |
| Status | Reference Implementation |
| Classification | Public Reference Architecture |
| Maintainer | Rohit Yallaling |
| Last Updated | August 2026 |
