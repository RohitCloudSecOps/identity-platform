# Enterprise Mover Identity Lifecycle

## Executive Summary

The Enterprise Mover Identity Lifecycle defines the standardized process for managing identity and access changes when an existing employee changes organizational attributes, responsibilities, role, department, location, manager, or employment conditions.

The Mover process ensures that access remains aligned with the employee's current business responsibilities while removing access that is no longer required.

The lifecycle combines authoritative workforce events, identity attribute synchronization, role recalculation, access governance, provisioning, deprovisioning, and audit controls.

---

# Business Scenario

An existing employee moves from one business role or organizational context to another and requires corresponding changes to enterprise access.

| Requirement | Expected Outcome |
|-------------|------------------|
| Identity Continuity | Existing enterprise identity remains associated with the employee. |
| Attribute Update | New organizational attributes are synchronized. |
| Role Recalculation | Access is recalculated based on the new role. |
| Access Removal | Access no longer required is removed. |
| New Access | Required access for the new role is provisioned. |
| Least Privilege | Access reflects current business responsibilities. |
| Governance | Sensitive access follows approval policies. |
| Auditability | All access changes are recorded. |

---

# Mover Event Sources

The Mover lifecycle should originate from an authoritative workforce event.

| Source | Example Event | Identity Impact |
|--------|---------------|-----------------|
| HR System | Department change | Recalculate role and access |
| HR System | Job title change | Recalculate role mapping |
| HR System | Manager change | Update approval relationships |
| HR System | Location change | Re-evaluate regional access |
| HR System | Employment type change | Re-evaluate applicable policies |
| HR System | Business unit change | Recalculate organizational access |
| Identity Governance | Approved role change | Update access assignments |
| Manager Workflow | Approved responsibility change | Trigger controlled access update |

---

# Mover Identity Attributes

| Attribute | Purpose |
|-----------|---------|
| Employee ID | Maintains identity correlation. |
| Department | Determines organizational access. |
| Job Title | Supports role mapping. |
| Business Role | Determines functional access. |
| Manager | Updates approval relationships. |
| Location | Supports regional access policies. |
| Employment Type | Determines applicable lifecycle policies. |
| Employment Status | Confirms identity remains active. |
| Business Unit | Supports organizational authorization. |
| Cost Center | Supports application and financial access policies. |

---

# Mover Lifecycle Workflow

```text
HR / Workforce Change
        │
        ▼
Identity Change Detection
        │
        ▼
Attribute Validation
        │
        ▼
Current Access Assessment
        │
        ▼
New Role Evaluation
        │
        ▼
Access Recalculation
        │
        ├───────────────┐
        ▼               ▼
Remove Old Access   Request New Access
        │               │
        └───────┬───────┘
                ▼
        Provision Approved Access
                │
                ▼
        Validate Final State
                │
                ▼
           Audit & Monitoring
```

---

# Mover Processing Stages

| Stage | Process | Expected Result |
|-------|---------|-----------------|
| 1 | Receive workforce change | Authoritative Mover event generated. |
| 2 | Validate changed attributes | New identity information is valid. |
| 3 | Correlate identity | Existing identity is identified. |
| 4 | Capture current access | Existing access state is established. |
| 5 | Determine new role | Target role is identified. |
| 6 | Recalculate access | Required and obsolete access are identified. |
| 7 | Remove obsolete access | Access no longer required is revoked. |
| 8 | Evaluate new access | New access is classified by policy. |
| 9 | Provision approved access | Required access is provisioned. |
| 10 | Validate final state | Identity matches target role. |
| 11 | Record audit events | Complete change history is captured. |

---

# Before-and-After Access Model

| Access Category | Before Move | After Move | Action |
|----------------|-------------|------------|--------|
| Corporate Email | Required | Required | Retain |
| Collaboration | Required | Required | Retain |
| Previous Department Application | Required | Not Required | Remove |
| New Department Application | Not Required | Required | Provision |
| Previous Role Group | Assigned | Not Required | Remove |
| New Role Group | Not Assigned | Required | Assign |
| Privileged Access | Existing | Re-evaluate | Review |
| Sensitive Application | Existing | May Change | Re-certify if required |

---

# Access Recalculation Model

The Mover process should compare the employee's current access against the access required by the new business role.

| Evaluation | Description |
|------------|-------------|
| Current Role | Identify existing business role. |
| Target Role | Determine new business role. |
| Current Access | Establish currently assigned permissions. |
| Required Access | Determine access required by the new role. |
| Excess Access | Identify permissions no longer required. |
| Missing Access | Identify permissions required by the new role. |
| Sensitive Access | Identify access requiring approval. |
| Privileged Access | Re-evaluate elevated permissions. |

