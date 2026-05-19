# ITA Coverage Application Testing Project

## Overview

This project contains an exploratory and regulation-based testing assessment of the OSHA ITA (Injury Tracking Application) Coverage Application.

The purpose of the testing was to evaluate whether the application correctly determines which establishments are required to electronically submit OSHA injury and illness records, including Forms 300A, 300, and 301.

The testing focused on:

* OSHA reporting decision logic
* NAICS classification behaviour
* Employee threshold rules
* Employer type separation
* State Plan routing behaviour
* Input validation
* Exception handling
* Cross-rule interaction testing

---

# Project Objective

The objective of this project was to:

* Explore how the ITA Coverage Application behaves under different regulatory conditions
* Evaluate whether OSHA reporting rules are applied correctly
* Identify inconsistencies, validation issues, and logic defects
* Practice structured exploratory testing and regulation-based test design

---

# Product Under Test

The product tested was the OSHA ITA Coverage Application.

The application is designed to help establishments determine whether they are required to electronically submit occupational injury and illness data to OSHA.

The system uses decision logic based on:

* Employee count
* Industry classification (NAICS)
* Employer type
* State selection

---

# Testing Approach

## Exploratory Testing

The testing began with exploratory interaction to understand:

* Application flow
* Input dependencies
* Decision boundaries
* Validation behaviour
* Reporting outcomes

The following UI elements were explored:

* Dropdown menus
* Input fields
* Validation behaviour
* Submission responses
* Navigation links

---

# Regulation-Based Test Design

The test strategy was built directly from OSHA regulatory structure rather than random industry selection.

The test design covered:

* OSHA Appendix A industries (partially exempt)
* OSHA Appendix B industries (100+ employee reporting industries)
* Standard non-exempt industries
* USPS exception case (491110)
* Employee threshold boundaries
* Employer type separation
* State Plan routing logic
* Invalid and malformed inputs

---

# Test Dimensions

| Test Area                  | Purpose                                                      |
| -------------------------- | ------------------------------------------------------------ |
| NAICS Regulatory Grouping  | Verify reporting logic across OSHA industry classifications  |
| Employee Threshold Testing | Verify behaviour at OSHA reporting boundaries (20, 100, 250) |
| Employer Type Testing      | Verify separation of Private, Federal, and State/Local rules |
| State Plan Testing         | Verify routing behaviour for State Plan jurisdictions        |
| Input Validation           | Verify handling of invalid or malformed inputs               |
| Interaction Testing        | Verify behaviour when multiple rules interact together       |
| Exception Testing          | Verify USPS special-case handling                            |

---

# Key OSHA References

The testing was based on:

* 29 CFR Part 1904
* 29 CFR 1904.41
* OSHA Appendix A (Partially Exempt Industries)
* OSHA Appendix B (Designated Industries)
* 29 CFR 1960.72(a) (Federal Agency Reporting)

References:

* [https://www.osha.gov/recordkeeping](https://www.osha.gov/recordkeeping)
* [https://www.osha.gov/recordkeeping/naics-codes-electronic-submission](https://www.osha.gov/recordkeeping/naics-codes-electronic-submission)
* [https://www.osha.gov/stateplans](https://www.osha.gov/stateplans)

---

# Key Findings

## Observed Strengths

* Stable and responsive interface
* Clear validation for required fields
* Correct handling of employee thresholds in many scenarios
* Consistent State Plan routing behaviour
* Stable handling of large numeric values

## Issues Observed

* Weak NAICS validation
* Scientific notation accepted as numeric input
* Unclear separation between federal and private-sector reporting logic in some scenarios
* Potential ambiguity in decision explanations

---

# Example Test Scenarios

| Scenario                         | Result                             |
| -------------------------------- | ---------------------------------- |
| 20-employee threshold            | Correctly triggered 300A reporting |
| Invalid numeric input            | Rejected/flagged                   |
| USPS exception case              | Correctly handled                  |
| State/Local Government selection | Routed to State Plan guidance      |
| Extreme employee values          | System remained stable             |

---

# Skills Demonstrated

This project demonstrates:

* Exploratory testing
* Regulation-based test design
* Risk analysis
* Boundary value testing
* Input validation testing
* Cross-rule interaction testing
* Defect reporting
* Analytical reasoning
* Test documentation

---

# Deliverables

The project includes:

* Test Report
* Test Strategy
* Test Cases
* Bug Reports
* Risk Assessment
* Recommendations

---

# Lessons Learned

This project improved my understanding of:

* Structured exploratory testing
* Regulation-driven test design
* Decision-rule analysis
* Test strategy documentation
* Linking test coverage directly to business rules and regulations

---

# Author

Amogi Endurance Friday

Senior Technical Associate Health Informatics | Data Analyst | Software Tester


LinkedIn: [Add your LinkedIn link]
