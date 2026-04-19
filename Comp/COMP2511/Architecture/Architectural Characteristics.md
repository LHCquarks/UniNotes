## Overview
Architectural characteristic are simply qualities which our our software architecture must support, intentionally or implicitly. These characteristics influence the system and decisions regarding the system. They're important because they align the architecture with real-world needs and successful development. Characteristics majorly affect the structure of the program (e.g. monolithic v.s. microservices).

Some popular architectural characteristics include:
- Scalability
- Availability
- Maintainability
- Security
- Elasticity
- Extensibility
- Deployability
- Responsiveness
There is no exhaustive list of architectural characteristics - they evolve with time and context.
## Architectural Characteristics v.s. Logical Components
Architectural characteristics refer to how the system performs under various constraints, while logical components refer to the domain behaviour of the software (what it does). The table below outlines the relationship:

| Logical Component | Architectural Characteristic |
| ----------------- | ---------------------------- |
| User Registration | Scalability                  |
| Content Posting   | Availability                 |
| Noticications     | Responsiveness               |
| Admin Dashboard   | Security                     |
### Characteristics Affect Structure


## Characteristical Complexity
Don't over-engineer! Too many characteristics leads to unnecessary complexity. This is because characteristics are synergistic (affect each other), evolving, and impossible to standardize. Limit these characteristics to prevent unwanted complexity, and stay focused on the essential traits. Around 7 characteristics is where the limit should start taking place - however, this is subject to change depending on what your software needs.

## Implicit v.s. Explicit Characteristics
**Explicit** characteristics are stated clearly in the requirements document (e.g. "The system must support both English and French"), while **implicit** characteristics are not stated, but expected (e.g. Users expect their data to be secure). A good domain understanding helps identify implicit characteristics.

## Types of Characteristics
### Process Characteristics
Process characteristics represent the intersection between the architecture and the development process of the software. This reflects the process through which the system is built. These
### Structural Characteristics
Structural characteristics are concerned with the internal structure/composition of the system. This influences how components are coupled, interact, and evolve independently. Design qualities such as Modularity, cohesion and adaptability are heavily related to structural characteristics.
### Operational Characteristics
Operational characteristics define how the architectural decisions shape system behaviour at runtime.  They dictate what parts of the system are able to be controlled, adapted and monitors while the system is running, and directly influence reliability, performance and fault tolerance.
### Cross-Cutting Characteristics
These characteristics span the system and affect other characteristics. For example, security.
### Composite Characteristics
Composite characteristics are simply characteristics which are a little more complex, which can usually be represented as a group of simpler characteristics (e.g. reliability = availability, consistency and integrity)

## Sources of Characteristics
There are three main sources of architectural characteristics
- **Problem Domain**: The specific use-case context of the system (e.g. Web Apps -> JavaScript)
- **Environmental Awareness**: The culture, budget, capabilities, goals and requirements of the organisation (e.g. Legacy-heavy organisation -> priorities integratability with existing software)
- **Holistic Domain Knowledge**: The regulatory standards, best practices, and user trust factors (e.g. Government services abide by privacy laws -> Accessibility, security, maintainability)
Architects should identify the most important characteristics across all three sources.
## Trade-offs between Characteristics
Architectural characteristics will frequently conflict or compete, where enhancing one trait compromises another. These are not flaws, rather conscious decisions to be made. There is no correct answer - it's an extremely case-by-case problem.
**Examples**
- Security $\rightleftharpoons$ Performance
- Scalability $\rightleftharpoons$ Simplicity
- Availability$\rightleftharpoons$ Maintainability
- Deployability $\rightleftharpoons$ Robustness
- Responsiveness $\rightleftharpoons$ Data Consistency
- Flexibility $\rightleftharpoons$ Performance

To attack this issue, the following practices are useful:
- Engaging clients early to understand important characteristics
- Use Architectural Decision Records to document rationale.