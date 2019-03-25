# Code Promotion

## Strategy

Code promotion is an important activity in a development effort, having a well documented approach to promote code once it's been reviewed and ready to move to production can yield greater team throughput. There are often a few steps along the way between development and production, this guide provides prescriptive guidance into what these could mean for your organization prior to reaching production.

* Individual Scratch Org
  * This is where all the work happens, each developer and quality assurance engineer works within their own individual Scratch Org. Developers concentrate on developing unit tests and adding/modifying functionality. Quality assurance engineers can develop automated tests and collaborate with developers in fabricating data to support functional changes.
* Integration Scratch Org
  * Once a team including both developers and quality assurance engineers feel confident a change is ready for testing, they move the updated package to an Integration Scratch Org, the act of moving the package to this Scratch Org will help test the deployment process and may uncover issues that the team can resolve. Quality assurance engineers can gate this environment preventing changes from moving forward until the quality meets organizational standards.
* Quality Assurance Sandbox \(Dev-Pro Sandbox\)
  * This environment is meant for full integration testing by the QA team, involving both automated and manual testing.
* User Acceptance Testing Sandbox\(Partial-Full Sandbox\)
  * This environment is meant to demonstrate the functionality to key business stakeholders and end users to confirm all functionality exhibits expected behaviors.
* Integration Sandbox \(Full Sandbox\)
  * This environment is a short-term stop, meant to test the package being installed into an environment that closely resembles production, and is meant to uncover installation errors. Lightweight automated browser testing is run here to ensure that the installation works without issues with production data.
* Production
  * Once in production, the package should work as expected and if not, should be easily reverted back to the prior version.

## SFDX: Moving Source & Data Between Orgs

After you convert from source format to metadata format and package metadata from one org, you can release your app in a different org. You can install this in production with `force:package:install`. You can specify tests to run after deployment and indicate whether to roll back the deployment if there are errors.

### Different Commands for Moving Source

**`sfdx force:source:deploy`**

* takes ‘things’ that are in DX format and sends them to an org without the requirement to test anything. It does not provide the ability to roll back the changes if they would not work, it just sends the data, overwriting existing things without regard.
* can’t determine a minimal deployment package to generate, so it deploys everything.
* used for moving metadata to sandboxes and production orgs, not scratch orgs

**`sfdx force:mdapi:deploy`**

* same toolset as a changeset to deploy data, so it has the same requirements and features \(rollback on error for example\) and may run tests before allowing the data to be deployed. The data for this needs to be in MDAPI format \(converted from DX via the `force:source:convert`command\) as it will look at what is in the package.xml file to determine what is supposed to be deployed.
* Since not everything can be put into a package yet, you may need to deploy some things via the MDAPI after you install a package
* **Note**: To support the needs of continuous integration and automated systems, the — rollbackonerror parameter of the `force:mdapi:deploy`command defaults to true.

**`sfdx force:package:install`**

* installs a packaged version of something. This can be an appexchange package or a DX package \(once that package is built using the `force:package:version:create` command. It needs a packageId \(starts with 04t\) or an alias from the local sfdx-project.json file as a parameter.
* Since not everything can be put into a package yet, you may need to deploy some things via the MDAPI after you install a package

**`sfdx force:source:push`**

* `force:source:push` only works on objects that are ‘trackable and in scratch orgs.
* Things that are in the ‘Source Tracking’ column here [https://developer.salesforce.com/docs/metadata-coverage/45](https://developer.salesforce.com/docs/metadata-coverage/45)
* The `source:deploy` command works differently from source:push for scratch orgs. The source you deploy overwrites the corresponding metadata in your org, similar to running `source:push`with the — force option. To deploy metadata that’s in the metadata format, use `force:mdapi:deploy`.
* `Source:push` and `source:retrieve` are used to keep the org and sandbox up to date in terms of branching. Source:deploy and source:retrieve are used to actually push the metadata to another sandbox / environment.

#### Working with package.xml

**The following elements can be defined in package.xml:**

* `<fullName>` contains the name of the server-side package. If no `<fullName>` exists, this is a client-side unpackagedpackage.
* `<types>` contains the name of the metadata type \(for example, CustomObject\) and the named members \(for example, myCustomObject\_\_c\) to be retrieved or deployed. You can add multiple `<types>` elements in a manifest file.
* `<members>` contains the fullName of the component, for example **MyCustomObject\_\_c**. The `listMetadata()` call is useful for determining the fullName for components of a particular metadata type, if you want to retrieve an individual component.
* For many metadata types, you can replace the value in members with the wildcard character \* \(asterisk\) instead of listing each member separately. See the reference topic for a specific type to determine whether that type supports wildcards.
* `<name>` contains the metadata type, for example **CustomObject** or **Profile**. There is one name defined for each metadata type in the directory. Any metadata type that extends Metadata is a valid value. The name that’s entered must match a metadata type that’s defined in the Metadata API WSDL.
* `<version>` is the API version number that’s used when the .zip file is deployed or retrieved.
* The manifest file defines the components that you’re trying to retrieve or deploy and the API version used for the deployment or retrieval.
* To delete components before adding or updating other components, create a manifest file that’s named **destructiveChangesPre.xml** and include the components to delete.

#### For SFDX Questions and Discussions

[Chatter Profile](https://success.salesforce.com/ProfileView?u=0053A00000EDjmFQAT)

-- Valerie Belova

