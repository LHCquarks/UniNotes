## Overview
Layered Architecture separates technical responsibilities into distinct layers by dividing the system into manageable, logical parts which are easy to implement and promotes reuse and separation of content.

Layered Architectures are typically easy to understand and implement, and it promotes reuse and separation of concerns.
### Architectural Style and Philosophy
Layered architecture is **technically partitioned** and usually **monolithic**. The domain logic spans multiple layers:
- Presentation (UI)
- Workflow (business logic operations)
- Persistence (data base schemas and operations)

Layered architecture easily supports changes in **technical** capabilities. However, **domain** changes almost always affect multiple layers. Once again, it becomes a trade-off: Ease of technical changes v.s. difficulty of domain-wide changes.
## Physical Architectures in Layered Systems
Some common physical architectures include:
- Embedded/Mobile
	- All layers bundled into one deployable unit
- Two-Tier (Client/Server)
	- Client UI directly accessible from the database
- Three-Tier (Web)
	- Browser (presentation)
	- App server (business logic)
	- Database server (persistence)

### Physical Architectures - Pros and Cons

| Physical Architecture | Pros                                | Cons                          |
| --------------------- | ----------------------------------- | ----------------------------- |
| Two-Tier              | Simple, quick to build              | Less secure, poor scalability |
| Three-Tier            | Scalable, flexible                  | Complex infrastructure        |
| Embedded/Mobile       | High performance, simple deployment | Limited scalability           |
## Adding Layers
Additional layers can be introduced for specialised tasks, clearly isolating code from core business logic. Since an additional layer is usually a technical change, this is not too difficult.

For example, an **integration** layer might be added to a program to allow APIs to communicate with it.

## Strengths and Weaknesses of Layered Architecture
**Strengths**
- Technical Partitioning: Easy technical reuse.
- Data Intensive Operations: Efficient local data processing.
- Performance: High internal performance without network overhead.
- Fast Development: Ideal for small systems.
- Feasibility: Quick, cost-effective solution.
**Weaknesses**
- Deployability: Monolith deployments become difficult as systems get larger.
- Coupling: High risk of tight coupling
- Scalability: Difficult to scale individual functionalities independently.
- Elasticity: Poor performance under busy traffic conditions.
- Testability: Increasingly difficult testing as codebase grows.