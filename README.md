# ITA Coverage Application Testing

## 📌 Project Overview
This repository contains a structured and exploratory software testing analysis of the ITA Coverage Application developed by the Occupational Safety and Health Administration (OSHA).

The application determines whether an establishment is required to submit workplace injury and illness data (Forms 300A, 300, and 301) through the Injury Tracking Application (ITA).

This project demonstrates a systematic approach to testing rule-based systems, focusing on input validation, decision logic, and system behavior.

---

## 🎯 Objectives
- Evaluate the correctness of reporting decisions
- Identify inconsistencies in system logic
- Analyze how different inputs affect outcomes
- Explore rule hierarchy and decision pathways
- Document findings in a professional and structured format

---

## 🧠 System Understanding

The application determines reporting requirements based on:

- State
- Employee size (11 or more employees)
- Peak establishment employment
- Government classification:
  - Non-government
  - Federal Government
  - State/Local Government
- NAICS code (industry classification)

---

## 🔍 Testing Approach

Testing was conducted using a combination of:

### 1. Variable Isolation
Changing one input at a time to observe its impact on output.

### 2. Boundary Testing
Testing critical thresholds such as:
- 10 vs 11 employees
- 20 vs 100 employees
- 249 vs 250 employees

### 3. Rule Exploration
Identifying how:
- Government type affects reporting requirements
- NAICS codes influence eligibility
- Employee thresholds trigger different reporting levels

### 4. Consistency Testing
Repeating test cases to verify stable system behavior.

### 5. Comparative Analysis
Running identical inputs across:
- Different states
- Different government types

---

## 🧪 Key Test Areas

- Input validation
- Rule-based decision logic
- Government classification behavior
- Employee threshold handling
- NAICS code influence
- Output consistency and clarity
- UI behavior (field persistence and reset)

---

## 📊 Key Findings

### ✔ Consistent Behavior
- Non-government establishments with 11+ employees typically require **Form 300A submission**
- State and local government establishments consistently return **“Reporting Not Required”**

### ⚠ Observed Anomalies
- Federal government selection may not always reflect correctly in output
- Possible mismatch between UI selection and backend processing
- Some inputs appear to default to "Non-government" behavior under certain conditions

### 🧠 Discovered Rules
- Government type can override other decision conditions
- Employee thresholds determine reporting level (none, 300A, full reporting)
- NAICS codes influence whether an establishment is covered or exempt
- State has minimal impact on core reporting decisions

---

## 🧾 Repository Structure
