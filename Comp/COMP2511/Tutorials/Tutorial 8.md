## Software Architecture
Software architecture defines the fundamental high-level structure of a software system. It defines how system components are structures, how they interact, and the guiding characteristics that shape its evolution.

**How is it different to software design?**
So far, we've dealt with software design at a code-level. i.e. classes, methods, controllers and design patterns.

Architecture operates at a more macro-scale. It involves system-wide and more structural decisions of a system, which take more effort to change. Typically involves multiple components or subsystems.

Specifically, software architecture focuses on modules, layers, services, fronted, backend, etc.

## C4 Diagrams 
C4 Models help visualise the different abstraction levels of a system - it bridges the gap between high-level systems and low-level systems. A C4 diagram contains 4 core diagrams:
### Level 1: Context Diagram
Shows the system as a "box" and its interaction with users 
### Level 2: Container Diagram
Breaks system into containers (applications/services/databases) and shows how they interact
**Why separate this way?**
- Separation of concerns
- Independent deployment
- Scalability
- Technology flexibility
### Level 3: Component Diagram

### Level 4: Code (Class) Diagram
Offers a detailed view of the source code structure (e.g. classes) within a ...


## Sequence Diagrams
A sequence diagram is an interaction diagram showing  the temporal order of interactions between objects or components 


Asynchronour arrows should be open, while synchronous arrows should be closed.