# Title of project/initiative

**This repository is accessible to all users in the github.com/equinor organisation. Please do not expose any classified (i.e. restricted or confidential) information in the architecture contract or any other files in this repository. For guidance use IT governance, for TDI projects use R&T governance.**

- **Leading advisor** (primary contact): Unknown
- **EITA architect** (primary contact): Unknown
- **Lead developer/developer contact**: Unknown
- **Git repository**: `https://github.com/equinor/<TBA>` (one or more repositories)

## Project and Leading advisors summary

Use `R` for `recommend` or `NR` for `Not Recommended` to visualize the "state" of the issues raised.

| Responsible      | Content                                                   | Result (Recommend-R or Not Recommended-NR) | Comments      |
|------------------|-----------------------------------------------------------|--------------------------------------------|---------------|
| EITA             | Aligned with BA strategy                                  | Blank                                      | Comments here |
| EITA             | Aligned with (or develop) TO-BE architecture for the area | Blank                                      | Comments here |
| Leading advisors | Comply with technical direction                           | Blank                                      | Comments here |
| Leading advisors | IT Technology                                             | Blank                                      | Comments here |
| Leading advisors | Information Management                                    | Blank                                      | Comments here |

## Meeting log

- DD.MM.YYYY - Document participants and type of meeting.
- DD.MM.YYYY - Document participants and type of meeting.

## Discussions & Actions

Please document discussion from meetings. Address the topic and what was discussed / commented. E.g. Area / Topic and Comments.

- **Cyber Security**, the topic was **Authentication** , what we **discussed** was .... the follow-up **actions** are ...

---

## Self assessment questions

The below is a non-exhaustive list of topics to be discussed during the architecture contract meetings. These are intended as triggers for self-assessment and discussion and might not contain all relevant topics or questions. Feel free to supplement as necessary. Additionally not all questions and topics will be relevant for all types of solutions / architecture contracts.

Answer based on the current state of the software / activity. Try to answer all questions. If you have not decided on a particular subject or think a question is not relevant, please state so (e.g. "Not decided yet", or "Not relevant because ...").

Based on the discussion, the architecture contract will be updated to contain specific points or issues that the project should follow up on, improve on or seek help on.

### General

- Which business area is the solution meant for? (use full name rather than abbreviation for business area/unit).
- Who are the users?
- Application description (brief)
- Main technologies (programming languages, frameworks, run-time environments etc)
- Where will the software be hosted?
- Link to architecture diagrams (preferably C4 Model for software architecture)
- How has EITA been involved in ensuring alignment with the strategy for the business area?

### Software Development & Software Architecture

