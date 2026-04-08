A micro-service performs one specific function, and communicates with other micro-services over a network. It's similar to Modular Monolith, but each module is deployed as its own service. Each service has its own database, for which access is restricted to the owning micro-service. It becomes a balance of small and large services.

**Strengths**
- Deploy-ability
- Maintainability
- Test-ability
- Faster, parallel development
- Fault isolation
- Smaller, focused code-bases
**Weaknesses**
- More complex to set up
- Harder to debug (tracing issues across services is tricky)
- Communication costs - services talking over the network is slower and more error prone than in-process calls
- Databases separated by micro-services, which isn't suitable for data which cannot be broken apart

A natural progression is to start off with Modular Monolith and transition into micro-services.