---

# Role Transition Model

| Transition Type | Example | Primary Access Action |
|----------------|---------|-----------------------|
| Department Transfer | Finance → Engineering | Remove old department access and assign engineering access. |
| Job Role Change | Developer → Engineering Manager | Recalculate role-based permissions. |
| Location Change | India → United States | Re-evaluate regional access. |
| Business Unit Change | Product → Security | Recalculate organizational access. |
| Manager Change | Manager A → Manager B | Update approval relationships. |
| Employment Type Change | Contractor → Employee | Re-evaluate lifecycle policies. |
| Temporary Assignment | Engineering → Project Team | Add approved temporary access. |

---

# Mover Security Controls

| Security Control | Description | Objective |
|------------------|-------------|-----------|
| Identity Correlation | Ensure the change applies to the correct identity. | Prevent unauthorized modifications. |
| Attribute Validation | Validate changed workforce attributes. | Maintain identity accuracy. |
| Access Recalculation | Compare current and required access. | Prevent privilege accumulation. |
| Old Access Removal | Remove permissions no longer required. | Enforce least privilege. |
| New Access Approval | Require approval for sensitive access. | Strengthen governance. |
| Privileged Access Review | Re-evaluate administrative permissions. | Protect privileged resources. |
| Audit Logging | Record access changes. | Support investigation and compliance. |
| Reconciliation | Validate final downstream state. | Detect provisioning inconsistencies. |

---

# Mover Success Criteria

| Validation Area | Success Condition |
|----------------|-------------------|
| Identity | Existing identity remains correctly correlated. |
| Attributes | New organizational information is synchronized. |
| Old Access | Unnecessary access is removed. |
| New Access | Required access is provisioned. |
| Role | Identity reflects the new business role. |
| Privileged Access | Administrative access is appropriately re-evaluated. |
| Authentication | Authentication state remains valid. |
| Authorization | Permissions match the target role. |
| Audit | All changes are recorded. |
| Reconciliation | Downstream systems reflect the expected state. |

---

# Approval and Governance Model

Access changes during a Mover event should be evaluated according to business risk and the sensitivity of the requested resources.

| Access Category | Action | Approval Requirement |
|----------------|--------|----------------------|
| Existing Birthright Access | Re-evaluate against new role | Policy-driven |
| New Standard Access | Provision according to role | Policy-driven |
| Sensitive Application | Provision new access | Application owner / manager approval |
| Privileged Access | Re-evaluate elevated permissions | Explicit approval |
| Production Access | Re-evaluate and provision | Strong approval |
| Temporary Project Access | Add for defined duration | Business owner approval |
| Previous Role Access | Remove when no longer required | Automated policy where possible |

---

# Mover Processing Sequence

The sequence should ensure obsolete access is identified and removed while required new access is provisioned in a controlled manner.

| Sequence | Action | Dependency |
|----------|--------|------------|
| 1 | Receive Mover event | Authoritative workforce change exists |
| 2 | Validate changed attributes | Required data is available |
| 3 | Correlate existing identity | Existing identity must be identified |
| 4 | Capture current access | Current authorization state is available |
| 5 | Determine target role | New business role is established |
| 6 | Calculate access delta | Required and obsolete permissions identified |
| 7 | Remove obsolete access | Old access is no longer required |
| 8 | Evaluate new access | New access classified by policy |
| 9 | Obtain approvals | Required approvals completed |
| 10 | Provision new access | Approved permissions assigned |
| 11 | Validate final state | Access matches target role |
| 12 | Record audit events | Complete transition evidence captured |

---

# Access Delta Model

The Mover process should calculate the difference between current access and target access.

| Access State | Definition | Action |
|--------------|------------|--------|
| Retain | Access required by both old and new roles | Keep access |
| Remove | Access exists but is not required by new role | Revoke access |
| Add | Access required by new role but not currently assigned | Provision access |
| Review | Sensitive or privileged access requiring evaluation | Route through governance |
| Temporary | Access required for a limited project or assignment | Assign with expiration |

---

# Provisioning and Deprovisioning

A Mover event is both an access removal and access provisioning process.

| Operation | Example | Expected Result |
|-----------|---------|-----------------|
| Group Removal | Remove previous department group | Old access revoked |
| Role Removal | Remove previous business role | Previous permissions removed |
| Application Deprovisioning | Disable obsolete application account | Unnecessary account removed |
| Group Assignment | Assign new department group | New access granted |
| Application Provisioning | Create new application account | Required application available |
| Role Assignment | Assign target business role | New permissions applied |
| Privileged Access Review | Re-evaluate administrative access | Excess privilege prevented |

