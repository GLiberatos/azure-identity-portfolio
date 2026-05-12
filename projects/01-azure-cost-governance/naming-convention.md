# Azure Naming Convention

## Purpose

This document defines the naming convention I will use for Azure resources in my portfolio lab environment.

A naming convention helps make resources easier to identify, manage, troubleshoot, and document.

## Why Naming Standards Matter

In Azure, resources such as virtual machines, resource groups, virtual networks, and storage accounts all need names.

Without a standard, names can become confusing.

For example, these names are not helpful:

```text
testvm
newrg
azurething
server1
demo
```

## Naming Format
```text
<resource-type>-<workload>-<environment>-<region>-<instance>
```

## Naming Components
| Component     | Meaning                    | Example                     |
| ------------- | -------------------------- | --------------------------- |
| resource-type | The type of Azure resource | rg, vm, vnet                |
| workload      | The purpose or project     | identity, systems, security |
| environment   | The environment type       | lab, dev, test              |
| region        | Azure region               | eastus                      |
| instance      | Number for uniqueness      | 001                         |

## Example Resource Group Name
```text
rg-identity-lab-eastus-001
```

## Standard Abbreviations
| Azure Resource          | Abbreviation |
| ----------------------- | ------------ |
| Resource Group          | rg           |
| Virtual Network         | vnet         |
| Subnet                  | snet         |
| Network Security Group  | nsg          |
| Virtual Machine         | vm           |
| Network Interface       | nic          |
| Public IP Address       | pip          |
| Storage Account         | st           |
| Log Analytics Workspace | law          |
| Key Vault               | kv           |

## Portfolio Naming Standard
```text
<resource-type>-<workload>-lab-<region>-<###>
```

## Examples
| Resource Type           | Example Name                 |
| ----------------------- | ---------------------------- |
| Resource Group          | rg-identity-lab-eastus-001   |
| Virtual Network         | vnet-identity-lab-eastus-001 |
| Subnet                  | snet-identity-lab-eastus-001 |
| Network Security Group  | nsg-identity-lab-eastus-001  |
| Virtual Machine         | vm-dc-lab-eastus-001         |
| Log Analytics Workspace | law-identity-lab-eastus-001  |

## Naming Rules

The following rules will be used:

- Use lowercase letters where supported
- Avoid spaces
- Avoid special characters unless required
- Keep names readable
- Use numbers for multiple instances
- Use abbreviations consistently
- Do not include sensitive information in resource names

## Beginner Lesson
A good Azure resource name should answer three basic questions:

1. What is it?
2. What is it for?
3. Where does it belong?

Example:

```text
rg-identity-lab-eastus-001
```
This tells me it is:

- A resource group
- For identity work
- In a lab environment
- Located in East US
- The first instance

## Future Improvement
In a future project, I may convert this naming convention into a PowerShell or Bicep template so that resources can be created more consistently.
