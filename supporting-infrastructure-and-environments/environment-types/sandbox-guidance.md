# Sandbox Guidance

## Sandboxes: Create, Clone, and Edit

A sandbox is a copy of your production organization. You can create multiple copies of your organization in separate environments for different purposes such as development, testing, and training, without compromising the data and applications in your production organization. Different types of sandboxes have different refresh intervals, meaning they cannot be replaced for a set amount of days. It is important to be mindful of which sandbox is being used for which process. This guide explores basic sandbox information, and practices.

### Sandbox General Information

**Note From QA Strat:**

* Unit Tests and Apex Tests: Scratch Orgs
* Feature Tests and Regression Tests: Dev-Pro Sandbox
* Staging and user-acceptance testing: Partial-Full sandbox

**Developer Pro Sandboxes**

* Have a refresh interval of 1 day
* 1 GB limit
* Only Metadata is copied
* No sandbox template

**Partial Full Sandboxes**

* Have a refresh interval of 5 days
* 5 GB limit
* Metadata and sample data is copied
* Has a sandbox template \(required\)

**Full Sandboxes**

* Have a refresh interval of 29 days
* Same storage limit as production org
* Metadata and all data is copied
* Has a sandbox template \(optional\)

### Important Practices

* Give Manage Sandbox permissions to a user to allow them create, refresh, activate, or delete a sandbox
* Give Setup and Configuration permissions to a user to allow them to view a sandbox
* Monitor the storage of each sandbox to ensure you don't throw too much into it
* Refresh a sandbox before you plan to work on or test new changes in it
* Make sure you don't refresh or delete a sandbox until you're sure that you're finished the work you have to do in it. Be mindful of the refresh intervals.

#### Creating a Sandbox

1. Setup -&gt; Sandboxes in Quick Find
2. Click 'New Sandbox'
3. Enter a name \(Such as 'QA'. The fewer characters the better
4. Select the type of sandbox you want
5. For a Partial Copy or Full sandbox, decide the type of data you want in the sandbox a. Partial: click next, select the template b. Full: click next, select how much data to include\(or choose a template\)
6. To run scripts after each create and refresh for this sandbox, specify the Apex class you previously created from the SandboxPostCopy interface.

#### Creating Sandbox Templates

1. Setup -&gt; Sandboxes in quick find -&gt; sandbox templates
2. New Sandbox
3. Enter a name and description
4. Select checkboxes for each object you want from the available objects list
5. Save

#### Refreshing a Sandbox

1. Setup -&gt; Sandboxes in quick find
2. Next to the name of sandboxes there should be a refresh link, click it
3. Review the name, values, and description
4. Select the type of environment you want
5. If you want your sandboxes activate immediately after refresh, select Auto Activate
6. Click Create

#### Cloning a Sandbox

A sandbox can be cloned to save time. Instead of pulling source from the production org, you can replicate the data. Sandbox cloning simplifies having multiple concurrent streams of work in your application life cycle. You can set up a sandbox for each type of work, such as development, testing, and staging

1. Set up -&gt; Sandboxes
2. Click Clone
3. Enter a Name
4. confirm that the sandbox name selected in the Create From dropdown is the sandbox you want to use as your source org. Click Next, then Create

#### For More Information Regarding Sandboxes:

Salesforce's Sandbox Guide & Documentation: [Here](https://help.salesforce.com/articleView?id=create_test_instance.htm&type=5)

