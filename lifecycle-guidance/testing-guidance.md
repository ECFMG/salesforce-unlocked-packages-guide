# Testing Guidance

## QA Automated Testing and Developer Unit Testing

When you're ready to move your code to the next step of the development process, it's important to have rigid testing decisions in place. Each environment is going to be associated with different types of testing. We also introduce a concept called Apex Testing. The programming language that salesforce uses is called [Apex](https://developer.salesforce.com/docs/atlas.en-us.apexcode.meta/apexcode/apex_intro_what_is_apex.htm), and any unit tests used will be written in Apex. The Apex testing framework makes it easy to test your Apex code. The Apex testing framework enables you to write and execute tests for your Apex classes and triggers on the Lightning Platform. Apex unit tests ensure high quality for your Apex code and let you meet requirements for deploying Apex.

We'll explore that further in this page.

### SFDX Testing Decisions

* Unit Tests and Apex Tests: Scratch Orgs
* QA Feature Tests and Regression Tests: Dev-Pro Sandbox
* Staging and user-acceptance testing: Partial-Full sandbox

### Tasks

1. Create Developer Environments
2. Develop using the web and local tools
3. Migrate changes to the integration environment
4. Test
5. Migrate changes to UAT environment
6. Perform user-acceptance testing
7. Migrate changes to the staging environment
8. Replicate production changes in the staging environment
9. Schedule the release

#### Apex Unit Test Flow

1. Authorize Dev Hub
2. Create Scratch Org
3. Install package / push source
4. Run Tests
5. Delete Org
6. Create / Send Report

#### Test Requirements in Production

1. 75% of Apex statements must be executed \(strive for 100% code coverage\)
2. All Apex triggers must be called. 
3. All Apex tests must execute without throwing any uncaught exceptions or exceeding governors.

Best Practices:

* Arrange the data correctly, act on it, and assert to make sure your code is doing what it should be doing
* Run tests as real user profiles
  * `Sfdx force:user:create`
* Exercise bulk trigger functionality
  * Can be called with more than one object-- aim for 10-20.
  * Aim to make sure it 'works' - not to test limits
* Plan ahead Refresh your sandbox when it makes sense for the project
* Build-in Assert methods into your test
  * System.Assert\(expect, actual, 'friendly message'\)
    * Helps you find what went wrong in test failure
* Use Test.startTest and Test.stopTest commands. Gives you a new set of governor limits, and runs any asynchronous code
* Write Positive Tests
* Write Negative Tests
* User tests
  * Create a user with a given profile, and assign permissions to them
* turn off seeAllData. This ensures you don't get random failures if data changes
* Do not install LTS in a production org. Lightning tests don’t run in an isolated testing context, and DML operations you perform in a test are not rolled back when the test completes.

#### Sample Flow

* Bob the Builder just developed a feature and he sends it to the develop branch. QA tester, Oscar, pulls into his environment, and runs the script that creates a scratch org and runs the apex tests. Next, he pushes the application to the Partial Copy Sandbox, and runs his regression and features tests in the sandbox. When Oscar feels like the application passed all his tests, he then pushes to the Full sandbox for UAT testing.
* Tester Megan Goes into the Full Sandbox, and goes about UAT testing. She spins up some user accounts and works on using the application. When she feels like the application passes her user tests, she sends it off to the production org. This happens after the packages have been updated and installed.
* Carl, QA tester, is testing the application when the apex code coverage reaches 70%. The application cannot be passed further, so he lets the developer know, and deletes his scratch org.

#### Resources

* [Apex Testing Trailhead](https://trailhead.salesforce.com/en/content/learn/modules/apex_testing)
* [Apex Developer Guide](https://developer.salesforce.com/docs/atlas.en-us.apexcode.meta/apexcode/apex_testing.htm)

-- Valerie Belova

