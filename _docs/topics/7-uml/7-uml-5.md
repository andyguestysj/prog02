---
title: Sequence Diagram
permalink: /docs/7-uml-5/
---

A **sequence diagram** shows object interactions arranged in time sequence. It depicts the objects involved in the scenario and the sequence of messages exchanged between the objects needed to carry out the functionality of the scenario. Sequence diagrams are typically associated with use cases.

A sequence diagram shows, as parallel vertical lines (lifelines), different processes or objects that live simultaneously, and, as horizontal arrows, the messages exchanged between them, in the order in which they occur. This allows the specification of simple runtime scenarios in a graphical manner.

## Sequence Diagram Components

### Actor

In Sequence Diagrams Actors are used to represent a user that interacts with a system. 

![Actor](https://ysjprog02.netlify.app/assets/img/topics/7uml/secactor.png)
*Actor* 

### Participant

Sometimes used to represent users, participants are mainly used to represent methods, objects or other components of the system.

![Participant](https://ysjprog02.netlify.app/assets/img/topics/7uml/participant.png)
*Participant* 

The two actor figure/participant boxes represent the start and end of the participation of the actor/participant in the sequence. The dotted line between the two is called the lifeline.

### Synchronous Messages

A synchronous message waits for a reply before the interaction can move forward. The sender waits until the receiver has completed the processing of the message. The caller continues only when it knows that the receiver has processed the previous message i.e. it receives a reply message. A large number of calls in object oriented programming are synchronous. We use a solid arrow head to represent a synchronous message.

![Synchronous Messages](https://ysjprog02.netlify.app/assets/img/topics/7uml/synchronous.png)
*Synchronous Messages* 

### Asynchronous Messages

 An asynchronous message does not wait for a reply from the receiver. The interaction moves forward irrespective of the receiver processing the previous message or not. We use a lined arrow head to represent an asynchronous message.

![Asynchronous Messages](https://ysjprog02.netlify.app/assets/img/topics/7uml/asynchronous.png)
*Asynchronous Messages* 
