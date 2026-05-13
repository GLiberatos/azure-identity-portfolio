# Azure Tagging Standard

## Purpose

This document defines the tagging standard I will use for Azure resources in my portfolio lab environment.

Tags help add business and operational context to Azure resources.

A tagging standard helps support:

- Cost tracking
- Resource ownership
- Cleanup
- Governance
- Security classification
- Automation
- Documentation

## What Are Azure Tags?

Azure tags are metadata values assigned to Azure resources.

Tags use a key-value format.

Example:

```text
Environment = Lab
```

In this example:

| Part        | Meaning        |
| ----------- | -------------- |
| Environment | Tag name / key |
| Lab         | Tag value      |

## Why Tags Matter

Without tags, Azure resources can become difficult to manage as the environment grows.

Tags help answer questions such as:

- Who owns this resource?
- What project does this resource belong to?
- Is this resource for lab, development, testing, or production?
- Is this resource temporary?
- When should this resource be reviewed or deleted?
- What type of data should this resource contain?
- Is this resource managed manually or through automation?

## Required Tags

The following tags will be required for Azure resources created in this portfolio lab.

| Tag Name           | Example Value            | Purpose                                 |
| ------------------ | ------------------------ | --------------------------------------- |
| Environment        | Lab                      | Identifies the environment type         |
| Workload           | IdentityPortfolio        | Identifies the workload or project area |
| Project            | Project01-CostGovernance | Identifies the portfolio project        |
| Owner              | PortfolioOwner           | Identifies the resource owner           |
| CostCenter         | PortfolioLab             | Supports cost tracking                  |
| DataClassification | PublicDemo               | Identifies the sensitivity level        |
| ProvisioningMethod | Manual                   | Identifies how the resource is created  |
| ExpirationDate     | 2026-06-30               | Supports cleanup and review             |

## Standard Tag Values

### Environment

| Value | Meaning                              |
| ----- | ------------------------------------ |
| Lab   | Learning and portfolio lab resources |
| Dev   | Development resources                |
| Test  | Testing resources                    |
| Prod  | Production resources                 |

For this portfolio, most resources will use:

```text
Environment = Lab
```

### Workload

| Value               | Meaning                                              |
| ------------------- | ---------------------------------------------------- |
| IdentityPortfolio   | Azure identity and Entra portfolio work              |
| SystemsPortfolio    | Azure systems engineering portfolio work             |
| SecurityPortfolio   | Azure security portfolio work                        |
| AutomationPortfolio | PowerShell, Graph, or infrastructure automation work |

### DataClassification

| Value       | Meaning                                       |
| ----------- | --------------------------------------------- |
| PublicDemo  | Safe for screenshots and public documentation |
| InternalLab | Lab data not intended for public sharing      |
| Sensitive   | Data that should not be exposed publicly      |

For this portfolio, resources should normally use:

```text
DataClassification = PublicDemo
```

No real production data, customer data, passwords, secrets, tenant IDs, or personal information should be stored in publicly documented portfolio resources.

### ProvisioningMethod

| Value       | Meaning                              |
| ----------- | ------------------------------------ |
| Manual      | Created manually in the Azure portal |
| PowerShell  | Created or managed by PowerShell     |
| Bicep       | Created or managed by Bicep          |
| Terraform   | Created or managed by Terraform      |
| AzurePolicy | Created or enforced by Azure Policy  |

At the beginning of this portfolio, most resources will use:

```text
ProvisioningMethod = Manual
```

As automation is added later, this value may change.

## Example Tag Set

The following example tag set would be used for Project 01 resources.

| Tag Name           | Value                    |
| ------------------ | ------------------------ |
| Environment        | Lab                      |
| Workload           | IdentityPortfolio        |
| Project            | Project01-CostGovernance |
| Owner              | PortfolioOwner           |
| CostCenter         | PortfolioLab             |
| DataClassification | PublicDemo               |
| ProvisioningMethod | Manual                   |
| ExpirationDate     | 2026-06-30               |

## Beginner Lesson

A resource name tells me what the resource is.

A tag tells me more about why the resource exists and how it should be managed.

Example resource name:

```text
rg-identity-lab-eastus-001
```

Example tags:

```text
Environment = Lab
Project = Project01-CostGovernance
Owner = PortfolioOwner
CostCenter = PortfolioLab
```

Together, the name and tags make the resource easier to understand, manage, and clean up.

## Tagging Rules

The following rules will be used:

- All Azure resources should have required tags where supported
- Tag names should be consistent
- Tag values should be clear and readable
- Tags should not contain passwords, secrets, tenant IDs, or personal information
- The ExpirationDate tag should be reviewed regularly
- Public portfolio screenshots should not expose sensitive tag values

## Portfolio Standard

For this portfolio, every Azure resource should include these tags where supported:

```text
Environment
Workload
Project
Owner
CostCenter
DataClassification
ProvisioningMethod
ExpirationDate
```

## Future Improvement

In a future project, I may use Azure Policy to require specific tags during resource creation.

I may also use PowerShell to report on resources that are missing required tags.