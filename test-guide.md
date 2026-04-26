# ITA COVERAGE APPLICATION – TEST GUIDE

## 1. Introduction

This document defines the structured approach for testing the ITA Coverage Application developed by the Occupational Safety and Health Administration (OSHA).

The application determines whether an establishment is required to submit workplace injury and illness data (Forms 300A, 300, and 301) through the Injury Tracking Application (ITA).

---

## 2. Purpose

The purpose of this test guide is to:

- Identify all testable elements of the system
- Define a structured approach to testing
- Explore and validate system behavior under different conditions
- Support consistent and repeatable testing
- Capture both expected and unexpected system behavior

---

## 3. System Overview

The ITA Coverage Application evaluates reporting requirements based on user-provided inputs and predefined regulatory rules.

### Core Inputs:
- State
- Firm size (11 or more employees)
- Peak establishment employment
- Government classification:
  - Non-government
  - Federal Government
  - State or Local Government
- NAICS code (industry classification)

### Core Outputs:
- Reporting NOT required
- Submit Form 300A
- Submit Form 300A + 300/301

---

## 4. Test Scope

### In Scope:
- Input field behavior
- Validation rules
- Decision logic and rule processing
- Output accuracy and consistency
- UI behavior and state persistence

### Out of Scope:
- Backend implementation details
- External system integrations
- Performance and load testing

---

## 5. Test Approach

Testing will be conducted using an exploratory and analytical approach:

### 5.1 Variable Isolation
Only one input variable is changed at a time to determine its impact on system output.

### 5.2 Boundary Testing
Critical threshold values will be tested, including:
- 10 vs 11 employees
- 20 vs 21 employees
- 99 vs 100 employees
- 249 vs 250 employees

### 5.3 Rule Exploration
System behavior will be analyzed to identify:
- Rule hierarchy
- Conditional dependencies
- Override conditions

### 5.4 Consistency Testing
Repeated execution of identical inputs to verify stability and determinism.

### 5.5 Comparative Testing
Testing identical scenarios across:
- Different states
- Different government types
- Different NAICS codes

---

## 6. Testable System Elements

### 6.1 Input Fields
- State selection
- Employee size selection
- Peak employment input
- Government classification selection
- NAICS code selection

### 6.2 Input Validation
- Required field enforcement
- Numeric validation (peak employment)
- Handling of invalid or incomplete inputs

### 6.3 Decision Logic
- Employee threshold rules
- Government classification rules
- NAICS-based eligibility rules

### 6.4 Rule Interaction
- Interaction between government type and employee thresholds
- Interaction between NAICS and reporting requirements
- Identification of rule overrides

### 6.5 UI Behavior
- Field persistence after selection
- Field reset behavior when inputs change
- Default values and auto-selection behavior

### 6.6 Output Behavior
- Accuracy of reporting decision
- Clarity of system messages
- Alignment between input and output

---

## 7. Key Test Focus Areas

- Government classification consistency (especially Federal Government behavior)
- Employee threshold transitions
- NAICS code influence on reporting decisions
- Input persistence and UI state handling
- Output consistency and logical correctness

---

## 8. Risks and Assumptions

### Risks:
- Incorrect classification may lead to compliance errors
- Input misinterpretation may affect decision accuracy
- Lack of transparency in rule logic may obscure defects

### Assumptions:
- Inputs provided by the user are intended to reflect real-world scenarios
- The system applies OSHA regulatory rules consistently

---

## 9. Test Data Strategy

Test data will include:

- Valid inputs (expected scenarios)
- Boundary values
- Edge cases
- Invalid and unexpected inputs

Examples:
- Low employee counts (e.g., 10)
- Threshold values (e.g., 11, 20, 100, 250)
- Different government types
- Multiple NAICS codes across industries

---

## 10. Observation and Documentation

Each test execution will capture:

- Test ID
- Input values
- Expected outcome
- Actual result
- Observations
- Identified issues (if any)

---

## 11. Success Criteria

Testing will be considered successful when:

- System behavior is consistent and repeatable
- Outputs align logically with inputs
- Key rules and decision paths are understood
- Any inconsistencies or anomalies are clearly documented

---

## 12. Conclusion

This test guide provides a structured framework for evaluating the ITA Coverage Application. It ensures that testing is systematic, comprehensive, and focused on understanding both system behavior and underlying decision logic.
