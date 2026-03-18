## Overview
Behavioural Modelling captures how the system behaves in response to events or interactions over a time period. Software Design/Architecture (UML diagrams, etc.) do not tell us how components interact over time. Different notations for expressing behaviour include:
- Sequence Diagrams
- Activity Charts
- State Charts
## Sequence Diagrams
A sequence diagram is an interaction diagram telling us how objects interact in a time-sequences manner. They clarify interactions among objects and improve system behaviour understanding. Emphasizing the order of interactions, they show how operations are carried out through exchange of messages.
### Components of Sequence Diagrams
- **Actor**: External user or system
- **Objects**: Entities involved, represented by rectangles
- **Lifelines**: Lines showing object existence during interactions
- **Messages**: Communications between objects
- **Activation Boxes**: Indicators of active processing of messages
![[Sequence Diagram.png]]


### Types of Messages
There are two types of messages:
- **Synchronous**: The user waits for a response before continuing
- **Asynchronous**: The user does not wait for an immediate response
Generally, sending a message is indicated with a solid line, while sending a response is indicated with a dotted line.

| Synchronous Message                       | Asynchronous Message                      |
| ----------------------------------------- | ----------------------------------------- |
| ![[Synchronous Message - Sequence Diagram.png\|325]] | ![[Asynchronous Message - Sequence Diagram.png\|325]] |
## Sequence Diagram - Overview
- The **Horizontal Axis** captures participating objects. They are placed from left to right in order of participation in message sequence.
- The **Vertical Axis** represents time (time passing $\rightarrow$ moving downwards), focusing on order rather than duration
- **Messaging** is shown using horizontal arrows. These can be calls/invocation of methods, in a component, or results given by that component.

## Interaction Branches
### Optional Interaction
**opt** represents optional scenarios which are conditional. It functions the same as an if statement without an else (it either happens, or it doesn't. No alternatives)
![[Optional Scenario - Behavioural Modelling.png|400]]
### Alternative Interaction
**alt** represent alternative scenarios, each of which is conditional. They are functionally equivalent to if-else branches
![[Alternate Scenarios - Behavioural Modelling.png|400]]
### Looping Interaction
**loop** represents repeated actions. This is also conditional - once the condition is not met the loop ends (through, the condition can be somewhat implied).
![[Looping Scenario - Behavioural Modelling.png|400]]
### Parallel Processes
**par** represents concurrent processes occurring simultaneously.
![[Parallel Processes - Behavioural Modelling.png|400]]

## Benefits of Sequence Diagrams
Sequence Diagrams:
- Clarify interaction order/logic
- Identify inefficiencies and redundancies
- Enhances team communication
- Helpful debugging tool, improving process clarity
- Improves collaboration and understanding

## Example Sequence Diagram
![[Example Sequence Diagram.png]]


