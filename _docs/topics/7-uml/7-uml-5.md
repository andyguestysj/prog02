---
title: Sequence Diagram
permalink: /docs/7-uml-5/
---

A **sequence diagram** shows object interactions arranged in time sequence. It depicts the objects involved in the scenario and the sequence of messages exchanged between the objects needed to carry out the functionality of the scenario. Sequence diagrams are typically associated with use cases.

A sequence diagram shows, as parallel vertical lines (lifelines), different processes or objects that live simultaneously, and, as horizontal arrows, the messages exchanged between them, in the order in which they occur. This allows the specification of simple runtime scenarios in a graphical manner.

## Sequence Diagram Example

The example below describes the sequence for logging in to an ATM machine. The user inserts their bank card and the ATM prompts the user to enter their PIN. The user enters the PIN and the ATM connects to the control system to validate the PIN. If it is validated the ATM asks the user what they want to do. If it is not validated the user is informed.

![Use ATM Sequence Diagram Example](https://ysjprog2.netlify.app/assets/img/topics/7uml/UseATM.png)
*Use ATM Sequence Diagram Example* 

## Sequence Diagram Components

### Actor

In Sequence Diagrams Actors are used to represent a user that interacts with a system. 

![Actor](https://ysjprog2.netlify.app/assets/img/topics/7uml/seqactor.png)
*Actor* 

### Participant

Sometimes used to represent users, participants are mainly used to represent methods, objects or other components of the system.

![Participant](https://ysjprog2.netlify.app/assets/img/topics/7uml/participant.png)
*Participant* 

The two actor figure/participant boxes represent the start and end of the participation of the actor/participant in the sequence. The dotted line between the two is called the lifeline.

### Synchronous Messages

A synchronous message waits for a reply before the interaction can move forward. The sender waits until the receiver has completed the processing of the message. The caller continues only when it knows that the receiver has processed the previous message i.e. it receives a reply message. A large number of calls in object oriented programming are synchronous. We use a solid arrow head to represent a synchronous message.

![Synchronous Messages](https://ysjprog2.netlify.app/assets/img/topics/7uml/synchronous.png)
*Synchronous Messages* 

### Asynchronous Messages

 An asynchronous message does not wait for a reply from the receiver. The interaction moves forward irrespective of the receiver processing the previous message or not. We use a lined arrow head to represent an asynchronous message.

![Asynchronous Messages](https://ysjprog2.netlify.app/assets/img/topics/7uml/asynchronous.png)
*Asynchronous Messages* 

# Sequence Diagram Example

The example below describes the sequence for logging in to an ATM machine. The user inserts their bank card and the ATM prompts the user to enter their PIN. The user enters the PIN and the ATM connects to the control system to validate the PIN. If it is validated the ATM asks the user what they want to do. If it is not validated the user is informed.

![Use ATM Sequence Diagram Example](https://ysjprog2.netlify.app/assets/img/topics/7uml/UseATM.png)
*Use ATM Sequence Diagram Example* 

The dashed vertical lines between the top and bottom of the diagrams show the participant is "alive" for the full sequence. Where a box is shown over the line the participant is considered "active".

In this example the User, ATM and Control system are all "alive" throughout the sequence. The User is actually alive while the ATM and Control systems are powered up and running. At the start of the sequence (before the user enters their card) none of the participants are active with regards to this sequence. (Really the sequence hasn't begun).

The User inserts their bank card. By doing this they start the sequence and become an active part of it. The ATM likewise becomes an active participant as the card is inserted. The Control system is running but not yet involved. It doesn't become an active part of the sequence until the ATM attempts to verify the PIN.

The gaps in the activation show that they are not a direct continuation of the sequence but instead an alternate outcome.