---

# Provisioning Error Handling

| Failure | Potential Cause | Recommended Action |
|--------|-----------------|--------------------|
| Missing Change Attribute | Incomplete HR event | Hold workflow and correct source data. |
| Identity Correlation Failure | Existing identity cannot be identified | Stop processing and investigate identity correlation. |
| Role Mapping Failure | Target role cannot be determined | Route to IAM exception queue. |
| Old Access Removal Failure | Connector or target system issue | Retry removal and monitor exception. |
| New Access Provisioning Failure | Connector or application issue | Retry provisioning and create exception if unresolved. |
| Approval Timeout | Required approver unavailable | Escalate according to governance policy. |
| Reconciliation Failure | Target state differs from expected state | Reconcile and remediate affected accounts. |
| Partial Completion | Some systems updated while others failed | Maintain transaction state and complete controlled recovery. |

---

# Exception Management

Mover exceptions should be tracked and assigned to accountable teams.

| Exception | Handling | Owner |
|-----------|----------|-------|
| Invalid HR Data | Correct authoritative employee information. | HR |
| Unknown Target Role | Validate business role mapping. | IAM / Manager |
| Excess Access Detected | Investigate and remove unnecessary access. | IAM |
| Failed Application Removal | Retry or coordinate with application owner. | IAM / Application Team |
| Failed New Provisioning | Retry connector operation. | IAM Operations |
| Privileged Access Conflict | Route through PAM governance. | PAM / Security |
| Approval Delay | Escalate according to approval policy. | Manager / Application Owner |
| Reconciliation Failure | Compare target and expected identity state. | IAM Operations |

---

# Audit Events

| Event | Audit Information |
|-------|-------------------|
| Mover Event Received | Employee ID, source, timestamp |
| Identity Correlated | Identity identifier and correlation result |
| Attribute Changed | Previous and new attribute values according to audit policy |
| Role Recalculated | Previous role, target role |
| Access Removed | Application, group, role, timestamp |
| Access Requested | Resource, requester, justification |
| Access Approved | Approver, timestamp, decision |
| Access Provisioned | Target system, account, permission |
| Privileged Access Reviewed | Privilege, decision, approver |
| Reconciliation Completed | Expected state and actual state |
| Mover Completed | Overall lifecycle result |

---

# Operational Monitoring

| Monitoring Area | Indicator | Operational Response |
|----------------|-----------|----------------------|
| Mover Events | Pending events | Investigate workflow processing. |
| Attribute Changes | Invalid or incomplete data | Coordinate with HR. |
| Access Removal | Failed revocations | Retry and escalate unresolved failures. |
| New Provisioning | Failed assignments | Investigate connector or application issue. |
| Approval Queue | Aging requests | Escalate pending approvals. |
| Privileged Access | Unexpected elevated permissions | Investigate immediately. |
| Reconciliation | Identity state mismatch | Correct downstream systems. |
| Processing Time | Excessive transition duration | Identify workflow bottlenecks. |
| Exceptions | Growing exception volume | Perform root-cause analysis. |

---

# End-to-End Mover Scenario

## Scenario

A software engineer transfers from the **Application Engineering** department to the **Cloud Platform Engineering** department.

The employee remains active but requires a different set of application and infrastructure permissions.

| Attribute | Before Move | After Move |
|-----------|-------------|------------|
| Employee Status | Active | Active |
| Department | Application Engineering | Cloud Platform Engineering |
| Job Function | Software Engineer | Cloud Platform Engineer |
| Manager | Engineering Manager A | Engineering Manager B |
| Business Role | Application Engineer | Cloud Platform Engineer |
| Location | India | India |
| Employment Type | Full-time | Full-time |

---

# End-to-End Processing

| Step | Action | Result |
|------|--------|--------|
| 1 | HR updates employee department and role. | Authoritative Mover event generated. |
| 2 | IAM platform receives event. | Mover workflow initiated. |
| 3 | Changed attributes validated. | New organizational data confirmed. |
| 4 | Existing identity correlated. | Existing identity retained. |
| 5 | Current access collected. | Existing authorization state established. |
| 6 | Target role calculated. | Cloud Platform Engineer role identified. |
| 7 | Access delta calculated. | Retain, remove, add, and review permissions identified. |
| 8 | Previous application access evaluated. | Obsolete access identified for removal. |
| 9 | Cloud platform access evaluated. | Required access identified. |
| 10 | Sensitive access routed for approval. | Governance workflow completed. |
| 11 | Previous role groups removed. | Obsolete permissions revoked. |
| 12 | New role groups assigned. | Required permissions provisioned. |
| 13 | Application accounts updated. | Target systems reflect new role. |
| 14 | Privileged access reviewed. | Administrative permissions aligned with new role. |
| 15 | Final state validated. | Identity matches target role. |
| 16 | Audit events recorded. | Complete transition history available. |

