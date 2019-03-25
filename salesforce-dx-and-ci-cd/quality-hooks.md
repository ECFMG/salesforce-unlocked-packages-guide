# Quality Hooks

## Overview

Quality hooks are part of the git-flow process and tie in linting and unit tests to be automatically performed with each check-in by a developer.

Fortunately, the SFDX provides a number of tools for both linting, security, and unit testing to be introduced into the DevOps pipeline.

The guidance that follows illustrates how to incorporate the items into Azure Pipelines.

Static Analysis In order to ensure quality code, static analysis should performed on all source code. SonarQube and SonarCloud are great tools to help make this happen

Salesforce specific checks are provided by:

* [CheckMarx](https://www.checkmarx.com/sast-supported-languages/apex-overview-vulnerabilities/)
* [CodeScan](https://www.code-scan.com/)
* [PMD](https://pmd.github.io/pmd-6.2.0/pmd_rules_apex.html)
* [Clayton](https://www.getclayton.com/)

Automated Testing  All unit tests should be executed for any code written. \(Apex\) as well as monitor code coverage with each commit

* Apex 
  * Unit Tests 
    * Running as part of build: `sfdx force:apex:test:run --resultformat human`
    * Mocks [link](https://andyinthecloud.com/2015/03/29/unit-testing-apex-enterprise-patterns-and-apexmocks-part-2/)
  * Lightning 
    * Linting [link](https://developer.salesforce.com/docs/atlas.en-us.lightning.meta/lightning/cli_usage.htm) - ensure consistent quality code \(code analysis / validation\)
    * ESLint Rules [link](https://developer.salesforce.com/docs/atlas.en-us.lightning.meta/lightning/cli_rules_customization.htm)
    * Lightning Tests [Link](https://github.com/forcedotcom/LightningTestingService)

Resources:

* Salesforce DX - CI/CD - [https://www.youtube.com/watch?v=wUc1l5keYmo](https://www.youtube.com/watch?v=wUc1l5keYmo)
* Salesforce CI how-to: [https://developer.salesforce.com/page/Continuous\_Integration\_How-To](https://developer.salesforce.com/page/Continuous_Integration_How-To)

