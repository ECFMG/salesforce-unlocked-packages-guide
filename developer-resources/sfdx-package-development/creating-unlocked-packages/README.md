# Creating Unlocked Packages

### Creating and Configuring Unlocked Package

Managing packages in their sfdx-project.json file is a vital part of the development process. The process of involving dependencies, versioning, and installation can all become very confusing. This page breaks down the process in a digestible way, so that you can easily create, version, and install packages.

**Package Version Numbers:**

* NEXT: increment the build number to the next available for the package
* LATEST: assign the latest version of the package

**Dependencies**

* By default, when referencing a certain Standard Object, field, or component type, you will generate a prerequisite dependency on your package

**Package Installation Key:**

* ensures the security of the metadata within the package. Authorized Users are then provided the key
* Provide -k \(installation key\) when running `sfdx force:package:version:create`. This key must be supplied when installing the package in an org.
* Installation keys can be changed by running `sfdx force:package:version:update`

**NameSpaces**

* Distinguishes your package and its contents from packages of other developers
* Creating a "no namespace" package gives developers more control over how to organize and distribute parts of an application. Existing unpackaged metadata can be migrated only to an unlocked package with no namespace.

#### Creating the Package

**Generate**

* `sfdx force:package:create`
* Make sure you specify the -name, -packagetype, -path, and -description. 
* specify feature and org preferences for the metadata in your sfdx-project.json

**Release**

* `sfdx force:package:version:create`
* Make sure you specify the -package, -installationkey, -wait, and any optional variables you wish to update
* Use the "-b" flag to specify a build on a "logical branch". This flag allows you to keep experimental/development builds separate from the "main stream" builds that would be generated from your GIT MASTER branch

**Install**

* `sfdx force:package:install`
* Make sure you specify the package version by running `sfdx:force:package:version:list` to find its 0Ho ID.
* Install packages in order of dependencies

### Best Practices

* Include the -tag option when you use the `package:version:create` and `package:version:update` commands. This option helps you keep your version-control system tags in sync with specific package versions.
* Keep your sfdx-project.json populated with important information such as versions, name, build, aliases, etc. This is your source of truth for all packages.
* use -wait when creating package versions. This helps you avoid the process of having to run sfdx `force:version:report:create` in order to view your package's status.
* Don't version every little feature or change. Your org has a maximum number of package commands you can run.
* Avoid namespaces if you aren't accustomed to them
* Specify PermissionSets within your packages
* Refer to the [CLI Command Reference](https://developer.salesforce.com/docs/atlas.en-us.sfdx_cli_reference.meta/sfdx_cli_reference/cli_reference.htm) when running sfdx commands
* Refer to the [Scratch Org and DevHub Reference](https://medium.com/@heruwala/salesforce-source-driven-development-and-scratch-org-2ccaccbcb191) when using Scratch Org
* Adopt a robust .forceignore file to avoid pulling down unwanted metadata
* Have developers religiously refer to the [Metadata Coverage Report](https://developer.salesforce.com/docs/atlas.en-us.sfdx_dev.meta/sfdx_dev/sfdx_dev_supported_mdapi_types.htm) to avoid packaging metadata this is incompatible with packaging.

