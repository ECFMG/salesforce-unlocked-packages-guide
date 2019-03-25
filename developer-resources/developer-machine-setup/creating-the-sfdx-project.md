# Creating the SFDX Project

### Creating a Project

Along with creating a repository for each package, an sfdx project should also be created for each package. The sfdx project along with the repository will live in the same directory. It's important to name the project after the particular package or feature that the team will be working on.

1. In VSCode, navigate to the top row, and select 'Terminal'. A new terminal window should appear at the bottom portion of the screen.
2. Type in the command `sfdx force:project:create --projectname "Name" --manifest` This will populate the directory with sfdx files
3. Authorize your provided org, using `sfdx:force:auth:web:login --setdefaultdevhubusername --setalias "Alias"`

* `--setalias` make is easier to access your org when running commands that push source to your org
* `--setdefaultusername` makes it so that org is the default org. If you don't specify an org when working with files or packages, they will automatically be pushed to the default org.

#### project-scratch-def.json

This json file will contain the instructions for scratch org creation. Normally, when you've authenticated an org, and you're ready to start developing you'll spin up a scratch org, push data into the org, and start developing. You can include thigs like edition, name, and features

* Edition—The Salesforce edition of the scratch org, such as Developer, Enterprise, Group, or Professional
* Add-on features—Functionality that is not included by default in an edition, such as multi-currency.
* Settings—Org and feature settings used to configure Salesforce products, such as Chatter and Communities.
* **Note:** For more information about the scratch org definition file: Visit [Here](https://developer.salesforce.com/docs/atlas.en-us.sfdx_dev.meta/sfdx_dev/sfdx_dev_scratch_orgs_def_file.htm)

**The First Scratch Org**

SFDX development is performed in a Scratch Org which is an empty local Salesforce environment.

1. Create a Scratch Org from project-scratch-def.json `sfdx force:org:create --definitionfile "config/project-scratch-def.json" --setalias "Alias"`
2. `sfdx force:source:push` to push the project source into the scratch org
3. `sfdx force:package:install --package` to install all of the packages into the org. Make sure to install in dependency order.
4. `sfdx force:user:permset: assign ---permsetname "Permission"` allows the scratch org to access data that is limited to the hub.
5. `sfdx force:org:open` to open up the project in your browser.

Unlike a sandbox, the Scratch Org will have no data in it when it is created. To ensure data is available in a Scratch Org to support the development and testing efforts data will have to be scripted in, fortunately, Salesforce provides capabilities to support this.

This is the basis for starting up a project. Scratch org management will be explored later in the wiki.

#### sfdx-project.json

This is the json file that describes all of the packages within your project. It's a useful place to refer to the packages in your org. Although, when you first create the project, this json file will only contain the force-app path. It's important to jot down the '0ho' IDs of packages in this file.

* To find package names and IDs, run `sfdx:force:package:list`
* **Note:** for more information about parameters you can specify in your sfdx-project.json file, click [Here.](https://developer.salesforce.com/docs/atlas.en-us.sfdx_dev.meta/sfdx_dev/sfdx_dev2gp_config_file.htm)

