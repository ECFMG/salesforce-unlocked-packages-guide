# Introduction

## Introduction

Unlocked Packages provide the ability to divide a Salesforce org into components that can be versioned and deployed independently. Unlocked packages include metadata \(both code and configuration\).

> Unlocked Packages enable "Source Code as the Source of Truth"

There is a balance that needs to be defined between making package sizes small enough that changes can move quickly through the development process, but not so small that any change requires multiple packages to need to change.

The following guidance details an approach to structure packages in a manner that best strikes this balance.

### Package Categorization

_**Breaking up your "Happy Soup"**_ The following provides guidance on how to organize the org into SFDX Packages:

#### "Base" Packages

Base packages can be thought of as holding custom objects and providing data that other packages may depend on. It's important to know that packages can have dependencies, so common functionality should be pushed downwards into these base packages to promote reuse.

* Common interfaces
* Standard Salesforce SObjects
* object-level metadata
* UI Libraries \(including common Lightning Components\)
* Custom objects
* Page layouts
* Custom list views
* Custom or standard fields

#### Dependent Packages

A package can be dependent on one or more packages. Normally, the more components you include in later packages, the more packages you would have to reference. For example, if you have a package whose code references 3 other packages, those would have to be listed as dependencies. In these types of packages, you can have components such as:

* Apex Services
* Shared Lightning Components
* Custom Page Templates
* Theme images
* Tabs
* Permission Sets

### Package Decomposition

#### Breaking Down Metadata Across Packages:

* A group of related code and customization
* Can be tested independently from other components in your org
* Able to be released independently
* Source components can only live In one project at a time
* Object-level metadata should be kept in a base class.
* Make sure your base class doesn’t account for other shared metadata
* You don’t have to break up data without a reason
* If there are deeply intertwined dependencies, include those together.
* If functionality would be useful to future apps or other parts of the org, maybe consider moving the metadata elsewhere
* There is no objectively-right method for breaking up metadata
* Very subjective, should match working styles of team

**Things that don't work**

* Shared metadata
* Shared Objects

**Note:** Use dependencies instead, and reference back to the metadata and objects.

For Questions and Collaboration: [Chatter Page](https://success.salesforce.com/ProfileView?u=0053A00000EDjmFQAT)

## Resources

Salesforce Trailhead:

* [Quick Start: Unlocked Packages](https://trailhead.salesforce.com/en/content/learn/projects/quick-start-unlocked-packages)

-- Valerie Belova

