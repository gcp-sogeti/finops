## Finops : les Fondamentaux


----

### Finops
The goal of FinOps is not to save money. FinOps is about making money.
So it's no longer a fight about the cost of infrastructure but a conversation about its business business.

----

### Not a role, not a function, but a combination of activities
<img src="img/culture.png" style="background:none; border:none; box-shadow:none;"/>

----

## the 6 main steps

> Strategy
> Governance
> Build
> Run
> Optimization
> Technology watching & Expertise

----

### Finops Level adoption

Level 1 : Understand your invoice for the Cloud and lay the foundations (quickwins).
Level 2 : Keep your expenses under control by optimizing usage and pricing (KPI).
Level 3 : Establish digital sobriety as a pillar of the organization.

<img src="img/finops.png" style="background:none; border:none; box-shadow:none;"/>

----

## Design for Cost Reduction

• “Right-size” & “Right-family” instances.
• Purchasing Reserved Instances (RI) for groups of long-running instances.
• Leverage spot instances to get the best price.
• Use optimize services to leverage a “Pay as you go” model to reduce cost(ServerLess function, Pub/Sub, BiQuery etc.).
• Design for server-less architecture.
•  Delete unattached block storage discs. ...
• Delete obsolete snapshots. ...
• Delete disassociated IP addresses. ...
• Terminate zombie assets. ...
• Put non-production VMs on a schedule. ...
• Take advantage of committed use discounts. ...
• Migrate cold data to lower cost storage.

----

## Implementing governance policies and rules

• Track and manage changes like: launching new resources, tracking and terminating unused or underutilized assets
• Automate workflow for policy actions like: stop or terminate instances, delete volumes, etc.
• Automate the process of purchasing and modifying reserved instances across one of more accounts.
• Avoid costly surprises in your cloud. Proactively manage your cloud with policy notifications
