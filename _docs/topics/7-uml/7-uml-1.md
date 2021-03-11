---
title: Unified Modelling Language
permalink: /docs/7-uml-1/
---

Video of this lecture.  


## Modelling Systems

When we are trying to design a system it is often useful to develop a model of that system. Modelling a system is a good way to understand it by identifying the components of the system and how they interact with each other.  

There are three ways in which systems modelling is often used in software engineering.  

During the **Analysis** phase of a project, where new software is being developed, a model of the processes being used is developed. The analysts examine the way people work, what they need the new software to do, how they work, etc. They often develop a model of the whole situation not just the software required but how it fits in to the work they are doing and how the people who will be using it interact with each other.   

Sometimes there is an existing system which needs to be updated or replaced. If the system is and old, legacy system there may be little to no information on how it works. Analysts will reverse engineer a system model so that the designers of the new/updated system have something to work from.  

Finally new systems are modelled as part of the design for that new system.  

## Unified Modelling Language

The Unified Modelling Language (UML) was developed as a standardised graphical language for specifying, visualising, constructing and documenting the artefacts of software systems. It was designed to model the structure, behaviour and function of the code through a selection of diagrams.

![UML Diagram Hierarchy](https://ysjprog02.netlify.app/assets/img/topics/7uml/uml_overview.png)
*UML Diagram Hierarchy*  

UML Diagrams are divided in to two groups, as shown in the image above.  

**Behaviour** diagrams describe how the code *behaves*, these are diagrams that show interactions between objects, interactions between users and the system and how the state of the system changes over time.  

**Structure** diagrams describe how the code is *structured*, these are diagrams that show the class hierarchy of the system, the object and component structures.  

**Behaviour** diagrams show the dynamics of the system, how it changes over time. **Structure** diagrams show static views of the system. They are either a view of the fixed components of the system or a snapshot of the structure at a moment in time.  

