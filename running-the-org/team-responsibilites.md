# Team Responsibilites

## Introduction

Running a Salesforce Org requires a team effort, and will likely require team members to wear many hats. 



### 

### 

#### DevOps Engineering

* **Responsibilities**
  * Source code repository and pipeline Management
    * Add new repos and pipelines for unlocked packages as needed
      * \(After approval from Software Architecture\)
    * Manage code reviewer sign-off assignment
    * Asset management \(develop & document policy/strategy\)
    * Secrets management \(develop & document policy/strategy\)
    * Branch management \(develop & document policy/strategy\)
    * Manage permissions / policies / extensions
  * Administer code promotion from Scratch Org to DevInt &gt; Test &gt; UAT &gt; Prod Sandboxes
    * Participate in change management process
    * Unlocked package versioning
  * Participates in release management meetings
  * Monitors the DevOps toolset feature releases, communicates changes to team.
  * Develops team onboarding materials for DevOps
* **Resources**
  * [Get Started with Azure DevOps \(self learning\)](https://docs.microsoft.com/en-us/learn/modules/get-started-with-devops/)
  * [Agile with Azure DevOps \(self learning\)](https://docs.microsoft.com/en-us/learn/modules/choose-an-agile-approach/index)
  * [Azure DevOps Management Documentation](https://docs.microsoft.com/en-us/azure/devops/user-guide/project-admin-tutorial?view=azure-devops)
  * [Azure DevOps Feature Timeline](https://docs.microsoft.com/en-us/azure/devops/release-notes/features-timeline)

**System/Site Reliability Engineering**

* **Responsibilities**
  * Metrics Collection, Publishing and Rate Limiting
    * Responsible for managing storage and costs involved in running this service line. 
    * Determines data to be collected, defining granularity and frequency, determines how data can be summarized
    * Continually:
      * 1\) start very high-level 
      * 2\) get in the wild 
      * 3\) monitor 
      * 4\) review with team and adjust accordingly. 
      * Continually adapting and optimizing granularity and frequency.
    * Builds logging budgets \(storage\) and ensures applications operate within budget limits
      * Reviews all budgets to understand overall cost
    * Determine normal operating constraints for metrics, develop alerting and means of publishing and notification of proper staff when out of range.
    * Monitor systems for outages, interruptions and service degradation
    * Monitors systems against governor limits and Salesforce enforced thresholds \(API Limits etc\)
      * Warns when system is close to exceeding expected boundaries
      * Maintains quotas for limits, gets insight if quotas are breached and discusses with appropriate team members
  * Works with Salesforce Team and Business to develop run-books for system issues
  * Builds and maintains APM stack or other logging/monitoring platforms and tools
