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

## Future Improvement
In a future project, I may use Azure Policy to require specific tags during resource creation.

I may also use PowerShell to report on resources that are missing required tags.


---

# What this file proves

This file shows that you understand:

| Skill | What it Demonstrates |
|---|---|
| Tagging | You know how metadata is used in Azure |
| Cost awareness | You understand resources need financial tracking |
| Ownership | You know resources should have an accountable owner |
| Cleanup planning | You are thinking about lifecycle and waste reduction |
| Security awareness | You are avoiding sensitive data in public documentation |
| Automation readiness | You are preparing for future PowerShell or policy enforcement |

---

# Important note

Not every Azure resource type supports tags, and not every resource type passes tags into cost reports. Microsoft maintains a tag support list by resource type. :contentReference[oaicite:3]{index=3}

Beginner translation:

> Tags are very useful, but they are not magic. Most common Azure resources support them, but you still need to know there are exceptions.

For your beginner portfolio, that is fine. We will use tags where supported.

---

# Day 2 definition of done

You are done for today when this is complete:

| Task | Status |
|---|---|
| `tagging-standard.md` created | ☐ |
| Content pasted into the file | ☐ |
| File reviewed in GitHub preview | ☐ |
| Formatting looks clean | ☐ |
| File committed to GitHub | ☐ |

Use this commit message:

```text 
id="3pt4mh"
```
Add Azure tagging standard documentation