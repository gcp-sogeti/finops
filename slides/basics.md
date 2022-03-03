## Finops : les Fondamentaux


----

### Finops
The goal of FinOps is not to save money. FinOps is about making money.
So it's no longer a fight about the cost of infrastructure but a conversation about its business business.

----

### Not a role, not a function, but a combination of activities
<img src="https://finops.world/wp-content/uploads/2019/12/cloud-center-excellence-activities-1024x678.png" style="background:none; border:none; box-shadow:none;"/>

----

## Finops Teams

The finops team is composed by techincal and financial members, who will work with many team.
Mandatory : define and share objectives (KPI), best practices and recommandations

Eq. : serverless usage vs classic IaaS.


----

## the 6 main steps
 
 > Strategy
 > Governance
 > Build
 > Run
 > Optimization
 > Technology watching & Expertise


----

## Economic Unit

Economic unit for a project : The idea here is to measure cloud spend against to business metrics

Why is import ? :
It can help you in forecasting.
in terms of profits and therefore costs.
It allows you to optimize your products.
It allows you to evaluate the sustainability on the market.

----

### Finops Level adoption

- Level 1 : Understand your invoice for the Cloud and lay the foundations (quickwins).
- Level 2 : Keep your expenses under control by optimizing usage and pricing (KPI).
- Level 3 : Establish digital sobriety as a pillar of the organization.

<img src="img/finops.png" width="50%" style="background:none; border:none; box-shadow:none;"/>

----

## Organization strategy for Tagging resources

Tags can be used to apply chargeback showback to associated business entities

Technical teams can use tags to :
- identify costs for each platform (production, integration, test & dev,QA...) 
- trigger automated actions on resources with certain tags


----

## How to define tag ?

Through IAC template you can associate tags

```yaml
resource "google_compute_instance_from_template" "tpl" {
  name = "instance-from-template"
  zone = "eu-central1-c"

  source_instance_template = google_compute_instance_template.tpl.id

  // Override fields from instance template
  can_ip_forward = false
  labels = {
    environment = "production"
    project     = "application-xx"
    department  = "financial"
  }
}
```

----

## Enforce Tag control

You can enforce Tagging control :
terraform-compliancea <img src="https://github.com/eerkunt/terraform-compliance/raw/master/logo.png" width="35%" style="background:none; border:none; box-shadow:none;"/>
* tfsec / Checkmark
* terratag
* Sentinel
* Azure Policy
* ....


----

## Design for Cost Reduction

• “Right-size” & “Right-family” instances.
• Purchasing Reserved Instances (RI) for groups of long-running instances.
• Leverage spot instances to get the best price.
• Use optimize services to leverage a “Pay as you go” model to reduce cost(ServerLess function, Pub/Sub, BiQuery etc.).
• Design for server-less architecture.
• Delete unattached block storage discs. ...
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
