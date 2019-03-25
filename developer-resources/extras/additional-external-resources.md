# Additional External Resources

### DevOps Resources

* [Salesforce DX Community Group](https://success.salesforce.com/_ui/core/chatter/groups/GroupProfilePage?g=0F93A000000HTp1)
* [Salesforce CLI release notes](https://developer.salesforce.com/media/salesforce-cli/releasenotes.html)
* [Kitchener Salesforce Developer Group Event: Introduction to DevOps with Salesforce DX](https://youtu.be/jt_AB3g6mb4)

### Architectural Design Patterns

#### Domain Layer - Domain Driven Design  / Anti Monolith

It is desirable to segment the codebase into business domains that are not interdependent so that each business domain can evolve at its own rate and change can be isolated and changes moved to production independently.

In a microservices driven architecture there are significant advantages of ensuring that each microservice own the data that it interacts with and that no other microservice interacts with another's data directly. The net result allows microservice teams to evolve their codebase and underlying data structures/data stores with confidence that it will not impact any other part of the system.

**Resources:**

* Eric Evans - [Domain Driven Design](http://dddcommunity.org/book/evans_2003/)
* Andrew Fawcett - [Domain Layer in Salesforce](https://developer.salesforce.com/page/Apex_Enterprise_Patterns_-_Domain_Layer)

#### Service Layer

**Resources:**

* Martin Fowler - [https://martinfowler.com/eaaCatalog/serviceLayer.html](https://martinfowler.com/eaaCatalog/serviceLayer.html)
* Andrew Fawcett - [https://developer.salesforce.com/page/Apex\_Enterprise\_Patterns\_-\_Service\_Layer](https://developer.salesforce.com/page/Apex_Enterprise_Patterns_-_Service_Layer)

#### Selector Layer / CQRS

To help ensure queries are optimized, organized and reusable it may be important to implement a selector layer.

**Resources:**

* Andrew Fawcett - Video - [https://www.youtube.com/watch?v=qlq46AEAlLI](https://www.youtube.com/watch?v=qlq46AEAlLI)
* Andrew Fawcett - [https://developer.salesforce.com/page/Apex\_Enterprise\_Patterns\_-\_Selector\_Layer](https://developer.salesforce.com/page/Apex_Enterprise_Patterns_-_Selector_Layer)

#### Canary Releases / AB Testing

To minimize impact to production users of new features and to allow for better understanding of user usage it may desirable to employ canary releases and AB testing functionality. Canary releases allow releasing into production functionality but control the audience impacted, for example starting with production test accounts to allow QA to validate functionality in production, then to a smaller portion of the userbase and then finally to the entire userbase. We desire AB testing to allow the business to perform trials of functionality to determine if yields the expected outcome.

**Resources:**

* Martin Fowler - [https://martinfowler.com/articles/feature-toggles.html](https://martinfowler.com/articles/feature-toggles.html)
* Salesforce Maximizer Blog: [http://sforcemaximizer.com/how-to-do-ab-testing-on-new-features-with-your-salesforce-crm/](http://sforcemaximizer.com/how-to-do-ab-testing-on-new-features-with-your-salesforce-crm/)

#### Service Registry / Discovery

Andrew Fawcett suggests using a factory pattern to resolve services in Salesforce, it would be ideal have Service Registry / Discovery implementation. Developing an approahc resolving services would be beneficial. \(i.e. ideally not having a direct reference between a visual force or lightning component controller and the service\(s\) it consumes\) Having the ability to switch out implementations, or have multiple implementations with different functionality running in parallel is desired \(for example speech to text with both Salesforce Eintstein and Amazon services\)

**Resources:**

* Service Registry - [http://microservices.io/patterns/service-registry.html](http://microservices.io/patterns/service-registry.html)

#### Application Telemetry

Providing runtime analytics to SREs at the org enables detailed behavior understanding.

**Resources:**

* Event Monitoring - [https://trailhead.salesforce.com/en/modules/event\_monitoring/units/event\_monitoring\_intro](https://trailhead.salesforce.com/en/modules/event_monitoring/units/event_monitoring_intro)'
* Financial Times Approach -   [http://engineroom.ft.com/2016/01/28/logging-alerting-and-recovery-on-the-force-com-platform/](http://engineroom.ft.com/2016/01/28/logging-alerting-and-recovery-on-the-force-com-platform/)
* Using with LogStash - Plugin - [https://www.elastic.co/guide/en/logstash/current/plugins-inputs-salesforce.html](https://www.elastic.co/guide/en/logstash/current/plugins-inputs-salesforce.html)
* Integration Example : [https://www.elastic.co/blog/analyzing-salesforce-data-with-logstash-elasticsearch-kibana](https://www.elastic.co/blog/analyzing-salesforce-data-with-logstash-elasticsearch-kibana)

