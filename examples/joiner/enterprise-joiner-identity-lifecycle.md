# Enterprise Joiner Identity Lifecycle

## Executive Summary

The Enterprise Joiner Identity Lifecycle defines the standardized process for creating and enabling digital identities when a new employee, contractor, or workforce member joins the organization.

The process begins with an authoritative workforce event and continues through identity creation, attribute synchronization, account provisioning, birthright access assignment, authentication enrollment, application access, and audit validation.

The objective is to provide the right identity and appropriate access at the right time while maintaining security, governance, and operational consistency.

---

# Business Scenario

A new employee joins the organization and requires access to enterprise systems based on their employment status, department, job function, location, and assigned responsibilities.

The Joiner process must ensure that:

| Requirement | Expected Outcome |
|-------------|------------------|
| Identity Creation | A unique enterprise identity is created. |
| Identity Accuracy | Attributes originate from an authoritative source. |
| Authentication | The user can securely authenticate. |
| Birthright Access | Standard access is automatically assigned according to policy. |
| Application Access | Required applications are provisioned. |
| Least Privilege | Only approved access is granted. |
| Governance | Sensitive access follows approval requirements. |
| Auditability | All lifecycle activities are recorded. |

---

# Source of Authority

The Joiner lifecycle should begin from an authoritative workforce system.

| System | Responsibility |
|--------|----------------|
| HR System | Creates the employee record and provides authoritative workforce attributes. |
| Identity Governance Platform | Applies lifecycle and access governance policies. |
| Enterprise Directory | Creates and maintains the enterprise identity. |
| Cloud Identity Provider | Provides cloud authentication and identity services. |
| Provisioning Platform | Synchronizes identities with connected applications. |
| Target Applications | Receive and maintain application accounts. |
| SIEM / Audit Platform | Records security and lifecycle events. |

---

# Joiner Identity Attributes

The following attributes are commonly used to establish and correlate the enterprise identity.

| Attribute | Purpose |
|-----------|---------|
| Employee ID | Unique workforce identifier. |
| First Name | User identity information. |
| Last Name | User identity information. |
| Display Name | Enterprise directory presentation. |
| Corporate Email | Primary communication and authentication identifier. |
| Department | Determines organizational context and access policies. |
| Job Title | Supports role and access determination. |
| Manager | Supports approval and governance workflows. |
| Location | Supports regional and application policies. |
| Employment Type | Determines applicable lifecycle policies. |
| Employment Status | Determines whether the identity should be active. |
| Start Date | Determines when identity activation should occur. |

---

# Joiner Lifecycle Workflow

```text
HR Employee Record
        │
        ▼
Identity Validation
        │
        ▼
Identity Creation
        │
        ▼
Directory Synchronization
        │
        ▼
Cloud Identity Creation
        │
        ▼
Birthright Access
        │
        ▼
Application Provisioning
        │
        ▼
Authentication Enrollment
        │
        ▼
Access Verification
        │
        ▼
Audit & Monitoring
```

---

# Joiner Processing Stages

| Stage | Process | Expected Result |
|-------|---------|-----------------|
| 1 | HR record creation | Authoritative employee record exists. |
| 2 | Identity validation | Required attributes are validated. |
| 3 | Identity correlation | Existing duplicate identity is checked. |
| 4 | Enterprise identity creation | Unique identity is created. |
| 5 | Directory provisioning | Account is created in the enterprise directory. |
| 6 | Cloud synchronization | Cloud identity is created or synchronized. |
| 7 | Birthright access evaluation | Standard access is determined. |
| 8 | Application provisioning | Approved application accounts are created. |
| 9 | Authentication enrollment | Required authentication methods are registered. |
| 10 | Verification | Identity and access are validated. |
| 11 | Audit logging | Lifecycle events are recorded. |

---

# Birthright Access Model

Birthright access represents the baseline access automatically assigned according to predefined enterprise policies.

| Attribute | Example Policy |
|-----------|----------------|
| Employee Status | Active employee |
| Department | Engineering |
| Employment Type | Full-time |
| Location | India |
| Job Function | Engineering |
| Baseline Access | Corporate email, collaboration platform, endpoint services |
| Additional Access | Requires role-based assignment or approval |

Birthright access should remain limited to services required for standard workforce operation.

---

# Identity Creation Controls

| Control | Description | Purpose |
|---------|-------------|---------|
| Unique Identity | Ensure each workforce member receives a unique identity. | Prevent duplicate identities. |
| Attribute Validation | Validate required HR attributes. | Maintain identity data quality. |
| Identity Correlation | Check existing identities before creation. | Prevent duplicate accounts. |
| Naming Standard | Apply enterprise username and email conventions. | Maintain consistency. |
| Lifecycle Status | Set identity status based on employment state. | Prevent premature access. |
| Start-Date Control | Align activation with approved start date. | Prevent early access. |

---

# Application Provisioning Model

| Application Category | Provisioning Method | Governance |
|---------------------|----------------------|------------|
| Corporate Email | Automated provisioning | Birthright |
| Collaboration Platform | Automated provisioning | Birthright |
| Service Management | SCIM / API | Role-based |
| Source Control | SCIM / API | Role-based |
| Cloud Platform | Identity federation / provisioning | Approval-based |
| Production Systems | PAM / privileged workflow | Strong approval |
| Business Applications | SCIM / connector | Role-based |
| Sensitive Applications | Governance workflow | Explicit approval |

---

# Joiner Access Decision

The final access assignment should be based on identity attributes, business role, and enterprise policies.

| Decision Input | Example |
|----------------|---------|
| Employment Status | Active |
| Department | Engineering |
| Job Function | Software Engineering |
| Location | India |
| Employment Type | Full-time |
| Business Role | Software Engineer |
| Application Sensitivity | Standard / Sensitive |
| Privilege Level | Standard |
| Approval Requirement | Based on application policy |

---

# Success Criteria

| Validation Area | Success Condition |
|----------------|-------------------|
| Identity | Unique enterprise identity exists. |
| Directory | Directory account is active according to lifecycle policy. |
| Cloud Identity | Cloud identity is synchronized successfully. |
| Authentication | Required authentication methods are enrolled. |
| Birthright Access | Baseline access is assigned correctly. |
| Applications | Required application accounts are provisioned. |
| Authorization | Permissions match approved roles. |
| Security | No unauthorized privileged access exists. |
| Audit | Lifecycle events are captured successfully. |
