# Create/Reset/Manage Test Data



**Test Automation - Create/Reset Test Data:**  
  
This document depicts the complete end-to-end flow of the data creation and resetting to utilize the data as part of test automation and execution in Scratch Org in SalesForce. The "Data" folder will be created upon creation of the unlocked packages\(Future state\) and therefore the team can able to create the data for each feature component and host in JSON format in the "Data" folder. The process of consuming the test data has been documented below.

1. Create and place the data in JSON format for each business feature in "Data" folder of the Master Branch.
2. Create a repository of the "Feature Branch" from the Master Branch.
3. The "Feature Branch" should have the following folders present.   a. Function Automation Folder - Where the functional test automated scripts\(using Selenium\) reside.   b. The "Data" folder where the test data resides in JSON format for each business feature.
4. Create a Scratch Org in SalesForce.
5. Copy the "Featured Branch" into the Scratch Org.
6. Develop/Update the test automated scripts for the "Featured Branch" in the Scratch Org by utilizing the test data from the "Data" folder for all the business features required.
7. Copy the updated scripts and data from "Feature Branch" to the "Master Branch" using the SFDX pull request.
8. Ignore the "Functional Scripts" and "Data" folders by mapping the folders path in the .forceignore file in Git before deploying into the DEV, QA and UAT sandboxes.

