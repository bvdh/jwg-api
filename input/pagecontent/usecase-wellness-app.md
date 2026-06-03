### Overview

A wellness application may optionally claim EHR interoperability component conformance ([Art. 47–48](https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202500327#art_47)) and use the same API transactions defined in this IG to exchange patient data.

This page also describes how wellness applications might be used to support the patient's right ([Art. 5](https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202500327#art_5), [Art. 48(2)](https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202500327#art_48)) to insert data into an EHR system.

### Scope

This IG specifies an informative example for how wellness applications might use the API functionalities discussed in this IG. Requirements for the patient-facing health data access service, including the use of the eIDAS 2.0 patient wallet, are out of scope.

### Participants

- **Wellness application** — [Document Consumer](actors.html#document-consumer) and/or [Resource Consumer](actors.html#resource-consumer); optionally [Document Publisher](actors.html#document-publisher) for patient-written data.
- **EHR system** — [Document Access Provider](actors.html#document-access-provider) and/or [Resource Access Provider](actors.html#resource-access-provider)
- **Health Data Access service** — Patient-facing access service, may authenticate the patient and establish authorization context; outside this IG's scope

Whether a wellness app connects directly to an EHR system or through a patient access service is not specified by EHDS and left free to implementation.

#### Authorizing Patient Data Exchange

For a wellness app to act on behalf of the patient to exchange data, for example when connected to the health data access service, an authorization mechanism is required that ties access to the patient's identity and consent. Defining patient-level authorization mechanisms is outside this IG's scope, but we recommend implementers consider the [SMART App Launch](https://hl7.org/fhir/smart-app-launch/) framework for meeting this need.

### Using the Interoperability Component to Access Patient Data

1. The patient authenticates to the health data access service, and consents to share data with the wellness application.
2. The Wellness Application (Acting as a Document/Resource Consumer) queries health Data Access service (Acting as a Document/Resource Access Provider) to access data.

### Art. 5: Insertion of Patient-Provided Data (Informative)

EHDS has not fully specified the requirements, expected data, or use cases for Art. 5 patient data insertion.

#### Submitting Patient-Provided Documents

A wellness app may submit patient-provided priority-category data in EEHRxF format to an EHR system using the [Document Publisher](actors.html#document-publisher) interactions defined in this IG (ITI-105).

To distinguish patient-provided data from clinician-authored data, resources may carry `.meta.security` tags and/or [Provenance](https://hl7.org/fhir/provenance.html) resources indicating the patient as the source.

#### Future Work: Resource-Level Patient-Provided Data

Patient-provided data extends beyond priority-category documents. For individual resources (observations, medications, etc.), we recommend future work follows an approach analogous to the [FHIR CGM specification](https://build.fhir.org/ig/HL7/cgm/), modeling the needs of a specific use case and its interaction with care providers — for example:
- Continuous glucose monitoring and other device-sourced observations
- Patient-reported vitals/observations (fitness trackers, home monitoring)
- Patient-reported medications and supplements
