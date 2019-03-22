## Project Overview: 

### Goals

The purpose of this wiki is to help traditional application developers transition into the world of SalesForce DX.  In traditional custom application development, you control the code, the database and the systems (in the event you leverage continuous integration/delivery) that package up and deploy your application; The good news is that with SalesForce DX, you still largely have all of those same features, they just exist in a slightly different flavor. 

Developing in SalesForce is fundamentally different from traditional custom application development in a number of ways. The biggest differences with the advent of SalesForce DX is that the deployable asset that we now move between environments across our SalesForce org is now a package. Rather than manually tracking changes and manually migrating them, (change-set style deployment) we can now build smaller focused components. These components work as a standalone SalesForce DX project, which can be versioned and packaged. These modules contain all of the code, data, and metadata needed for a successful deployment. This document should give you a good understanding of how all of this comes together, making developing in SalesForce DX a much more "developer-best-practices-friendly" environment.

### Who is this for?
It is important to understand that there are massive and varying scales of SalesForce implementations and that this approach may not be for everyone.  This is generally a better fit for large-scale enterprise Salesforce implementations. This approach should be fully understood and carefully considered before establishing it into practice. 

Martin Fowler has explored the [MonolithFirst](https://martinfowler.com/bliki/MonolithFirst.html) approach, and for many small scale companies, this approach may be sufficient. 

This guide is designed for larger, more enterprise-level teams looking to stand up and support a more complex Salesforce project that would likely benefit from concepts like continuous integration and a more structured, component-based, development paradigm.

### Resources
Before beginning, it may be a good idea to go through [this trailhead trail](https://trailhead.salesforce.com/content/learn/trails/sfdx_get_started). It takes you through the fundamentals of SFDX, so that you can gain an understanding of the general processes, and terminology that comes with using sfdx.

### How can I contribute?
The authors of this guide are welcome to feedback and have built this from a lack of guidance available.

Please feel free to add [issues](https://github.com/ECFMG/salesforce-unlocked-packages-guide/issues) or send updates via pull requests.



### Collaborators
* [Valerie Belova](https://github.com/valbelova)
* [Dhaval Heruwala](https://github.com/heruwala)
* [Mike Mocarski](https://github.com/mmocarski72)
* [Patrick Gidich](https://github.com/gidich)