* **Resources**
  * [https://github.com/dastergon/awesome-sre](https://github.com/dastergon/awesome-sre)
  * [SRE Trailmix](https://trailhead.salesforce.com/users/gidich/trailmixes/sre-starter-kit)

**Software Architectural Direction**

* **Responsibilities**
  * Reviews proposed changes to the systems prior to implementation to ensure alignment
  * Runs software architectural review sessions prior to sprint work beginning
  * Develops technology roadmaps
    * Understands strategic initiatives 
    * Reviews Salesforce technology roadmaps and:
      * Identifies alignment of salesforce technology to initiatives
      * Identifies customized features that are becoming platform features 
    * Reviews all 3rd party components/modules used in the system
      * Develops life cycle for turning on/sunsetting these items
  * Works with Enterprise Architecture Team
  * Works with team to develop guidelines for Unlocked Package Strategy, reviews boundaries for each unlocked package proposed, and regularly audits unlocked packages to ensure they only contain what is expected.
* **Resources**
  * [Salesforce Architecture Developer Center](https://developer.salesforce.com/developer-centers/architecture/)
  * Andrew Fawcett

**Test Data Management**

* **Responsibilities**
  * Ensure proper data coverage for all functionality and breaks up appropriately to align to Unlocked Packages
    * Data coverage needs to address use cases as needed to prove user story succeeds \(positive/negative testing etc\)
  * Ensure data alignment with automated UI tests and Unit Tests.
  * Deliver data within the context of a sprint to support feature development/modification.
  * Responsible for overall quality of test data in Sandboxes and Scratch Orgs
  * Automate the generation of test data where possible 
    * Identify and implement tools/approaches supporting data generation
      * Old Approach \[[DETAILS](https://developer.salesforce.com/page/Generating_and_Loading_Representative_Test_Data_for_Salesforce_and_Force.com_Orgs)\] 
      * Newer Approach - Forceea \[[Details](https://github.com/nmitrakis/Forceea)\]
      * JQ is a great utility to work with JSON [https://stedolan.github.io/jq/](https://stedolan.github.io/jq/)

**Automated UI Test Development**

* **Responsibilities**
  * All custom functionality in system needs to be covered by automated UI testing
  * Ensure automated UI tests are developed alongside functionality during a sprint

**Code Quality Management** 

* **Responsibilities**
  * Maintain automated checks for pull requests
    * Ensure Unit Tests Pass and Code Coverage % Requirements \(currently 75%\)
    * Static Code Analysis Rule-set Management
      * Adherence to Naming Conventions / Styles  
      * Adherence to Architectural Conventions
      * Adherence to Unlocked Package Guidance
      * Security Checks
        * Work with Security Team to Review and ensure alignment with organizational
  * Build, Maintain, Evangelize and Publish Software Architecture Standards for the organization
  * Manually review pull requests for adherence to Software Architecture Standards
    * Maintain [documented code review process](https://ecfmg.gitbook.io/sfdx-unlocked-packages-guide/developer-resources/extras/code-review-checklist) on GitBook

**Data Engineering**

* **Responsibilities**
  * Ensures data is cleansed when sandboxes are refreshed with production data
  * Reviews SOQL/SOSL queries
    * Define best practices and maintain on GitBook as part of guidance.
  * Reviews object design
    * Define best practices and maintain on GitBook as part of guidance.
  * Ensures systems are backed up
  * Reviews data limits
  * Maintains enterprise data dictionary
  * Leverages External Tools as needed
    * [https://blogs.informatica.com/2018/02/08/choose-informatica-cloud-test-data-management-for-your-salesforce-security-model/\#fbid=izOpcfsdDgJ](https://blogs.informatica.com/2018/02/08/choose-informatica-cloud-test-data-management-for-your-salesforce-security-model/#fbid=izOpcfsdDgJ)
* **Resources**
  * [Data Architecture and Management Trailmix](https://trailhead.salesforce.com/en/users/strailhead/trailmixes/architect-data-architecture-and-management)
  * [Data Engineering Starter Kit](https://trailhead.salesforce.com/en/users/gidich/trailmixes/data-engineering-starter-kit) Trailmix

**Access Control Management** - Roles, Profiles and Object Permissions

* **Responsibilities**
  * Ensures proper access to data and security 

**Security Testing**

* **Responsibilities**
  * Monitors code and configuration from a security perspective
  * Employs, configures, and runs reports with toolsets for monitoring security on platform
  * Works with security team to ensure adherence to security standards
  * Looks for OWASP top 10 and other security issues
  * Works with developers to develop remediation plans
  * Maintains a risk register
* **Resources**
  * [Develop Secure Web Apps Trail](https://trailhead.salesforce.com/en/content/learn/trails/security_developer)

**Salesforce Change Management**

* **Responsibilities**
  * Prepares for 3x annual Salesforce releases
  * Reviews all published documentation from Salesforce regarding releases
  * Audits environment to highlight areas of possible Impact
  * Runs point on all tickets that need to be created with Salesforce in support of releases
    * Works with PMO to describe impact to systems and helps to define resources needed to resolve
  * Builds Spring Summer Winter Release Process:
    * 5 Weeks ahead of release - Review Finalized Release Notes
    * 4 Weeks ahead of release - Stand up Preview Sandbox, Full regression is run with preview
    * 4-2 Weeks ahead of release - bug fixes / changes related to release are implemented and tested
    * 1 Week ahead of release -  all changes finalized and released into production in advance of release \(if possible\)
    * Release weekend - Monitor system throughout release 
* **Resources**
  * [Salesforce Release Strategies Trail](https://trailhead.salesforce.com/en/content/learn/modules/sf_releases?trail_id=sf_release_prep)
  * [Release Notes Website](https://releasenotes.docs.salesforce.com/en-us)

**Business Change Review**

* **Responsibilities**
  * Reviews requested changes requested by business staff or partners
  * Works with Salesforce Software Architect Direction resources to ensure alignment
  * Determines high level strategy for approach to implementation and impact to systems
  * Works with Business and Technical teams for clarity
* **Resources**
  * [Governance Basics](https://trailhead.salesforce.com/en/content/learn/modules/governance-basics)
  * [Blog Article](https://www.salesforce.org/ask-an-architect-governance-huh/)
  * [PDF](http://info.salesforce.org/l/30282/2018-05-24/852y5c/30282/178354/CSG_COE_Whitepaper_SFDO.pdf)

**Integration Liaison** 

* **Responsibilities**
  * Reviews external connections to the Salesforce environment \( all API integrations \)
    * Incoming and Outgoing
    * Work with Software Architect to maintain with Technology Roadmap
  * Ensures approach for integrations adhere to best practices
    * Define best practices and maintain on GitBook as part of guidance. 
  * Works with Salesforce Software Architect Direction resources to ensure alignment
  * Develops frequency/volume quotas and works with SREs to monitor them
  * Determines if fan out approach \(Custom APEX\) or Enterprise WSDL would be most appropriate
  * Determines methods for monitoring health of APIs and proper error conditions
  * Works with Integration team
  * Understands how system outages are expected to impact the Salesforce system and how to properly handle scheduled external system downtime
* **Resources**
  * [Integration Architecture Trail](https://trailhead.salesforce.com/en/users/strailhead/trailmixes/architect-integration-architecture)

 **Front End Engineering / Lightning Web Component** 

* **Responsibilities**
  * Reviews approaches taken for front end development and ensures quality and standards are met in respect to LWC and Javascript development
  * Build, maintain, evangelize and publish software architecture standards for front end engineering
  * Ensures unit tests \(Jest\) are integrated into build pipelines \[[Details](https://lwc.dev/guide/test)\]
  * Ensures JSLint/JSHint and other tools are integrated into build pipelines and are accessible to development team - define and leverage tools to maintain minimum quality standards and document on GitBook
* **Resources**
  * [Modern Javascript Development Trail](https://trailhead.salesforce.com/en/content/learn/modules/modern-javascript-development?trail_id=learn-to-work-with-javascript)
  * [LWC Dev Guide ](https://lwc.dev/guide/introduction)

**Business Admin Liaison** 

* **Responsibilities**
  * Provides support for business staff wishing to make minor changes to the system on their own with development support assistance
  * May evolve to allowing more advanced business staff to make changes in a dev environment, and reviews and guides changes and handles promotion of changes forward.
* **Resources**
  * [Service Cloud Consultant Trail](https://trailhead.salesforce.com/users/strailhead/trailmixes/prepare-for-your-salesforce-service-cloud-consultant-credential)

