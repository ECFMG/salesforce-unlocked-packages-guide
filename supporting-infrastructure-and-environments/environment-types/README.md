# Environment Types

## Introduction : Sandboxes and Scratch Orgs

Salesforce provides two types of non-production environments, Sandboxes and Scratch Orgs. Each fulfills a specific purpose and in the context of this guide will be used in the following manner:

* Sandboxes
  * Limited use for fixed environments \( DEV INT, QA, UAT \)
* Scratch Orgs
  * Support all development / dev+test uses

### Limitations

Each type of non-production environment has unique constraints which defines how these are used:

**Sandboxes**

Sandboxes are refreshed from the production environment, there are limitations on how frequently they can be refreshed, as well as how many can be created.

**Scratch Orgs**

Scratch Orgs only exist for limited time, can be easily created, but are completely empty when created, therefore any related data must be generated and scripted in.

### Role Assignments

**Development &gt; Scratch Orgs**

Assuming a Scrum/Agile approach, development efforts should be short lived, and involve a team including both developers and QA staff. Scratch Orgs marry well with the needs of these teams as it allows developers to work in an isolated environment, and leverage source control as a means of sharing changes with other team members. QA staff can validate changes being made as well as develop automated testing and related test data to exercise the functionality supported in a controlled manner.

**Functional Validation &gt; Sandboxes**

Once a change is ready to be promoted, confidence that it will work in a production environment is often a requirement. Having an environment that closely mirrors production \(including all related data\) is important.

### Next Steps

Continue on to understand [Code Promotion](https://ecfmg.gitbook.io/sfdx-unlocked-packages-guide/~/drafts/-LapX5U6ImRraSuuwNvU/primary/lifecycle-guidance/code-promotion) and how to structure these environments.

### Resources

Official Salesforce Documentation

* [Scratch Orgs](https://developer.salesforce.com/docs/atlas.en-us.sfdx_dev.meta/sfdx_dev/sfdx_dev_scratch_orgs.htm)
* [Sandboxes](https://help.salesforce.com/articleView?id=deploy_sandboxes_intro.htm&type=5)

