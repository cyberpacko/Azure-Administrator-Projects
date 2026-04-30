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

## Objectives
Enforce least‑privilege access across Azure resources

Centralize identity and access governance

Implement Multi‑Factor Authentication (MFA) and Conditional Access

Introduce Privileged Identity Management (PIM) for just‑in‑time access

Standardize RBAC assignments using built‑in and custom roles

Improve auditability and compliance

## Architecture Components
### Azure Services Used
Azure Entra ID (Identity & Access Management)

Azure Management Groups (Hierarchy & Governance)

Azure Privileged Identity Management (PIM)

Azure Activity Log (Auditing & Monitoring)

### Technologies
Azure Portal

Azure CLI

PowerShell

Bicep (optional IaC implementation)

## Implementation Steps


## Features

- Azure Entra ID tenant configuration (users, groups, dynamic membership)
- RBAC assignments with built-in and custom roles
- Custom RBAC role definition via JSON
- MFA and Conditional Access policy templates
- Privileged Identity Management (PIM) configuration
- Management Group hierarchy and policy assignments
- RBAC audit log export

See `docs/` for detailed design and governance documentation.
