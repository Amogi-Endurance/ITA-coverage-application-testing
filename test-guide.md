# OSHA ITA Reporting – Test Guide (Simple)

## Purpose
This guide will help verify if the system correctly determines when an establishment must submit OSHA Injury Tracking Application (ITA) reports.

The ITA system handles submission of:
- OSHA Form 300
- OSHA Form 301
- OSHA Form 300A

---

## What is being tested?
We are testing whether the system correctly:
- Identifies establishment type
- Applies OSHA reporting rules
- Determines ITA submission requirements

---

## Key Factors Used in Decision
The system typically uses:
- Establishment type (Private, Government, etc.)
- Number of employees
- Industry classification (NAICS code)
- State or federal reporting rules

---

## Establishment Types

### 1. Private Sector (Non-government)
✔ Most common category  
✔ May be required to submit ITA reports depending on:
- Employee count
- Industry risk level (NAICS code)

---

### 2. Government (State/Local)
✔ May be partially included  
✔ Reporting depends on State OSHA Plan rules  
✔ Not always required to report

---

### 3. Government (Federal)
Typically not included in ITA submission  
Follows separate federal safety reporting systems

---

## General Test Scenarios

### Scenario 1: Private Company – High Risk Industry
Input:
- Establishment type: Private
- Employees: 150
- NAICS: High-hazard industry

Expected:
✔ ITA submission required (Forms 300, 301, 300A)

---

### Scenario 2: Private Company – Low Risk Industry
Input:
- Establishment type: Private
- Employees: 50
- NAICS: Low-risk industry

Expected:
✔ May be exempt from ITA submission

---

### Scenario 3: Government Establishment
Input:
- Establishment type: Government (State/Local or Federal)
- Employees: Any
- NAICS: Any

Expected:
Follow government-specific rules  
May be exempt depending on category and rules engine logic

---

## Key Validation Rules

The system should ALWAYS:
1. Identify establishment type first  
2. Apply government vs private rules correctly  
3. Then evaluate employee count and NAICS code  

---

## Common Issues to Test For

- Government treated as private company
- Wrong application of NAICS rules
- Employee thresholds applied before establishment type
- Incorrect ITA submission requirement for exempt entities

---

## Expected Outcome

A correct system should:
- Apply OSHA rules consistently
- Avoid misclassification of establishment types
- Only require ITA submission when conditions are truly met

---

## Summary

ITA reporting is based on a combination of:
- Establishment type
- Industry classification
- Employee count
- Regulatory exemptions

Correct classification logic is critical for compliance accuracy.
