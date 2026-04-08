## Overview
A monolithic architecture organised by domain, not technical layers. It structures the application into independent domain modules. These modules are loosely coupled, but in a single unified codebase. So far in this course, most of the programming work would have used the Modular Monolith Architecture (A modular monolith at its core is simply an object-oriented architectural style).

This architecture allows code and teams to be aligned around business capabilities rather than the technical roles.
### Layered Architecture v.s. Modular Monolith Architecture
**Layered**
Organised by technical concerns (UI, services, DB)
Problem: Changes affect touch many teams
**Modular**
Organised by domain (Order, Payment, Inventory)
Benefit: Changes are isolated within a domain
## Modules
A module is an independent unit within a domain. It contains all the business logic for its domain. In object-oriented programming, a module would be equivalent to a class - of course, this means modules have sub-modules. 

For example: A restaurant app where users can reserve a table, view the menu and order food might be structured as follows:
- **Order Placement Module**
	- Sub-module: Payment Module
- **Menu Module**
	- Sub-module: Menu Item Information
- **Table Reservation Module**
## Code Organisation in a Modular Monolith
Each module has:
- Public API/Interface
- Private implementation. 
Direct calls to a module's implementation is not allowed, only to the module's public API/interface. This loosens the coupling between modules.
### Modularising the Database
To further reduce coupling, partition the data base per-module. Each module should only be allowed to access its own data. Therefore, rather than foreign keys, store the IDs, which should be passed into the relevant Module's API/Interface for that module to retrieve from its database.

## Strengths and Weaknesses of Layered Architecture
**Strengths**
- Domain Partitioning: Better Team Alignment
- Performance: No inter-service latency
- Maintainability: Domain-local changes
- Testability: Scoped, isolated testing
- Deployment: Single unit, easier CI/CD
**Weaknesses**
- Reuse: Harder to share utilities
- One set of characteristics: No per-module customization
- Fragile Molecularity: Easy to break coupling boundaries
- Operational Limits: Harder to scale or isolate faults