---

# Mover Completion Checklist

| Validation | Expected Result |
|------------|-----------------|
| Workforce Event | Valid authoritative change received |
| Identity Correlation | Existing identity correctly identified |
| Attributes | New organizational information synchronized |
| Current Access | Existing authorization state captured |
| Access Delta | Retain, remove, add, and review states calculated |
| Old Access | Unnecessary permissions removed |
| New Access | Required permissions provisioned |
| Sensitive Access | Required approvals completed |
| Privileged Access | Re-evaluated through PAM controls |
| Authentication | Identity remains appropriately protected |
| Authorization | Permissions match target role |
| Reconciliation | Downstream systems match expected state |
| Audit Trail | Complete lifecycle evidence available |
| Lifecycle Status | Mover workflow successfully completed |


---

# Roles and Responsibilities

The Mover lifecycle requires coordination between HR, IAM, managers, application owners, and security teams.

| Role | Responsibility |
|------|----------------|
| HR | Maintains authoritative organizational and employment information. |
| IAM Operations | Executes lifecycle workflows and resolves provisioning exceptions. |
| IAM Engineering | Maintains identity integrations, role mappings, policies, and automation. |
| Manager | Confirms the employee's new business responsibilities and access requirements. |
| Application Owner | Governs application-specific access and approves sensitive permissions. |
| Security Team | Defines security controls and reviews security-sensitive access changes. |
| PAM Team | Re-evaluates and controls privileged access. |
| Service Desk | Supports authentication and access-related user issues. |
| Employee | Uses access according to organizational security policies. |

---

# Responsibility Matrix

| Activity | HR | IAM | Manager | App Owner | Security |
|----------|----|-----|---------|-----------|----------|
| Workforce Change | R | I | C | I | I |
| Identity Correlation | I | R | I | I | I |
| Attribute Update | R | R | C | I | I |
| Access Recalculation | C | R | C | C | C |
| Old Access Removal | I | R | C | C | C |
| New Standard Access | I | R | A | C | I |
| Sensitive Access | I | C | A | A | C |
| Privileged Access | I | C | A | C | R |
| Exception Resolution | C | R | C | C | C |
| Reconciliation | I | R | I | C | C |
| Audit Review | I | R | C | C | A |

**R = Responsible, A = Accountable, C = Consulted, I = Informed**

---

# Key Engineering Decisions

| Decision Area | Engineering Decision | Rationale |
|---------------|----------------------|-----------|
| Identity Continuity | Maintain the existing enterprise identity during role changes. | Prevents unnecessary duplicate identities. |
| Source of Authority | Workforce changes originate from the authoritative HR system. | Establishes clear ownership of identity attributes. |
| Access Recalculation | Calculate access differences between current and target roles. | Prevents privilege accumulation. |
| Old Access Removal | Remove access that is no longer required. | Enforces least privilege. |
| New Access | Provision only policy-approved access. | Prevents uncontrolled access assignment. |
| Sensitive Access | Require explicit approval for sensitive resources. | Strengthens governance. |
| Privileged Access | Re-evaluate administrative permissions during role changes. | Prevents inappropriate privilege retention. |
| Automation | Automate standard access changes wherever possible. | Reduces manual operational effort. |
| Reconciliation | Validate the final state across connected systems. | Detects synchronization inconsistencies. |
| Auditability | Record before-and-after access decisions. | Supports governance and investigations. |

---

# Key Performance Indicators

Mover lifecycle performance should be measured using operational, security, and governance metrics.

| KPI | Description | Target Direction |
|-----|-------------|------------------|
| Mover Completion Rate | Percentage of Mover workflows completed successfully. | Increase |
| Access Removal Success Rate | Percentage of obsolete access successfully revoked. | Increase |
| New Access Provisioning Rate | Percentage of required access successfully provisioned. | Increase |
| Excess Access Rate | Percentage of users retaining access no longer required. | Decrease |
| Mover Processing Time | Time required to complete a role transition. | Decrease |
| Exception Rate | Percentage of Mover events requiring manual intervention. | Decrease |
| Privileged Access Exceptions | Number of inappropriate privileged permissions identified. | Decrease |
| Reconciliation Success Rate | Percentage of transitions matching expected final state. | Increase |
| Audit Completeness | Percentage of changes with complete audit evidence. | Increase |

