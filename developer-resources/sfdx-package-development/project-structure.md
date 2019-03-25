# Project Structure

## Introduction

### Packages as Projects

The codebase of the Salesforce org should be broken into multiple projects, this allows each unlocked package to be worked on independently.

#### Package Structure

**Project Configuration**

Each unlocked package "project" needs to contain its own `sfdx-project.json` file which defines all the details about an unlocked package.

Project Details:

* Filesystem Structure
* SFDX Plugins
* Namespaces

**Loading Sequence**

When you create a new scratch org, you need to install all of the dependencies into the scratch org first, then you push the data for the package. DX will recognize that it only needs to track the data of a certain package with the push/pull since the other data are part of other packages. This does require that the other packages are actually built into packages before working on this \(using the `force:package:version:create` command\).

If for example, you are a developer in Repo2, and you're working on Package2 for the project. Your Package2 could be dependent on Package1, which is housed in a different repo, and controlled by a different developer.

### Configuring the sfdx-project.json File for Dependent Packages

You simply need to tell the Package2 that it depends on the Package1 in the sfdx-project.json file that defines the package.

1. Create Package2 in its project using `sfdx:force:package:create` command, and specify its path and settings assuming all of the code exists. List Package1 as a dependency. 
2. If you attempt to version, you'll get the following error: Package1 isn't defined in the sfdx-proect.json. Add it to the packageDirectories section and add the alias to packageAliases with its 0Ho ID. 
3. In the sfdx-project.json, create a Packagedirectory for Package1. Specify the path as a dummy path \(such as force-app\). Fill the versionName, and versionNumber fields with information found in step 2.
4. Navigate to your org's "Installed Packages" list, and find Package1. Jot down the versionName and versionNumber, and fill the those fields in the sfdx-project.json of Package1 Project.
5. Run `sfdx:force:package:list` to list all of the packages in your org from the CLI. Copy down the name, and '0Ho' ID of Package2, and enter it as a field in packageAliases.
6. You should now be able version your Package2 using `sfdx:force:package:version:create` with its dependencies linked to Package1.

Even within a package, each programmer would create a branch of the VCS and then work on a section of code in their own scratch or. When they are ready, they can check the code in, and then merge it with any other changes \(easier if each developer is working in different classes\). The same thing applies to workflows, process builder, page layouts, etc. Create a branch, work in a scratch org, check in changes, merge, and repeat.

It's important to create a 'base' package that contains all of the things that will need to be shared across the other parts and the dependent packages on top of that\(Package1\). Each subsequent package would have its own repository. In the base package would be any custom objects that are needed and any custom fields for standard objects that relate to the widgets. Also, **include permission sets that provide access to the data**. Then you can build the Package2 and Package3 packages and define that they depend on the base package \(since that is where the data is defined\). In the Package2 and Package3, you would add any code, workflows, lightning applications, components, etc that are needed to provide service for widgets. This allows you to work on Package2 and Package3 independently and install/removed/update each in production as needed without working about stepping on each other's toes.

The great thing about Salesforce DX, is that packages are released independently, and are stored in the Org. Packages can be accessed and used by developers that don't have access to the source code.

## Parallel Development in Salesforce: A Modern Approach

![](https://camo.githubusercontent.com/5a14cc435e56e6698a766b8741a3f120b441ced1/68747470733a2f2f63646e2d696d616765732d312e6d656469756d2e636f6d2f6d61782f313030302f312a644e646f493035336e572d734776663765315a6b56512e6a706567)

## Resources

* [SFDX Package Development Model Trail](https://trailhead.salesforce.com/content/learn/modules/sfdx_dev_model)
* [Package Dependency Visualization Tool](https://github.com/afawcett/dependencies-cli/wiki/How-to-untangle-an-Org-into-Packages)

-- Valerie Belova

