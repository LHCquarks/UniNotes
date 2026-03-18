## Logical Components
Logical components of a software system are the **functional building blocks** of the system - the sections of the problem domain. They represent major features or responsibilities, typically corresponding to modules or folders in the codebase. These components should be named descriptively based on responsibilities, 

### Logical v.s. Physical Architecture
Logical components of an architecture are different to physical components of an architecture. **Logical architecture** describes what the system does functionally (e.g. Registration, Payment, Sign-on), while **physical architecture** describes how the system is built and deployed technically (services, databases, APIs)
### Creating a Logical Architecture
To create a logical architecture:
- Identify core components of the system
- Assign Requirements
- Analyse roles and responsibilities
- Align components with architectural characteristics (e.g. break down components based on scalability, availability and performance)
### Component Coupling
As always, the goal is to keep coupling low for flexibility and maintainability. We have terminology to describe it:
- **Afferent** coupling describes how many components depend on this component.
- **Efferent** coupling describes how many components this component depends on.
The total coupling is a combination of afferent and efferent coupling.

As always, this leads to trade-offs.
- Tightly coupled components are easier to trace, but harder to change
- Loosely coupling components are harder to understand in one place, but more maintainable
## C4 Architectural Modelling
### Challenges in Software Engineering
Architectural modelling is always about trade-offs. It's difficult to find a balance between understandability and correctness, especially in cross-functional teams. Additionally, there are multiple 'levels' of architecture. Higher level architectures are closer to requirements, while lower level architectures are closer to implementation.

There is no standardised way of modelling architectures. We've seen UML, and Sequence Diagrams. Let's introduce yet another!

### C4: Overview
C4 gives a name to different design concepts. C4 Models help visualise the different abstraction levels of a system - it bridges the gap between high-level systems and low-level systems. 

### C4 Diagram Levels
A C4 diagram contains 4 levels of abstraction:
#### Level 1: Context Diagram
A context diagram is the most general description of what your system does - the outermost level of abstraction from the program. It shows who will use it, and what external systems will interact with it.

This level helps you describe the scope of your project.
**Example**
![[Context Diagram - C4.png|700]]
#### Level 2: Container Diagram
A container diagram is one abstraction step down from level 1. It preserves level 1, and breaks your software system into a container, containing its modules - e.g. APIs, applications, databases and microservices. Each application/service is represented as a container and the interactions between high-level sub-services are shown (arrows must point to specific modules).
**Example**
![[Container Diagram - C4.png|700]]
#### Level 3: Component Diagram
Component Diagrams are one step deeper than Container Diagrams. This diagram zooms into the software system and shows the relationships between its components (where components are abstractions of your codebase). Similar to a UML diagram, but with a less strict set of rules.
**Example**
![[Component Diagram - C4.png|700]]
#### Level 4: Code Diagram
A code diagram has the most detail to show how the code of a single component is implemented. This can be in the form of a UML class diagram, or an entity relationship diagram describing the component.
**Example**
![[Code Diagram - C4.png|700]]

