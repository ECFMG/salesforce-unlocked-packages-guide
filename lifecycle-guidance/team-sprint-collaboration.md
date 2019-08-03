---
description: Unlocking the Package Development Model with Unlocked Packages
---

# Team Sprint Collaboration

![](../.gitbook/assets/image%20%282%29.png)

We previously explored the different development models supported by Salesforce, we are now going to take a deeper dive into the Package Development Model and how, with Salesforce DX and Scratch Orgs, larger size development teams can reap benefits and be more productive.

The diagram above showcases an approach where a large scale development teams with multiple development streams are happening simultaneously. The diagram will be explored in detail below, showcasing how unlocked packages help to isolate changes and provide for a modular approach to promoting change.

## Scratch Org Development Approach

Scratch Orgs are small, temporary and personal,  this is perfect to support sprint development, ensuring that each sprint begins with a clean slate, automated tests can run with known data, and no one steps on each other.

Leveraging personal Scratch Org instances a development team consisting of developers and quality assurance staff can work together on a feature branch. The feature branch can contain not only DX source code, but also data and automated UI tests. The team can share changes between team members through source control, and GIT is a great SCM to enable this for teams.

### Shift-Left Testing Nirvana

QA Engineers can help drive the creation of data to support the development of new features and functionality which can also support validation of user stories through automated UI scripts. Automated UI testing can be run by developers during development to both validate the work they are doing but also to confirm tests are complete and accurate. Collaboration between developers and testers to ensure quality fully automated UI tests and unit tests prove user story completion, not only at the time of development, but also can help considerably to support regression testing with the 3x yearly Salesforce releases, where organizations need to quickly validate the new release and address all issues within a 30-day window.

### Deployment Testing 

Testing the deployment of an Unlocked Package is extremely important, not all functionality is covered under metadata under source control and deployment testing will help to catch any functionality missed when using DX based deployments.

## Pull Request Quality Gating

Quality is important to any team, and the pull request has become a standard approach to initiate a conversation about the intent to merge code and promote to higher environments. Pull requests are a great mechanism to initiate a quality gate, both through automated tools like static code analysis and manual approaches as a code review.

## Validation and Deployment

Real world data volumes and performance characteristics cannot be achieved in a scratch org and need to be relegated to Sandboxes where data limits are much higher and performance is more representative of production systems. Sandboxes are also great environments to use for UAT allowing business users to interact with datasets which more closely represent data they work with on a daily basis.



   

