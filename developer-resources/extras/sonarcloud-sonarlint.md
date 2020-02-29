# SonarCloud / SonarLint

## SonarLint Installation Guide:

_Prerequisites_: 

* [VSCode](https://code.visualstudio.com/) with [Salesforce Extensions](https://marketplace.visualstudio.com/items?itemName=salesforce.salesforcedx-vscode) installed, [configured and connected](https://trailhead.salesforce.com/en/content/learn/projects/quickstart-vscode-salesforce) to both Azure DevOps and your ScratchOrg.
* A SonarCloud account \(Free for public projects / ~$10mo for most Salesforce projects\) - with a  project set up which will be used for the SFDX code analysis, note the projectKey as it will be used in step 14.

Configuration Process:

1. Install the [SonarLint Extension](https://marketplace.visualstudio.com/items?itemName=SonarSource.sonarlint-vscode) into VSCode, and restart VSCode
2. Open your VSCode project related to your ScratchOrg
3. Visit [SonarCloud](https://sonarcloud.io/) and log in using the **Azure DevOps** button.
4. Visit [your security page](https://sonarcloud.io/account/security/)
5. Under the section titled **Generate Tokens**, enter `vscode` and click the **Generate** button.
6. You will get a new token, copy the token value secure location we will use it later and you will not be able to retrieve it once it is generated.
7. Open Visual Studio Code, and navigate to the setting section
   * On Windows/Linux - File &gt; Preferences &gt; Settings
   * On macOS - Code &gt; Preferences &gt; Settings
8. Select User Settings and Search for SonarLint
9. Ensure that you select **User** directly under the search box so that you are configuring user settings.
10. Pick any of the settings and click \*\*Edit in settings.json
11. Paste the following into the settings.json file

    ```text
    "sonarlint.connectedMode.servers": [
     {
     "serverId": "<<YOUR COMPANY NAME>>", 
     "serverUrl": "https//sonarcloud.io", 
     "organizationKey": "<<YOUR COMPANY NAME>>",
     "token": "<<YOUR VSCODE TOKEN GOES HERE>>" // UNIQUE PER USER, DON'T SHARE WITH OTHERS
     }
    ],
    "sonarlint.connectedMode.project": {
     "serverId": "<<YOUR COMPANY NAME>>",
     "projectKey": "<<YOUR PROJECT KEY>>",
     "language": "apex"
    },
    ```

12. Replace the &lt;&lt;YOUR VSCODE TOKEN GOES HERE&gt;&gt; with the _token_ you created earlier.
13. Replace the &lt;&lt;YOUR COMPANY NAME&gt;&gt; with your _organization key_ 
    * You can look up the _organization key_ on the [organization key page](https://sonarcloud.io/account/organizations).
14. Replace the &lt;&lt;YOUR PROJECT KEY&gt;&gt; with your _project key_.
    * You can look up the _project key_ under Administration &gt; Projects Management on your organization's page.
15. Restart VSCode and reopen your VSCode Project related to your ScratchOrg









