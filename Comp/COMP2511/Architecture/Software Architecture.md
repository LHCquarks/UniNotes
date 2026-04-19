## Overview
Software Architecture is about developing an opinion on what the best way to solve a problem and write a program, and making informed structural decisions. It defines the fundamental structure of a software, and influences the software's adaptability, scalability, and reliability. **Architecture isn't about right answers. It's about right reasoning.**
## The Four Dimensions of Software Architecture
### Architectural Characteristics
The architectural characteristics of a software define fundamental qualities the software architecture must support. Some commonly used architectural characteristics include:
- Scalability
- Reliability
- Availability
- Testability
- Security
### Architectural Decisions
The architectural decisions are extremely case-by--case and both guide future development and influence the software behaviour. For example, a person deciding to design a software which handles the purchasing of muffins in a muffin store might make the decision to not prioritise scalability, because they don't expect to sell a billion muffins a day.
### Logical Components
This dimension involves how we split the code up into blocks. What 'units' will I split the program up into? This is usually for the programmer's benefit, rather than the computer. Design patterns heavily influence this.
### Architectural Style
Architectural Styles dictates the overall system shape and structural patterns. This involves high-level patterns like layered, event-driven or microservices.
## Architecture v.s. Design
Architectural decisions, while design decisions are appearance and detailed decisions. Not all decisions are clear-cut, rather they exist on a spectrum from architectural to design decisions. Generally architectural decisions are long-term, and high-impact, while design decisions are short-term and low-impact.

For example, choosing a programming language is an architectural decision, while choosing the colour of a UI button is a design decision.
## Trade-offs in Decision Making
Architectural decisions often involve significant trade-offs. For example:
- Deciding on a cloud deployment service: Scalability v.s. cost
- Async messaging: Performance v.s. complexity
- Choosing between performance and data consistency
Good software architects handle strategic choices based on the trade-offs each decision brings.