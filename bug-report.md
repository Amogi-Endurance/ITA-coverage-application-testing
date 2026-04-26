
Test ID: GOV-03

Title: Federal Government incorrectly classified as Non-government

Description:
When "Federal Government" is selected, the system returns the same reporting requirement as "Non-government", instead of exempting it from ITA submission.

Inputs:
- State: Georgia
- Employees: Yes
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



