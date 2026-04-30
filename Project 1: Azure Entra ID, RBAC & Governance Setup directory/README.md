# Azure Entra ID RBAC & Governance Configuration

## Overview
This project focuses on designing and implementing a secure, least‑privilege identity and access management model for a fictional organization migrating to Microsoft Azure. The goal is to configure Azure Entra ID (formerly Azure Active Directory), RBAC, and governance controls to ensure that users, groups, and administrators have only the permissions required to perform their duties.

The solution enforces enterprise‑grade security, role‑based access control, conditional access, and just‑in‑time privileged access across Azure subscriptions and resource groups.

## Business Problem
The fictional company is experiencing:

Excessive administrative permissions across teams

No centralized governance for Azure resources

Inconsistent access assignments across subscriptions

Lack of auditing and visibility into RBAC changes

No MFA or Conditional Access enforcement

No lifecycle management for privileged roles

This project resolves these issues by implementing a structured, secure, and auditable identity governance model using Azure Entra ID and Azure RBAC.

Objectives
Enforce least‑privilege access across Azure resources

Centralize identity and access governance

Implement Multi‑Factor Authentication (MFA) and Conditional Access

Introduce Privileged Identity Management (PIM) for just‑in‑time access

Standardize RBAC assignments using built‑in and custom roles

Improve auditability and compliance

Architecture Components
Azure Services Used
Azure Entra ID (Identity & Access Management)

Azure Management Groups (Hierarchy & Governance)

Azure Privileged Identity Management (PIM)

Azure Activity Log (Auditing & Monitoring)

Technologies
Azure Portal

Azure CLI

PowerShell

Bicep (optional IaC implementation)

Implementation Steps
1. Create a New Azure Entra ID Tenant
Deploy a new tenant for the fictional organization

Configure a custom domain (e.g., contoso-cloud.com)

Verify domain ownership via DNS

2. Create Users, Groups & Dynamic Membership
Add standard and administrative user accounts

Create security groups for role‑based access

Implement dynamic membership rules (e.g., department‑based auto‑assignment)

Example dynamic rule:

Code
(user.department -eq "Finance")
3. Assign Built‑In RBAC Roles
Assign roles at subscription and resource group scope:

Owner

Contributor

Reader

Assignments follow the least‑privilege model and are applied to groups, not individuals.

4. Create a Custom RBAC Role
Define a custom role using a JSON template with specific permissions.

Example permissions included:

Read‑only access to storage accounts

Ability to list keys but not regenerate them

No write or delete permissions

The custom role is deployed using:

Azure Portal

Azure CLI (az role definition create)

PowerShell (New-AzRoleDefinition)

5. Configure MFA & Conditional Access
Enforce strong authentication:

Require MFA for all users

Block legacy authentication

Apply Conditional Access policies such as:

Require MFA for admin roles

Require compliant device for resource access

Restrict access from risky sign‑ins

6. Enable Privileged Identity Management (PIM)
Configure PIM for just‑in‑time access:

Require approval for role activation

Enforce MFA on activation

Set activation time limits

Enable access reviews for privileged roles

Roles managed through PIM:

Global Administrator

User Administrator

Owner / Contributor roles

7. Set Up Management Groups
Create a hierarchical structure:

Code
Root Management Group
│
├── Corp
│   ├── Production
│   └── Non‑Production
└── Sandbox
Assign policies at the management group level, such as:

Enforce MFA

Restrict resource locations

Enforce tagging standards

Deny public IP creation

8. Review & Export RBAC Audit Logs
Use Azure Activity Log to:

Review RBAC changes

Track role assignments

Export logs to CSV or Log Analytics

Validate compliance with governance policies

Expected Outcomes
By completing this project, the fictional company achieves:

A secure and compliant Azure identity environment

Consistent RBAC assignments aligned with least‑privilege principles

Centralized governance using management groups

Strong authentication and conditional access enforcement

Auditable and monitored privileged access

Reduced risk of unauthorized access or privilege escalation

Future Enhancements
Automate RBAC assignments using Bicep or Terraform

Implement Access Reviews for all privileged roles

Integrate with Microsoft Defender for Cloud

Deploy a full Identity Governance solution (Lifecycle Workflows, Entitlement Ma

This repository contains scripts and templates to configure Azure Entra ID (formerly Azure AD), RBAC, and governance for a fictional organization. It focuses on enforcing least-privilege access, just-in-time privileged roles, and centralized management using Management Groups and policies.

## Features

- Azure Entra ID tenant configuration (users, groups, dynamic membership)
- RBAC assignments with built-in and custom roles
- Custom RBAC role definition via JSON
- MFA and Conditional Access policy templates
- Privileged Identity Management (PIM) configuration
- Management Group hierarchy and policy assignments
- RBAC audit log export

See `docs/` for detailed design and governance documentation.
