# Pipeline Introduction

## Introduction

Creating a pipeline automates many of the activities involved in development and helps to make processes more efficient and increases team throughput.

This section will explore setup and configuration leveraging Azure DevOps.

### Technical Considerations

Guidance in this document provides details on some products that the team who developed are familiar with, but the approach would be the same regardless of the tools used.

* [Azure Pipelines](https://docs.microsoft.com/en-us/azure/devops/pipelines/?view=azure-devops) - Continuous integration and continuous delivery \(CI/CD\) that works with any language, platform, and cloud.
* [Azure Repos](https://docs.microsoft.com/en-us/azure/devops/repos/index?view=azure-devops) - Unlimited cloud-hosted private Git and Team Foundation Version Control \(TFVC\) reports for your project.
* [Azure Boards](https://docs.microsoft.com/en-us/azure/devops/boards/index?view=azure-devops) - Work tracking with boards, backlogs, team dashboards, and custom reporting.
* [Azure Test Plans](https://docs.microsoft.com/en-us/azure/devops/test/index-tp?view=azure-devops) - All-in-one planned and exploratory testing solution.
* Visual Studio Code - IDE used in tandem with Salesforce DX plugin to write edit, and deploy code into the repos.

### Set-up Salesforce for continuous deployment

In order for Salesforce to receive new automated headless deployment, below are a few settings:

1. Create a Self-Signed SSL Certificate and Private Key
https://trailhead.salesforce.com/en/content/learn/modules/sfdx_travis_ci/sfdx_travis_ci_connected_app#Tdxn4tBK-heading4


2. Create the Connected App
https://trailhead.salesforce.com/en/content/learn/modules/sfdx_travis_ci/sfdx_travis_ci_connected_app#Tdxn4tBK-heading5


    Important!  
    Be sure to copy down the consumer key—you’ll use it later


3. Edit Policies
https://trailhead.salesforce.com/en/content/learn/modules/sfdx_travis_ci/sfdx_travis_ci_connected_app#Tdxn4tBK-heading8


you can define individual variable to pass to shell script, other options are variable groups and azure key vault

Alternatively you can save a template for build and release pipeline to streamline the deployment process.
-export ci-cd

solution  
alternate things I tried in appendix

Resources

Trailhead Module
https://trailhead.salesforce.com/content/learn/modules/sfdx_travis_ci/sfdx_travis_ci_connected_app