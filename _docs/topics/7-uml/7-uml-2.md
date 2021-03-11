---
title: Class Diagram
permalink: /docs/7-uml-2/
---

The most commonly used and arguably the most useful UML diagram is the **Class Diagram**.

The Class Diagram shows the classes involved in a system (or a part of that system). It shows the relationships between those classes - which classes inherit from which, which classes use other classes as member variables, etc. 

## A Simple Class Diagram  

![A simple class diagram](https://ysjprog02.netlify.app/assets/img/topics/7uml/class1.jpg)
*Simple Class Diagram*  

The diagram shows four classes. 

The *`Person`* class is an abstract parent class. This is indicated by the name being in *italics*. 

Two classes are derived from the *`Person`* class, the `Student` and the `Professor` classes. As their names are not in italics these are not abstract classes. 

The lines connecting these two classes to the *`Person`* class show a *relationship* between the classes. In this case the line has an empty triangle pointing to the *`Person`* class indicating it is the parent class for both `Student` and `Professor`. `Student` and `Professor` both inherit from *`Person`*.

The final class `Address` stores information concerning an address. It is also linked to *`Person`* by a line indicating some sort of relationship. In this case the line indicates an *association* between the *`Person`* and the `Address` classes. The arrow shows this is a *directed relationship*, specifically, in this case, a container-contained directional flow. The *`Person`* **contains** an `Address`.  

The numbers on this relationship add more detail. They show how many objects on one side are connected to how many objects on the other. Here we have 0..1 on the *`Person`* side and 1 on the `Address` side. The number indicated how many of the objects it is next to are connected to the object at the far end of the line.

So in this case a *`Person`* object is connected to 1 (exactly one) `Address`. Each `Address` is connected to 0..1, that is zero to one (zero or one) *`Person`* objects. So we know that in our system we will have a number of *`Person`* objects and a number of `Address` objects. Each *`Person`* object will be connected to one and only one `Address`. Each `Address` may be connected to one *`Person`* or it may not. It will not be connected to more than one *`Person`*. I guess at that University there are no professors married to each other or with children at the university!

Remember that the *`Person`* class is abstract. There won't be *any* objects created from that class. There will be `Professor` and `Student` objects though, and since they inherit from *`Person`* we consider them to be *`Person`* objects too.

## Class Diagram 

### Class Symbol
![A class in UML](https://ysjprog02.netlify.app/assets/img/topics/7uml/class-components.png)
*A class in UML*  

In UML a class is indicated by a box with three sections. From top to bottom these sections are.
* **ClassName** - the name of the class, in *italics* if the class is **abstract**
* **Member Variables** - the names of any member variables. The type of the variable may be indicated after the variable name, separated by a colon.
* **Class Methods** - the names of any class methods followed by () (brackets). Parameter names and/or types may be shown inside the brackets in the same format as for member variables. The return type may also be show after the brackets.

Member variables and class methods are in *italics* if they are **abstract**.

In addition the accessibility of member variables and class methods may be shown by prefacing them with +, -, # or ~.

|Symbol|Accessibility|
|---|---|
|+|Public|
|-|Private|
|#|Protected|
|~|Package|

![Class Accessibility](https://ysjprog02.netlify.app/assets/img/topics/7uml/class-components-access.png)
*Class Accessibility*  

### Class Relationship

![Class Relationships](https://ysjprog02.netlify.app/assets/img/topics/7uml/uml-class-relation-symbols.png)
*Class Relationships*  
