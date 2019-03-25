# Package Errors

When working with package commands, it's not unlikely to run into errors and issues. Here is a compilation of common errors that may occur, along with solutions to those errors.

### Common Package Errors and Fixes

**The package ID or Alias ID is invalid OR The subscriber version ID or package version ID isn't defined**

* The package version ids may be specific to a DevHub that does not allow them to be installed in another company's environments. This can happen on open source projects where the package IDs and version IDs are listed in the packageAliases section of open source SFDX projects
* To fix this, you would need to remove all of the IDs of packages and versions you have not created, and re-package them for yourself. Add your own IDs to the local sfdx-project.json

**"Package" isn't defined in the sfdx-project.json. Add it to the packagedirectories section and add the alias to packageAliases with its 0Ho ID.**

* Same problem as above. Your own DevHub doesn't recognize the packages that were created and versioned in another DevHub

**It's possible that the package was created on a different Dev Hub. Authenticate to the Dev Hub org that owns the package, and reference that Dev Hub when running the command**

* Same as problems from above. You have to recreate all of the packages from your own DevHub, and reference those IDs only.

**This Directory does not contain a valid Salesforce DX project**

* This happened if I tried to edit in a path that wasn't correct. Sometimes, when I opened a project, VSCode would open up the repo without the correct path. To fix this I just did "cd .\InsertFolderNameHere"
* Always double check that you are working in the path where your SFDX project is located

**Path must be a string, received null**

* It fixed itself when I edited the contents within the package directory folder, and then restarted VScode.I assume it's because a path is considered empty / doesn't have enough contents for a proper package.

**Expected path**

* This error occurred when I tried to version a package, and the path I referred to was different than the path in the sfdx-project.json file. It has to be exactly the same. I refereed "./forceapp1" in my command, however, in the file, it was just "forceapp1" without the "./"

**Package Root directory empty**

* This occurred when I created a package, and the folder for the package directory was empty. When I created an empty file inside of the directory and entered in a few random lines of cold, the error went away.

