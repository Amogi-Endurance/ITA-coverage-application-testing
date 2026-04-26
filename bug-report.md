
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
