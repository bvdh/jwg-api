## Authorization tickets

| Ticket | Summary | Resolution |
| --- | --- | --- |
| [FHIR-56367](https://jira.hl7.org/browse/FHIR-56367) | Add eIDAS/EU Wallet note (Access Provider)   | **Persuasive with mod**: We will require eIDAS Regulation and, where applicable, the EU Digital Identity Wallet requirements on user authentication. |
| [FHIR-56385](https://jira.hl7.org/browse/FHIR-56385) | Health Data Access Service not limited to Consumer | **Not Persuasive**: Agree that Patients have the right to insert and rectify. This can be implemented as a UI or using an API. When using an API, the publication API is an option.  **BvdH**: I see no need to require the publication API for patients, a UI seams to be easier |
| [FHIR-56386](https://jira.hl7.org/browse/FHIR-56386) | Health Professional Access Service Authorization | **Persuasive:** We will require SMART on FHIR and indicate that IHE-IUA is compatible.  |
| [FHIR-56388](https://jira.hl7.org/browse/FHIR-56388) | Security and Authorization | **Deferred**: The proposed specification requires additional information to be passed in the OAuth2 flow and access data calls that is currently not flagged in SMART App Launch. This change is seen to be to invasive as it prevents using standard libraries. We will reconsider if/once this functionality has been added to SMART App Launch.  |
| [FHIR-56581](https://jira.hl7.org/browse/FHIR-56581) | IUA & SMART Differences | **Persuasive**: We will add the sentence: SMART App launch uses a subset of IHE-IUA. |
| [FHIR-56584](https://jira.hl7.org/browse/FHIR-56584) | Authorization & User Level | **Persuasive with Mod**: User authentication is in scope of the IG but not on all API's/systems. We will indicate where this is required. When user authentication is used, the API shall indicate that the user information is also logged. |
| [FHIR-56615](https://jira.hl7.org/browse/FHIR-56615) | SMART should be preferred not mandatory | **Not Persuasive**: IHE-IUA is not not enough to implement OAuth2 for FHIR servers. The additional requirements define by SMART App Launch are required. |
| [FHIR-56616](https://jira.hl7.org/browse/FHIR-56616) | Revise the IUA Authorization Client actor | **Persuasive with mod**: We will remove the reference to IHE-IUA from the actor definition and replace it with new SMART App Launch actors. |
| [FHIR-56650](https://jira.hl7.org/browse/FHIR-56650) | Authorization parameter SHOULDs: clarify Consumers MAY supply the same parameters Providers SHOULD support | **Persuasive with Mod**: We will explicitly state what SMART App Launch capabilities are required for which actor. |
| [FHIR-56698](https://jira.hl7.org/browse/FHIR-56698) | SMART Authorization | **Persuasive**: We will add how to integrate eIDAS/EU Digital Wallet in the authorization step. |
| | | What are the GDPR requirements?|
| [FHIR-56699](https://jira.hl7.org/browse/FHIR-56699) | Foundational IHE Profiles CT, ATNA | **Persuasive**: We will add IHE-CT as a required profile for Authorization and Resource Servers. |
| [FHIR-56705](https://jira.hl7.org/browse/FHIR-56705) | Revise Section 4.1.5.2 Step 2: Obtain Authorization Token | **Persuasive**: We will add a table that clearly states what is required for each actor on each API. |
| [FHIR-56838](https://jira.hl7.org/browse/FHIR-56838) | Revise authorization page | **Persuasive with Mod**: Until we have good alternatives, SMART App Launch is required. We will remove the mention of IHE-IUA and define SMART App Launch actors. |
| [FHIR-56845](https://jira.hl7.org/browse/FHIR-56845) | Revise actors and SMART references | **Persuasive**: We will define EHDS specific SMART App Launch based actors. |
| [FHIR-56848](https://jira.hl7.org/browse/FHIR-56848) | SMART Backend Services requirements | **Not Persuasive**: We propose to require SMART App Launch. |
| [FHIR-56852](https://jira.hl7.org/browse/FHIR-56852) | Systems SHOULD support SMART Backend Services | **Not Persuasive**: We propose to require SMART App Launch. |
