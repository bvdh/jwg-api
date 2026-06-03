### Overview 

A healthcare organization deploying EHR systems with can connect them together to serve internal exchange needs or to aggregate data for external exchange. 

### Scope

Healthcare Organizations use a complex and varied array of interoperability standards and solutions to meet the standards of practice and workflow needs of the healthcare organization. We do not describe all of these use cases here, but focus on where the functional components described in the EU Health Data API can be used within a Healthcare Organization.

### Participants

- **EHR systems** — Can act as [Document Access Provider](actors.html#document-access-provider), and/or [Resource Access Provider](actors.html#resource-access-provider)

### Example Deployment Patterns

**Direct** — An EHR system exposes it's data directly for query as a Document or Resource Access Provider.

**Registry** - A Source EHR system(s) creates data and acts as a Document Publisher towards a organization registery (Document Access Provider). This registry offers access to this data to EHR systems acting as Document Consumers.

**Facade** — An EHR system aggregates data from multiple internal EHR systems and presents a single [Document Access Provider](actors.html#document-access-provider) endpoint for EHR systems acting as Document Consumers to query.

**Gateway** — An EHR system aggregates access to data from other EHR systems within the organization for the purposes of making that data available external to the organization. See the [Cross-Organization via National Infrastructure](usecase-cross-org.html) deployment scenario for more details.

### Authorization

EHR systems acting as Document/Resource Access providers may contain their own authorization server, or use an organization-level authorization server to control API access.

### Patient Identity

Healthcare Organizations may have a single Enterprise Master Patient Index (EMPI) which identifies patients known to the organization, , and shares this patient identity with other EHR systems in the organization (for example, by offering the Patient.$match API described in the Patient Matching section), and may integrate with national patient information systems.





