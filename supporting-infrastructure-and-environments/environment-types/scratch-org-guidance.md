# Scratch Org Guidance

## Management of Scratch Orgs

The scratch org is a source-driven and disposable deployment of Salesforce code and metadata. They are great for temporary deployments, peer review, enhanced test coverage, and automation.

**You might spin up a new scratch org when you want to:**

* Start a new project
* Start a new feature branch
* Test a new feature
* Start automated testing
* Perform development tasks directly in an org
* Start from “scratch” with a fresh new org
* conduct user acceptance testing or to test installations of packages

#### Pushing Source to the Scratch Org

You can use `force:source:push` for scratch orgs only. If you’re synchronizing source to another org, use the Metadata API. The push command doesn’t handle merges. Projects and scratch orgs are meant to be used by one developer. Therefore, we don’t anticipate file conflicts or the need to merge.

**To push changed source to a scratch org that’s not the default, you can indicate it by its username or alias:** `sfdx force:source:push -u "Username"`

#### Selecting files for push to ignore:

It’s likely that you have some files that you don’t want to sync between the project and scratch org. You can have the push command ignore the files you indicate in .forceignore.

**Where to Put .forceignore**

* Be sure the paths that you specify in .forceignore are relative to the directory containing the .forceignore file. For the .forceignore file to work its magic, you must put it in the proper location, depending on which command you are running.
* Add the .forceignore file to the root of your project for the source tracking commands
  * `force:source:push`, `force:source:pull`, `force:source:status`, and `force:source:convert`
* Add the file to the Metadata retrieve directory \(with package.xml\)
  * `force:mdapi:convert`

