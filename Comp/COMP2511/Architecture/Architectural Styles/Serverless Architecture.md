## Overview
Serverless computing allows developers to build and run applications without managing infrastructure. Developers focus on deploying individual functions rather than microservices without managing servers. 

Instead of the developer managing deployment details, the provider deals with that. Serverless does **not** mean there is no server - just from the developer's perspective, there isn't. You do not manage a server.

### How Serverless Works
- User Sends Request
- API Gateway receives and triggers a Lambda/Function
- Function processes data and interacts with services
- Result returned to user

### Key Characteristics
- **Auto-scaling**: Instantly handles thousands of concurrent executions
- **Faster time-to-market**: Developers focus on business logic, not infrastructure
- **High availability**: Functions are distributed across multiple availability zones
- **Event-driven**: Functions execute on triggers like HTTP requests, file uploads, or database changes
- **Micro-Billing**: You only pay usage-base costs
- **Short-lived functions**: Ideal for tasks that complete quickly.
### Use Cases
The following could be example use cases of serverless architecture:
- Google Cloud Functions reacts to database changes and sends real-time notifications to users
- Lambda automatically resizes images uploaded to S3 for use in different display formats
### Serverless Design Principles
- Stateless (Don't rely on local memory - use shared storage)
- Event-Driven (Design workflows around events, not request-response chains)
- Minimal and Composable Functions (Keep single-responsibility per function)
- Use Queues/Pubs/Subs (Decouple flows using queues or publish-subscribe messaging services)

## Advantages and Disadvantages

### Limitations
- Cold starts (Latency due to program start-up)
- Vendor lock-in (Difficult to change Service Providers)
- Observability (hard to trace request flows)
- Resource limits (time and storage constraints)