- Does the software use any technology components not registered as Now/green (or not listed at all) in [IT Technology Lifecycle](https://techlifecycle.equinor.com)? If yes, please list them.
Does the application expose relevant data/functionality only using approved API mechanisms, as listed in [IT Technology Lifecycle](https://techlifecycle.equinor.com)?
- If you are exposing APIs, have you adapted to the principles in the Equinor [API Strategy](https://github.com/equinor/api-strategy)?
- Is the software subject to export control?
- TR1621, 2.8.1: _"All software developed by/for Equinor shall be made opensource, unless IP rights prevents this or there are unacceptable risks."_ Have you made your software open source? If not, please explain why.
- If you are considering bying (or already have bought) software tools, frameworks, libraries; Have you evaluated open source alternatives?
- If you are considering consuming services based on proprietary software; Have you evaluated alternative services based on open source software?
- Have all team members participated on software developer onboarding within the last 12 months?
- Does the team follow a documented Software Development Lifecycle Process? Describe very briefly.
- Do you do auditable code reviews for at least the major/central parts of the code?
- Do you deliver your software in iterations, with short feedback loops?
- Do you have a process for continuous improvement (e.g. by regular retrospectives)?
- Do the software developers have direct contact with the users of the software?
- Do you have an automated CI/CD pipeline?
- Please describe (using keywords) how the software is being tested?
- Do you have automated tests, run as part of your CI/CD pipeline?
- Have you assessed the technical debt in the software? How will you handle it?
- If your application contains a GUI, are you aligning your design with the [Equinor Design System](https://eds.equinor.com)

### Data & Information Architecture

 Note: See [this link](https://github.com/equinor/data-engineering/tree/master/docs) for optional related templates that can be linked to instead of commenting here.

- Is the full [lineage](https://en.wikipedia.org/wiki/Data_lineage) of data used by your application understood and how has this impacted your design choices?
- How is the data flowing into your application?
- Must data be kept in sync with other applications (where the same or related data appears multiple places? If yes, how are they kept in sync (e.g. event-based, sync-based)
- Is data in your application immutable, i.e. data is never updated or deleted? Are there any special requirements, legal or otherwise, regarding retention?
- Is your application considered to be a "systems of records" for all or a subset of the data? i.e. It holds the source of truth and if there is a deviation with another system, the value in the system of record is by definition the correct one.
- Is your application considered to be a "derived data system", i.e. data in your application is the result of taking some existing data from another system and transforming or processing it in some way. If you lose the derived data in your application, can you easily re-create from the original sources?
- Has a Legal Risk Assessment been performed? See [KB0042661](https://equinor.service-now.com/selfservice?id=kb_article&sys_id=96435887db360058c293199f299619c8) for more information.  
- How will other applications consume data from your application?
- What data from your application will be shared in the enterprise data platform?
- Is any produced / shared data (whether in the data platform or not)
  - Aligned with the [Enterprise Data Architecture](https://docs.omnia.equinor.com/services/data/dataarchitecture/overview/)
  - Uses master & reference data
  - Discoverable (registered in Data Catalog, APIM)
  - Named / structured / modeled according to established international or national open standards?
- What data quality requirements are needed / assumed by your application and any consumers of data and how are these ensured and monitored. Requirements might be related to accuracy, consistency, completeness, integrity, timeliness and more.
- Have you evaluated how the application should handle personal data, with GDPR regulations in mind? This includes logging of information that can identify a person, like name name, userID, email, etc.
- Have you understood and agreed the service level objective for your data (availability,  Recovery Time Objective (RTO) / Recovery Point Objective (RPO) etc.) and have you taken that into considering when making your storage technology choice?
- If we want to exit the application, but keep data usable other places - how do you plan doing that?

### Security and information management

- Who is the information owner for the software/application?
- What is the classification of the information handled by the software (open, internal, restricted, confidential)?
- Have you assessed how the information classification impact the security in the software?
- Development teams are responsible for initiating a [Security Health Check](https://statoilsrm.sharepoint.com/sites/Informationsecurityhealthcheck/Shared%20Documents/Forms/AllItems.aspx?RootFolder=/sites/Informationsecurityhealthcheck/Shared%20Documents/General&FolderCTID=0x012000D071A196DD4AD54E88B2352C5D9C5289). Has this been performed?
- Will you (or have you) ordered a penetration test? A penetration test is recommended for applications handling confidential or personal data or in cases where the risk is particularly high.

### Operations

- Which team / department will have the operational responsibility for the software?
- Has the RunBook been created?
- Has service design been done (LM of the department with operational responsibility is responsible)?
- Do you have any operational monitoring of the application?
- What have you done to ensure reliability and resilience in the software?
- What have you done to make it as easy and efficient as possible to operate the solution (reducing Total Cost of Ownership)?

**For procured software:**

- What kind of support & maintenance agreement do you have with vendor (if procured software)?
- How often will you get updates?
- Are the vendor committed to follow the lifecycle on components they are depending on, such as Microsoft SQL server, Microsoft Windows etc.?

## Sharing is caring

- What do you plan to share from your project/initiative/solution/team/? with the Equinor Developer Community?

## Other

- Are there other topics or issues you would like to discuss? Please list them.
