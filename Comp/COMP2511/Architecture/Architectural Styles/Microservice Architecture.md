A microservice performs one specific function, and communicates with other microservices over a network. It's similar to Modular Monolith, but each module is deployed as its own service. Each service has its own database, for which access is restricted to the owning microservice. It becomes a balance of small and large services.

**Strengths**
- Deployability
- Maintainability
- Testability
- Faster, parallel development
- Fault isolation
- Smaller, focused code-bases
**Weaknesses**
- More complex to set up
- Harder to debug (tracing issues across services is tricky)
- Communication costs - services talking over the network is slower and more error prone than in-process calls
- Databases separated by microservices, which isn't suitable for data which cannot be broken apart

A natural progression is to start off with Modular Monolith and transition into microservices.