OSHA-ITA APPLICATION – TEST REPORT & BUG REPORT
Product: OSHA-ITA Application
Version: 1.0.0
Reporter: Amogi Endurance
Date: 27.04.2026

Objective
Ensure system correctly determines whether ITA reporting is required based on OSHA rules.

Testing Report
Test Case #1A	
Summary	OSHA ITA reporting requirement for private high-hazard manufacturing establishment
Description
	The system evaluates whether a private sector manufacturing establishment with 180 employees and a high-hazard NAICS code (311423 – Dried and Dehydrated Food Manufacturing) is required to submit OSHA injury and illness data through the ITA. The expectation is to confirm correct application of OSHA reporting rules based on employee count and industry classification
Steps	•	State: Georgia 
•	Employee 11 or More: Yes 
•	Peak Establishment Employment: 180 
•	Establishment Type: No 
•	NAICS Code: 311423 – Dried and Dehydrated Food Manufacturing 
•	Submit
ITA Requirement	Based on your entries, you are required to report your OSHA Forms 300, 301 and 300A data to OSHA through the Injury Tracking Application

Status	Pass
Remark	This test confirms that the system correctly identifies covered private-sector high-hazard establishments and applies OSHA ITA reporting rules appropriately.

Test Case #1B	
Summary	OSHA ITA reporting requirement for federal government high-hazard manufacturing establishment
Description
	The system evaluates whether a federal government sector manufacturing establishment with 180 employees and a high-hazard NAICS code (311423 – Dried and Dehydrated Food Manufacturing) is required to submit OSHA injury and illness data through the ITA. The expectation is to confirm correct application of OSHA reporting rules based on employee count and industry classification
Steps	•	State: Georgia 
•	Employee 11 or More: Yes 
•	Peak Establishment Employment: 180 
•	Establishment Type: Yes, Federal government
•	NAICS Code: 311423 – Dried and Dehydrated Food Manufacturing 
•	Submit
ITA Requirement	Based on your entries, you are required to report your OSHA Forms 300, 301 and 300A data to OSHA through the Injury Tracking Application

Status	fail
Remark	The system fails to correctly distinguish Federal Government establishments and incorrectly applies OSHA ITA reporting rules meant for private-sector employers.


Test Case #1C	
Summary	OSHA ITA reporting requirement for State or Local Government high-hazard manufacturing establishment
Description
	The system evaluates whether a State or Local Government sector manufacturing establishment with 180 employees and a high-hazard NAICS code (311423 – Dried and Dehydrated Food Manufacturing) is required to submit OSHA injury and illness data through the ITA. The expectation is to confirm correct application of OSHA reporting rules based on employee count and industry classification
Steps	•	State: Georgia 
•	Employee 11 or More: Yes 
•	Peak Establishment Employment: 180 
•	Establishment Type: Yes, State or Local Government
•	NAICS Code: 311423 – Dried and Dehydrated Food Manufacturing 
•	Submit
ITA Requirement	Based on your entry for state, as a state or local government establishment you are NOT required to submit your injury and illness data through the Injury Tracking Application.

Status	Pass
Remark	This test confirms that the system correctly excludes State or Local Government establishments from ITA reporting requirements, even when they meet employee count and high-hazard industry conditions. The establishment type is correctly prioritized in the decision logic before applying NAICS-based reporting rules.


