OSHA ITA Coverage Testing

Overview
This project focuses on testing the OSHA Injury Tracking Application (ITA) Coverage Application, which determines whether establishments are required to submit OSHA injury and illness data (Forms 300, 301, and 300A).

The system applies rules based on:
Establishment type (Private, Federal Government, State/Local Government)
Employee count
NAICS industry classification
State Plan requirements
Purpose of Testing

The goal of this testing is to verify that the system:
Applies correct OSHA reporting rules
Correctly distinguishes between private and government establishments
Produces consistent and accurate reporting decisions
Avoids conflicting compliance messages
Test Oracles (Source of Truth)

Test results are evaluated using official OSHA guidance:
Occupational Safety and Health Administration ITA Coverage Application rules
OSHA Recordkeeping Regulation (29 CFR Part 1904)
Appendix A & B (industry exemptions and reporting requirements)
State Plan guidance for state/local government establishments

Business Rules Summary
1. Private Sector (Non-government)
Reporting required if employee size and NAICS thresholds are met
May require Forms 300, 301, and 300A
2. Federal Government
Exempt from OSHA ITA submission requirements
Should NOT be required to submit Forms 300, 301, or 300A
3. State / Local Government
Governed by State Plans
Reporting requirements depend on state-specific rules

Testing Approach
Testing is based on:
- Structured Testing
Using defined input combinations (state, employees, NAICS, facility type)
- Test Variations
Changing one variable at a time (e.g., facility type)
- Oracle-Based Validation
Comparing actual system output against OSHA rules and regulations

Expected Outcome
The system should:
Apply correct rule hierarchy:
Government classification (highest priority)
State Plan rules
Private sector NAICS + employee rules
Avoid conflicting reporting instructions

Tools / Standards Used
OSHA ITA Coverage Application
OSHA Recordkeeping Standard (29 CFR Part 1904)
State Plan guidance documentation

Note
This README is based on structured QA testing principles and official OSHA regulatory guidance used as test oracles.
