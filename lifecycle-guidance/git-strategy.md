# Git Strategy

## Overview:

A key part of the application lifecycle is defining where the code and related assets for development efforts will live, how they will be versioned, and how to support multiple releases across different components \(SFDX packages\) as well as multiple projects & team members per component. This document outlines specific aspects of those different sections of the ALM and how they all work together to support a seamless CI / CD pipeline. To better build a more complete understanding of how we will leverage GIT and branching, this document has been broken down into three different sections:

* Repository Definition / Package Structure
* Branching Strategy
* CI / CD Integration

The aforementioned topics are interrelated and integral to building an understanding on how to will be leverage GIT for development and release; by the end of this document, you should have sufficient understanding of the process to begin building within the framework outlined here.

## Branching Strategy:

**Helpful Reference :** [Read Thoughtworks Guidance on Trunk Based Deployment Pipelines](https://www.thoughtworks.com/insights/blog/enabling-trunk-based-development-deployment-pipelines)

Ideally, having short lived feature branches, or even trunk based development would improve deployment throughput.

The branching strategy used needs to map to the maturity, complexity and rate of change incurred in the org.



| Strategy | Maturity | Complexity | Rate of Change |
| :--- | :--- | :--- | :--- |
| Trunk Based | High | Isolated | High |
| Trunk Based | High | Interdependent | Low |
| Sprint Feature Branch | Low | Interdependent | High |
| Feature Branch | Medium | Isolated | High |
|  |  |  |  |



These 3 factors make a difference:

**Maturity:**

This is the maturity level of the team and the way change is approached. If the team has mature processes and procedures in place for managing and deploying change, including feature toggles etc and the organization is capable of ingesting changes just as rapidly, then the maturity level is considered to be high. Most organizations will likely be at the low and medium levels.

**Complexity:**

Anyone reading this guide will likely have a good degree of complexity within the org, how it is managed is something else altogether.  Following best practices of applying software architecture principles to salesforce is not an easy task, and will allow for isolation of change and better reuse within the system. Achieving isolation will prove challenging, but not an unachievable goal for any team. An interdependent system will restrict the ability to deploy multiple small isolated changes in arbitrary order.

**Rate of Change:**

An org that is undergoing constant rapid change has challenges that one that only incurs small changes very infrequently. Rapid change requires more investment in automation and standard operating procedures to insure continued ability to ingest change.

 