---

# Implementation Considerations

| Consideration | Engineering Requirement |
|---------------|-------------------------|
| Change Detection | Establish reliable event delivery from the authoritative HR system. |
| Identity Correlation | Maintain deterministic employee-to-identity matching. |
| Role Mapping | Define controlled mappings between business roles and technical access. |
| Access Delta | Implement a reliable mechanism for calculating retained, removed, added, and reviewed access. |
| Deprovisioning | Ensure obsolete access can be revoked automatically. |
| Provisioning | Standardize SCIM, API, or connector-based provisioning. |
| Approval Workflow | Route sensitive access through appropriate governance controls. |
| Privileged Access | Integrate with PAM for administrative permissions. |
| Reconciliation | Validate final identity and access state across target systems. |
| Exception Handling | Maintain operational queues and ownership. |
| Audit | Preserve evidence of access changes and decisions. |
| Recovery | Support controlled recovery from partial provisioning failures. |

---

# Access Transition Control Model

The Mover lifecycle can be represented as a controlled access-delta process.

| Layer | Responsibility | Example Control |
|-------|----------------|-----------------|
| Workforce Layer | Detect organizational change | HR event |
| Identity Layer | Maintain identity continuity | Identity correlation |
| Attribute Layer | Update organizational information | Attribute synchronization |
| Role Layer | Determine target business role | Role mapping |
| Access Analysis Layer | Compare current and target access | Access delta |
| Governance Layer | Approve sensitive access | Access request workflow |
| Deprovisioning Layer | Remove obsolete access | Automated revocation |
| Provisioning Layer | Add required access | SCIM / API |
| Privileged Layer | Re-evaluate elevated permissions | PAM |
| Audit Layer | Record transition evidence | Audit logging |

---

# Engineering Outcome

A successfully implemented Mover lifecycle should ensure that an employee's access continuously reflects their current business responsibilities.

| Outcome | Expected State |
|---------|----------------|
| Identity | Existing identity remains correctly correlated. |
| Attributes | Current organizational information is synchronized. |
| Role | Target business role is correctly determined. |
| Old Access | Unnecessary permissions are removed. |
| New Access | Required permissions are provisioned. |
| Sensitive Access | Appropriate approvals are completed. |
| Privileged Access | Administrative permissions are re-evaluated. |
| Least Privilege | No unnecessary access remains. |
| Applications | Connected systems reflect the target role. |
| Audit | Complete before-and-after evidence exists. |
| Operations | Exceptions are visible and actionable. |

---

# Related Architecture References

| Reference | Relationship to Mover Lifecycle |
|-----------|----------------------------------|
| Enterprise IAM Reference Architecture | Defines the overall identity platform. |
| Identity Lifecycle Reference Architecture | Defines Joiner, Mover, and Leaver principles. |
| Authentication Architecture | Defines authentication and identity verification controls. |
| Authorization Architecture | Defines authorization decisions and access enforcement. |
| Access Governance Architecture | Defines access requests, approvals, and certification. |
| RBAC Model | Defines role-based access assignment and role transitions. |
| SCIM Provisioning Architecture | Defines automated application provisioning and deprovisioning. |
| PAM Architecture | Defines privileged access controls. |
| Zero Trust Identity | Defines continuous identity and access security. |
| Hybrid Identity Reference | Defines identity synchronization across hybrid environments. |

---

# Summary

The Enterprise Mover Identity Lifecycle provides a standardized approach for managing identity and access changes when workforce members change roles, departments, locations, responsibilities, or employment conditions.

The lifecycle maintains identity continuity while recalculating access based on the employee's new business context.

By combining access-delta analysis, automated deprovisioning, controlled provisioning, governance approvals, privileged access review, reconciliation, and audit controls, the Mover process reduces privilege accumulation and maintains alignment between business responsibilities and technical access.

---

# Document Information

| Property | Value |
|----------|-------|
| Document Type | Enterprise IAM Example |
| Domain | Identity & Access Management |
| Repository | identity-platform |
| Example Category | Mover |
| Architecture Relationship | Identity Lifecycle |
| Version | 1.0 |
| Status | Reference Implementation |
| Classification | Public Reference Architecture |
| Maintainer | Rohit Yallaling |
| Last Updated | August 2026 |
