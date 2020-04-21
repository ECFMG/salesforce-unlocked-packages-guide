# VS Code Configuration

## Why Visual Studio Code?

Visual Studio Code \(VSCode\) is a free, cross-platform code editor with a strong plug-in community which extends its capabilities. Salesforce has created plug-ins to work with VSCode and has become the preferred editor for editing code with SFDX.

Visual Studio Code can be used by both developers and QA staff alike.

## VS Code SFDX Setup

#### Prerequisites

1. Java 8 Platform, Standard Edition Development Kit Some features in Salesforce Extensions for VS Code depend upon [Java](https://forcedotcom.github.io/salesforcedx-vscode/articles/getting-started/java-setup) \(Standard Edition Development Kit \(JDK\)\) 
   * The [AdoptOpenJDK](https://developer.salesforce.com/tools/vscode/en/getting-started/java-setup/#adoptopenjdk) is a recommended alternative to Oracle's Java which carries licensing fees.
2. GIT
   1. The [GIT Guide](https://help.github.com/en/github/getting-started-with-github/set-up-git#setting-up-git) from GitHub is a great resource for setting up and configuration GIT
      1. Mac Users - You may want to consider [connecting with SSH and adding SSH key to the SSH Agent](https://help.github.com/en/github/authenticating-to-github/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)
3. Install the Salesforce [CLI](https://developer.salesforce.com/tools/sfdxcli)

#### Download VS Code

Getting a workstation setup with VSCode and configured for Salesforce development is a straightforward approach, the steps below outline what is needed to perform regardless if the developer or quality assurance engineer is running on a PC or a Mac.

1. Download and Install Visual Studio Code
   * [https://code.visualstudio.com/download](https://code.visualstudio.com/download)
2. Install the official [Salesforce Extension Pack](https://marketplace.visualstudio.com/items?itemName=salesforce.salesforcedx-vscode#overview) into Visual Studio Code.

**Connect VS Code to Azure DevOps GIT Repos** 

[https://azuredevopslabs.com/labs/azuredevops/git/](https://azuredevopslabs.com/labs/azuredevops/git/)

## Salesforce SFDX Setup

Salesforce needs to be configured to enable SFDX. This is a one-time setup for the Developer org.

1. Setup [Dev Hub](https://developer.salesforce.com/docs/atlas.en-us.216.0.sfdx_setup.meta/sfdx_setup/sfdx_setup_enable_devhub.htm) and G2P in your Salesforce edition
   1. Navigate to Setup &gt; Settings &gt; Development &gt; Dev Hub
   2. Move the slider to enable Dev Hub and G2P Packaging
2. From a command prompt in Visual Studio Code issue `sfdx force:auth:web:login` to log into the Dev Hub using the CLI, which will authorize you to create scratch orgs.

## Additional VS Code Plugins for SFDX Projects

* [SonarLint](https://marketplace.visualstudio.com/items?itemName=SonarSource.sonarlint-vscode) - Provides realtime feedback on writing better code. 
  * Connects with [SonarCloud](https://sonarcloud.io/) \(free for public projects ~$10/mo for most Salesforce projects\)
  * [Details on how to configure SonarLint](../extras/sonarcloud-sonarlint.md#sonarlint-installation-guide)
* [Prettier](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode)  - Keeps code formatting consistent
* [C\#](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp) - For building Automated UI Tests with Selenium
* [XML](https://marketplace.visualstudio.com/items?itemName=redhat.vscode-xml) - Helps with working with XML Files

## VS Code Configurations

Automatically push code to org when saving:

`salesforcedx-vscode-core.push-or-deploy-on-save.enabled` to `true`.

## Resources

* [Salesforce Visual Studio Code Extensions Home Page](https://developer.salesforce.com/tools/extension_vscode)
* [Salesforce CLI Installation Instructions](https://developer.salesforce.com/docs/atlas.en-us.sfdx_setup.meta/sfdx_setup/sfdx_setup_install_cli.htm#sfdx_setup_install_cli)

Trailhead Module:

* [Quick Start: Visual Studio Code for Salesforce Development](https://trailhead.salesforce.com/content/learn/projects/quickstart-vscode-salesforce)

-- Valerie Belova  


