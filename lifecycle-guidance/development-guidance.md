# Development Guidance

### Overview

As we established early on, developing in SalesForce is fundamentally different from traditional custom application development. With SalesForce DX, the primary deployment asset is the package you create. It simplifies the whole deployment in that it contains everything your component needs to work in the production org; The package is based on the code in Git which is versioned and the package itself will also be versioned - no room for anything to get lost. This is all good stuff, but what does it mean for our developers? How do they navigate this new model? The purpose of this page is to outline how we anticipate handling this new paradigm and give some insight as to what parts of the process are automated and what will involve intervention from the developers and team leads.

### Developer Machine Setup

This has been outlined here for more information: [VS Code Setup](https://ecfmg.gitbook.io/sfdx-unlocked-packages-guide/developer-resources/developer-machine-setup/vs-code-configuration)

### Work Initiation

At the start of any project \(feature development\), there should be a kick-off meeting where the developers get the chance to question the business analysts and project managers about the work being requested. There will be some high-level design needed to understand and assess what SalesForce DX package\(s\) will be affected by the business request and then an impact analysis and rough estimate can be given. Being as we are agile, we should then create a backlog of all of the work required to deliver the requested feature and prioritize the work items for our initial few sprints. As part of a "sprint 0" effort, there are a few "scaffolding" type steps we need to get in place before the work can begin - these are as follows:

1. New SFDX Project Development:
   * Creation of the initial AzureDevOps repository for the SFDX project along with the required branches - this should probably be handled by your team lead, but the role here is completely up to you and your team.
   * Creation of initial SalesForce DX project for the component - this should be created by your team / project lead as the structure of the project and any dependencies should be considered from the start of the project and who would be better than your team lead to set that up.
     * Instructions for creating the SFDX Project: [Detailed Here](https://ecfmg.gitbook.io/sfdx-unlocked-packages-guide/developer-resources/developer-machine-setup/creating-the-sfdx-project)
     *  Here is a good example of a modular App where the project packages are decomposed in their own Repos which empower individual development team to manage the development of the packages independently. The overall project structure looks like this:

        Easy Spaces App

        [ES-Space-Mgmt](https://github.com/ECFMG/ES-Space-Mgmt)  
        -[ES-Base-Objects](https://github.com/ECFMG/ES-Base-Objects)  
        -[ES-Base-Styles](https://github.com/ECFMG/ES-Base-Styles)  
        -[ES-Base-Code](https://github.com/ECFMG/ES-Base-Code)

       * [SFDX Complex Project Template](https://github.com/ECFMG/sfdx-falcon-template) - a good template to use, instructions in link
   * Creation of initial CI/CD AzureDevOps pipeline - ideally, to help the work flow smoothly all members of the team should know what's involved in creating a pipeline to avoid bottlenecks, but a central role, primarily the team / project lead should handle this initial setup.
     * Detail steps to create new CI/CD pipeline outlined [here](https://github.com/ECFMG/salesforce-unlocked-packages-guide/blob/master/salesforce-dx-and-ci-cd/pipeline-introduction.md)
2. All SFDX Project Development:
   * Creation of a feature branch off of development for the newly defined effort - your team lead or repository / project owner should handle the branch creation since they will also handle the merging & tagging of future production releases, so ensuring the branches are created correctly is important.
     * Data design session: Assuming we will be needing data for a given feature, we should first look into how we will need to structure the data to support it. Out of this session, we will deliver the following:
   * Data structure impact analysis: Impacts to existing data types & detail any new data types.
   * Initial data scripts to populate the data for test purposes.
     * **NOTE:** This may be deferred to a later sprint as we may not know all of the static / test data needed at the outset, but we should at least log the effort - as it will be needed to get the work to a test environment and this work should be captured.

#### Development Flow: Can be merged with below?? (Dhaval Tested this flow)

Personal / Feature Branch  

1. developer creates a package (One time setup)

Develop Branch  

2. developer creates version & updates .sh with stable version  
`$ cd/packagingDeployment.sh package MyScratchOrg`
3. commits to develop branch  

Package Branch  

4. Merge Develop changes to package branch  
`$ git checkout Package`  
`$ git merge Develop`  
`$ git push`
5. package branch build is picked up
6. waiting for QA to approve and goes to QA
7. QA approves, build deploys in QA org
8. QA completes testing
9. QA gives a final go
10. A tag is created in pakage branch by a technical person in package branch after a final review  
    `$ git tag -a UAT-v0.1.0.9 -m "This is the latest UAT version"`  
    `$ git push --tags`
11. a technical person also approves the UAT deployment approval email
12. UAT deployment kicks off and completes in few minutes.
13. Users completes acceptance testing in UAT and preparation for Prod release begins.
14. App development manager creates a pull request to master  

Master Branch  

15. App development manager approves pull request as well as approves deployment request
16. App manager creates a tag is in master branch for the prod release  
`git tag -a Prod-v0.1.0.9 -m "This is the latest Production version"`  
`git push --tags`
17. CD deploys the package goes to prod

### Development Process

Once we've done the initial setup to enable the work \(code repository & branches, project scaffolding, and any relevant data scripts\), you'll now have all you need in place to begin developing your SFDX project feature. To help illustrate the steps you'll need to do, as a developer, in your day-to-day routine - we'll walk you through a sample scenario below:

1. As you start your day, you open up AzureBoards and review the open tasks for your current sprint. You pick one off of the stack, read the details of what's required and make a personal branch off of the feature branch \(because this should already exist as part of Sprint 0\) for the current project your on \(all of this information should be readily available from your team / project lead\)
2. Once you have created your personal branch, you can begin development against the code & author your unit tests. You will write whatever classes you need and use the SFDX CLI to deploy your changes to your own personal scratch org to test the changes out.
3. Once your changes work properly in your scratch org, and your code is committed to your personal branch, your unit tests are written \(to the agreed upon test coverage amount\), have whatever static test data needed added to your data script, and think it's good enough to submit for testing - create a pull request to merge the changes in your personal branch into the feature branch.
4. Depending on your development teams policies are, either your team lead or your peer, will then review your pull request locally, test in their own personal scratch org, and if things check out, they'll merge your change into the Feature branch for others to now see - if there's an issue with your pull request, the team lead will comment on it in the pull request and provide direction as to how to correct any issues preventing the pull request from being merged; you'll then correct those and re-submit the pull request which should now be correct and ready to merge.
5. At a milestone to be determined between your development lead and QA, there will be a new package made for release to QA / Testing. The process of creating a package isn't terribly difficult, but to streamline the process we have created a script to encapsulate the steps and provide a more consistent package creation process. The script is available [here](https://github.com/ECFMG/ES-Space-Mgmt/blob/master/cd/packagingDeployment.sh)
6. Once the new package is created, it should be committed to the package branch for the specific feature you are creating. From this point, the CI/CD pipeline in AzureDevOps will pick up the change in the package and use this package to deploy to our QA environment automatically.
7. The AzureDevOps pipeline will run all of the unit tests and a security scan via PMD [https://pmd.github.io/latest/pmd\_userdocs\_installation.html](https://pmd.github.io/latest/pmd_userdocs_installation.html) to ensure that what it is attempting to deploy to QA is not introducing any security risks or breaking any pre-existing \(or new\) unit tests so that we have a fair confidence that will not break the environment as part of this automated deployment - our goal here is to keep all environments, even QA, as stable as possible.
8. Assuming the deployment runs successfully and the SFDX package is deployed to the QA org, testing of the new feature can now begin. From here, as issues are identified, the development & issue resolution cycle begins and is simply a repeat of the steps to get to this point \(add feature / fix issue, commit code, submit & review pull request, merge, package, CI/CD automated build, QA test, etc.\)
9. After we have formal sign off on the stability and completeness of the package released to QA, we may now migrate this package to UAT / Pre-Prod for final testing. This is done by performing steps 10-13 as described above.
10. Finally, after we have formal sign off on the UAT / Pre-Prod environment, we move the package to our production org by tagging the version of the package that is ready for production by first merging that version from package down into the master branch and then tagging it \(our currently recommended trigger for firing off builds - though it can be done via many other ways\).