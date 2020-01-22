# Development Models

As we alluded to in the overview, Salesforce development differs from traditional application development. The biggest difference between Salesforce development and your typical custom application development is that in custom application development, the code repository is always the source truth. With some recent changes released in Salesforce DX, you can begin to develop in a similar fashion. However, before we get ahead of ourselves, let's detail what's available from a development model perspective in Salesforce today. Salesforce supports three development models and each of these models places a different focus on the source of truth.

* Org Development Model
  * Source of Truth = **Production Org**
* Change Set Development Model
  * Source of Truth = **Combination of Metadata in the environment and last build of the changeset**
* Package Development Model
  * Source of Truth = **Metadata in the Package Project \(VCS\)**

For larger and more complex Salesforce development efforts, it's easy to imagine a team of 5-7 developers working away on a given feature set - with each developer touching a different portion of the application. Now imagine that same circumstance in each one of the models outlined above. It's easy to see that keeping track of changes across an active team of seven developers and moving those changes through environments manually could quickly become an unruly, tangled mess. When you get to this scale or larger, you'll likely want a more regimented approach that supports well-established software development best practices like test-driven development and continuous delivery; and the only model that currently supports this is the **Package Development Model**.

As an added bonus, the package development model supports the concept of modular development within Salesforce, allowing you to break apart large sets of functionality into smaller packages for smaller scoped and more controlled change management. We plan to explore this topic in-depth, but before we go any further - if you have questions or are unclear on Salesforce DX packages, or the different Salesforce development models and need more information, we suggest you investigate the resources listed below - as these concepts are foundational to the approach set forth in this guide.

## Resources

Trailhead Modules:

* [Org Developement Model](https://trailhead.salesforce.com/en/content/learn/modules/org-development-model)
* [Change Set Development Model](https://trailhead.salesforce.com/en/content/learn/modules/declarative-change-set-development)
* [Package Development Model](https://trailhead.salesforce.com/en/content/learn/modules/sfdx_dev_model)

