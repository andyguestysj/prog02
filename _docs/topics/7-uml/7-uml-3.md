---
title: Object Diagram
permalink: /docs/7-uml-3/
---

An object diagram in the Unified Modelling Language (UML), is a diagram that shows a complete or partial view of the structure of a modelled system at a specific time.

Object diagrams are similar in appearance to Class diagrams. The main difference between them is that Class diagrams show the relationships between classes throughout the execution of the program while Object diagrams are snapshots that show the relationships between objects at a specific moment in time.  

From an early UML specification :-

*"An object diagram is a graph of instances, including objects and data values. A static object diagram is an instance of a class diagram; it shows a snapshot of the detailed state of a system at a point in time. The use of object diagrams is fairly limited, namely to show examples of data structure."*

An object diagram focuses on the attributes of a set of objects and how those objects relate to each other. For instance, in this object diagram below, all three bank accounts tie back to the bank itself. The class titles show the type of accounts (savings, checking, and credit card) that a given customer could have with this particular bank. The class attributes are different for each account type. For example, the credit card object has a credit limit, while the savings and checking accounts have interest rates.

![Simple Object Diagram](https://ysjprog2.netlify.app/assets/img/topics/7uml/obj1.png)
*Simple Object Diagram* 

## Object Diagram Components

### Objects

In Object diagrams the object name:class, and specific member variable values are shown.  

![Objects in Object Diagrams](https://ysjprog2.netlify.app/assets/img/topics/7uml/obj.png)
*Objects in Object Diagrams* 

### Links

The links between objects in an object diagram show connections between objects. These use the same associations and use the same links as Class diagrams.

## Class Vs Object Diagrams

|Class Diagram|Object Diagram|
|---|---|
|It depicts the static view of a system.|It portrays the real-time behaviour of a system.|
|Dynamic changes are not included in the class diagram|Dynamic changes are captured in the object diagram.|
|The data values and attributes of an instance are not involved here|It incorporates data values and attributes of an entity|
|The object behaviour is manipulated in the class diagram.|Objects are the instances of a class.|

## Object Diagram Example

The example below shows a snapshot of the Shape application. There is a single image object that has a list of different shapes. Each shape has a single colour associated with it.  

![Shape Object Diagram](https://ysjprog2.netlify.app/assets/img/topics/7uml/objexample.png)
*Shape Object Diagram* 