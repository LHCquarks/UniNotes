## Overview
Architectural styles are predefined patterns/philosophies guiding the structure and deployment of software systems. They facilitate better design decisions and facilitate the software architecture with project needs.

Architectural Styles are similar to Design Patterns, but they're software-level rather than class-level.

This course focuses on the following architectural styles:
- [[Layered Architecture]]
- [[Modular Monoliths Architecture]]
- [[Microservice Architecture]]
- [[Event Driven Architecture]]
- [[Serverless Architecture]]
## Categories of Architectural Styles
There are two main categories for architectural styles:
1. **Partitioning**
		Technical v.s. Domain-based
2. **Deployment**
		Monolithic v.s. Distributed
Every program will have a Partitioning Style and a Deployment Style. 
## Partitioning Models
### Technical
Partitioning by Technical Concerns organises code by functional roles or technical layers. For example, a standard web app would be split into the UI, Services, and Database . It is easier for specialised teams, and risks over-generalisation.
**Advantages**
- Easier for specialised teams
**Disadvantages**
- Risk of over-generalisation
### Domain
Domain Partitioning involves organising code around business domains or problem area. For example, an e-commerce platform would be split into the customer domain (UI and accounts), the inventory domain (product and stock catalogue), and the payment domain (billing and transactions).
**Advantages**
- Alignment with business goals
- Easier maintenance of related features
- Stronger domain modelling
**Disadvantages**
- Risk of duplicating common functionalities
## Deployment Models Overview
**Monolithic Architecture** is a single deployable unit
- Pros: easier initial development, simplified debugging, and lower initial deployment cost. 
- Cons: Difficult to scale independently, a single bug can disrupt the entire system, and whey are inflexible when adapting to changing demands.
**Distributed Architecture** is multiple deployable units communicating over networks
- Pros: Independent scalability of components, encourages modular design, and fault isolation (failures only affect single units)
- Cons: High complexity due to network dependence, increased maintenance and debugging complexity, and higher infrastructural and operational costs.
## Fallacies of Distributed Computing
The following 11 fallacies are incorrect assumptions about distributed software development. They reveal key weaknesses in distributed systems. Good architecture anticipates and mitigates these assumptions, improving resilience and clarity.

The 11 Fallacies of Distributed Computing are as follows:
1. The network is reliable
	Mitigation:
	- Use timeouts
	- Retry policies
2. Latency is Zero
	Mitigation:
	- Monitor 95th-99th percentile latency
	- Minimise unnecessary calls
3. Bandwidth is Infinite
	Mitigation:
	- Minimise the passing of large, complex data structures
4. The Network is Secure
	Mitigation:
	- Zero trust architecture
	- Minimise number of endpoints
	- Secure each endpoint
5. Network Topology (physical network routing path) never changes
	Mitigation:
	- Coordinate with network teams
	- Use adaptive timeout policies
6. There is only one administrator
	Mitigation:
	- Maintain a clear contact directory
	- Standardize change coordination
7. Transport Cost is Zero
	Mitigation:
	- Assess total cost of ownership
	- Consider hybrid designs
	- Build this into your pricing
 8. The Network is Homogeneous
	Mitigation:
	- Test network assumptions regularly
	- Avoid hard dependencies on vendor features.
9. Versioning is Easy
	Mitigation:
	- Limit concurrent versions
	- Use deprecation plans
10. Compensating Updates Always Work
	Mitigation:
	- Design for idempotency
	- Include recovery mechanisms
	- Be careful of data inconsistency
11. Observability is Optional
	Mitigation:
	- Centralised Logging
	- Distributed Tracing
	- Alternatively, always write perfect bug-free code

