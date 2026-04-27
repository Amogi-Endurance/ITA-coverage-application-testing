# OSHA ITA Reporting

## Overview
This project explains OSHA Injury Tracking Application (ITA) reporting requirements in simple terms. It is meant to help QA testers, developers, and non-technical users understand who must submit OSHA injury and illness data.

---

## What is OSHA ITA?
The OSHA Injury Tracking Application (ITA) is an online system where certain employers must submit workplace injury and illness records.

These records include:
- OSHA Form 300
- OSHA Form 301
- OSHA Form 300A

---

## Who must submit ITA reports?

### 1. Private Companies (Main Group)
Most ITA reporting applies to private businesses such as:
- Farms
- Factories
- Construction companies
- Retail stores

They must report if they meet OSHA requirements such as:
- Employee size thresholds
- High-hazard industry classification

---

### 2. State and Local Government (Limited Cases)
Some state and local government employers may be required to report.

This depends on:
- Whether the state runs its own OSHA program (State Plan)
- State-specific reporting rules

---

## Who is NOT required to submit ITA reports?

### Federal Government
Federal government agencies:
- Are NOT part of OSHA ITA reporting requirements
- Do NOT submit Forms 300, 301, or 300A through ITA
- Follow separate internal safety reporting systems

---

## Simple Rule

- Private companies → May be required to report  
- Some state/local governments → May be required (depends on state)  
- Federal government → NOT included in ITA reporting  

---

## Key Insight
ITA reporting rules are designed mainly for private employers. Government employers are treated differently, and federal agencies are excluded from ITA submission requirements.

---

## Use Case
This document is useful for:
- QA testing (validation of compliance rules)
- Bug reporting (like incorrect classification issues)
- Understanding OSHA ITA eligibility logic

---

## Example Bug Scenario
If a system requires:

> Federal Government → OSHA 300/301/300A submission

This is incorrect because federal government agencies are not part of ITA-covered establishments.

---

## Summary
OSHA ITA reporting applies mainly to private employers, with some state/local government inclusion. Federal government agencies are excluded.
