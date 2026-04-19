## Overview
Architectural decisions must be justified - not just how it is done, but more importantly, why the decision was made. This context is helpful for future team members and even yourselves in the future. Important aspects of an architectural decisions are documented using the following format:
## ADR Structure
### Title
The title identifies and summarizes the decision. It is good practise to number/index them. They should be descriptive, concise and clear.
**Example:**
- ADR 001: Asynchronous messaging between order and payment services
### Status
The status is self-explanatory. Types:
- Proposed: pending approval
- Accepted: Approved and active
- Superseded by X: Replaced by another ADR
- RFC, Deadline XX/XX/XX: Open for feedback until a deadline
**Example:**
- ADR 015: Status: Superseded by ADR 021
### Context
The context indicates what situation led to the decision - i.e. the problem requiring a decision, and the alternatives solutions.
**Example:**
- Inventory updates are inconsistent across services; options include central database and event-based sync.
### Decision
Describe the decision that was made 😮😮🤯🤯. Uses clear, assertive language and is justified using rationale.
**Example:**
- We will migrate inventory management to PostgreSQL to ensure consistency and performance
### Consequences
The consequences section describes the side effects, trade-offs and outcomes of the decision. Both positive and negative impacts, and known limitations should be included.
**Example:**
- Enables real-time updates, but requires Kafka infrastructure.
### Compliance
The purpose of this section is to describe how the decision enforcement is measured. For example, through:
- Manual review
- Automated Tests
**Example:**
- Static code analysis rules for package structure and compliance
### Notes
The notes section is to record any metadata. It will include information such as:
- Author
- Approval date
- Approver
- Last modified
- Superseded reference
**Example:**
- Author: A. Johnson, Approved by: K. Svensen, Date: 15 May 2025, Supersedes: ADR 017

## Benefits of using ADR
- Serves as a memory log for decisions
- Helps **new** team members understand context
- Improves consistency and governance
- Supports continuous evolution and learning
## Example ADR Document

| **ADR 001: Use queues for asynchronous messaging between order and downstream services**<br><br>**Status**<br>Accepted<br><br>**Context**<br>The order service must inform downstream services (namely the notification and analytics services for now) about new items available for sale and all transactions. Options include asynchronous messaging (using queues) or asynchronous messaging (using REST)<br><br>**Decision**<br>We will use queues for asynchronous messaging between the order and downstream services.<br><br>Using queues will make the system more extensible, since each queue can deliver a different kind of message. Furthermore, since the trading service is acutely aware of any and all subscribers, adding a consumer involves modifying it, improving the security of the system.<br><br>**Consequences**<br>- Queues result in a higher degree of coupling between services. <br>- We will need to provision queuing infrastructure. <br>- If additional downstream services need to be notified in the future, we will have to make modifications to the trading service.\|<br><br>**Compliance**<br>We will use periodic manual code review to ensure asynchronous messaging is being used between the order and downstream services<br>**Notes**<br>Author: Joel Turner<br><br>Approved: ARB Meeting Members, 76 Jan 2050<br><br>Last Updated: 76 Jan 2050 |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
