Test ID: GOV-1

Title: Incorrect ITA reporting logic and inconsistent outputs across Non-government, Federal Government, and State/Local Government establishments

Description:
The system produces inconsistent OSHA Injury Tracking Application (ITA) reporting decisions for identical input values (state, employee size, peak establishment employment, and NAICS code) based on facility type selection.
In particular, Federal Government classification incorrectly triggers private-sector reporting logic, resulting in an incorrect requirement to submit OSHA Forms 300, 301, and 300A. Additionally, output messaging is inconsistent across government classifications.

Test Inputs (All Scenarios):
Scenario 1: 
Non-government
-	State: California
-	Did firm have ≥11 employees?: Yes
-	Peak Employment: 100
-	Facility Type: Non-government
-	NAICS Code: 111130 (Dry Pea and Bean Farming)
  
Scenario 2: 
Federal Government
-	State: California
-	Did firm have ≥11 employees?: Yes
-	Peak Employment: 100
-	Facility Type: Federal Government
-	NAICS Code: 111130 (Dry Pea and Bean Farming)
  
Scenario 3: 
State/Local Government
-	State: California
-	Did firm have ≥11 employees?: Yes
-	Peak Employment: 100
-	Facility Type: State or Local Government
-	NAICS Code: 111130 (Dry Pea and Bean Farming)
  
Actual Outputs:
Scenario 1: Non-government
“Based on your entries, you are required to report your OSHA Forms 300, 301 and 300A data to OSHA through the Injury Tracking Application.”
Correct behavior

Scenario 2: Federal Government
“Reporting is NOT required for this establishment.” But system contradicts itself by also stating:
“Based on your entries, you are required to report your OSHA Forms 300, 301 and 300A data…”
Critical contradiction: exemption vs mandatory reporting

Scenario 3: State/Local Government
“Reporting may be required for this establishment. Please contact your state occupational safety and health agency…”
Correct routing to State Plan guidance

 Expected Result:
Non-government:
•	Must require submission of Forms 300, 301, 300A via ITA
Federal Government:
•	Must be fully exempt
•	Must display ONLY:
“Reporting is NOT required for this establishment.”
•	Must NOT display any reporting requirement message
State/Local Government:
•	Must route to State Plan guidance only
•	Must NOT trigger federal ITA submission logic

Actual Result Summary:
•	Non-government: Correct
•	State/Local Government: Correct
•	Federal Government:
o	Shows exemption message
o	Also shows conflicting mandatory reporting requirement
o	Applies non-government logic incorrectly

🔴 Severity:
Critical
Impact:
•	Federal Government users receive conflicting compliance instructions
•	May lead to:
o	Incorrect OSHA submissions
o	Misclassification of government entities as private employers
o	Regulatory compliance risk
•	Indicates failure in rule precedence and output consistency
Root Cause (Likely):
-	Missing hard override rule for Federal Government
•	Multiple rule branches executed simultaneously:
o	Government exemption logic 
o	Non-government NAICS + employee logic 
•	Output layer merges conflicting rule results instead of resolving single outcome

Recommendation:
•	Implement strict rule hierarchy:
1.	Facility Type (Highest Priority)
o	Federal Government → Immediate EXEMPT (stop execution)
2.	State/Local Government → State Plan routing only
3.	Non-government → Apply NAICS + employee threshold rules
-------------------------------------------------------------------------------------------------------------------------


Test ID: GOV-03

Title: Federal Government incorrectly classified as Non-government

Description:
When "Federal Government" is selected, the system returns the same reporting requirement as "Non-government", instead of exempting it from ITA submission.

Inputs:
- State: Georgia
- Employees (≥11): Yes
- Peak Employment: 300
- NAICS: 111335 (Tree Nut Farming)

Test Variations:
1. Non-government → Full reporting required 
2. State/Local Government → No reporting required 
3. Federal Government → Full reporting required 

Expected Result:
Federal Government establishments should not be required to submit ITA data, similar to State/Local Government.

Actual Result:
Federal Government is treated as Non-government and required to submit Forms 300, 301, and 300A.

Severity:
High

Impact:
May lead to incorrect compliance requirements for federal establishments.

Recommendation:
Review classification logic to ensure Federal Government is handled as a distinct category and exempted appropriately.

---------------------------------------------------------------------------------------------------------------------


Test ID: GOV-04

Title: Incorrect messaging applied to Federal Government under small establishment exemption

Description:
When "Federal Government" is selected for a small establishment (≤10 employees), the system applies private-sector exemption messaging based on firm size instead of recognizing Federal Government as inherently exempt from OSHA ITA requirements.
This results in misleading guidance, as the exemption is attributed to firm size rather than government classification.

Inputs:
-	State: Georgia
-	Employees (≥11): No
-	Peak Employment: 10
-	NAICS Code: 111335 (Tree Nut Farming)

Test Variations:
1.	Non-government → No recordkeeping + No ITA submission
2.	State/Local Government → No ITA submission
3.	Federal Government → Partial exemption message shown

Expected Result:
-	Non-government (≤10 employees):
o	Exempt from OSHA recordkeeping
o	Not required to submit ITA data
-	State/Local Government:
o	Not required to submit ITA data
-	Federal Government:
o	Not required to submit ITA data
o	Should display a clear exemption based on government status, not firm size
o	 Should NOT include “partially exempt based on firm size” messaging

Actual Result:
-	Federal Government displays:
“Based on your entry for Firm size, you are partially exempt…”
-	This is misleading because:
o	Exemption is incorrectly attributed to firm size logic
o	Instead of Federal Government classification

Severity:
🟡 Medium

Impact:
-	Produces confusing and inaccurate compliance guidance
-	Misrepresents the basis for exemption (firm size vs. government status)
-	Could lead to:
o	Misinterpretation of OSHA applicability
o	Incorrect compliance assumptions or documentation

Recommendation:
-	Prioritize facility type classification before applying employee-size logic
-	Ensure Federal Government always:
o	Returns a distinct exemption message
o	Is excluded from private-sector exemption rules and wording
-	Update messaging to clearly reflect government-based exemption
----------------------------------------------------------------------------------------------------------------------

Test ID: GOV-05
Title: Incorrect validation and reporting logic for government establishments and peak employment constraint

Description:

The system incorrectly applies private-sector validation rules to government establishments and enforces an invalid constraint where peak establishment employment cannot exceed firm size. This results in inconsistent reporting eligibility messages and unnecessary validation errors.

Inputs:
-	State: California
-	Employees (≥11): No
-	Peak Employment: 10
-	NAICS Code: 111130 (Dry Pea and Bean Farming)

Test Variations:
1. Non-government → Correct reporting eligibility shown
2. Federal Government → Validation error displayed
3. State/Local Government → Validation error displayed

Expected Result:
-Peak establishment employment should be accepted as valid input when consistent with system rules
-Government establishments should:
-Be exempt from ITA reporting
-Not be affected by private-sector validation rules
-No validation error should be triggered for government classification cases

Actual Result:
-System displays error message:
“Peak establishment employment cannot be larger than Firm size.”
-Government establishments are incorrectly subjected to private-sector validation logic
-Reporting exemption logic is not consistently applied

Severity:
🔴 High

Impact:
-Blocks valid data input due to incorrect validation rules
-Applies private-sector constraints to government entities
-Produces inconsistent reporting eligibility outcomes
-Impacts usability and compliance accuracy

Recommendation:
-Separate validation rules from reporting eligibility logic
-Ensure government classification bypasses firm-size constraints
-Review and correct logic for peak employment validation handling
-Prevent cross-contamination between private-sector and government rule sets

