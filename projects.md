---
description: Projects that are currently ongoing
---

# Projects

**Frontend Development:** The opensolar frontend is under development and there are multiple opportunities for collaboration and development:

* Implementing a Content Management system: Opensolar requires a content management system in order to manage the content on the frontend. The frontend content is divided into the following sub categories:
  * Project content: Project details and content need to be editable by originators and receivers. Currently, this is done by changing parameters through the backend but this needs to be moved to the frontend where people can change content as desired.
  * Developer engine: The developer engine is one of the core pieces of the Opensolar platform. The engine enables developers to specify project details, give proejct quotes and continuously manage infrastructure all from one place.
  * Investor dashboard: The fields that are displayed on the investor dashboard are fed from a rudimentary CMS fed from the backend. These fields must be editable on the frontend by an investor, and an investor must have the optino to add fields from the backend to their dashboards.
  * Receiver dashboard: Like the investor dashboard, the fields that are displayed on the receiver dashboard are fed from a rudimentary CMS fed from the backend. These fields must be editable on the frontend.
  * Admin dashboard: Opensolar has an admin API interface through which admins can perform a variety of functions on the platform. These functions do not have pages on the frontend yet, and designing and developing such a page would be useful for all platform admins.
  * Teller dashboard: The teller works in conjunction with the platform, and there is no representation of the data that the teller communicates on the frontend. Designing such a page would be useful for developers and receivers to monitor progress on the teller, and view blockchain commitments and state updates that the teller commits.
* Pausable smart contracts: The Opensolar smart contract deployed on AWS has multiple redundancy checks in place but in no event can a platform admin stop its execution once the project flow is in place. Having a pausable smart contract would help admins arbitrate better in case of conflict and pause contract exeution in the event there's a hack on the platform, etc. This also helps clear some uncertainties on the legal side since the contracts can now be paused and investors can be protected by the platform against massive losses.
* * Migrating to a SQL based database: Opensolar right now uses boltDB - a key value pair database with limited room for scalability. Migrating to a SQL based database would better create relations between different entities on the platform, better design the database infrastructure, and be more scalable since SQL is designed to be used in production environments. postgreSQL or MySQL would be ideal options to look at for migration.
* asd

