---
title: Class Diagram
permalink: /docs/7-uml-2/
---

The most commonly used and arguably the most useful UML diagram is the **Class Diagram**.

The Class Diagram shows the classes involved in a system (or a part of that system). It shows the relationships between those classes - which classes inherit from which, which classes use other classes as member variables, etc. 

## A Simple Class Diagram  

![A simple class diagram](https://ysjprog2.netlify.app/assets/img/topics/7uml/class1.jpg)
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
![A class in UML](https://ysjprog2.netlify.app/assets/img/topics/7uml/class-components.png)
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

![Class Accessibility](https://ysjprog2.netlify.app/assets/img/topics/7uml/class-components-access.png)
*Class Accessibility*  

### Class Relationship

The lines between classes indicate different types of relationships. 

![Class Relationships](https://ysjprog2.netlify.app/assets/img/topics/7uml/uml-class-relation-symbols.png)
*Class Relationships*  

(Definitions from Wikipedia)

#### Dependency

A dependency is a semantic connection between dependent and independent model elements. It exists between two elements if changes to the definition of one element (the server or target) may cause changes to the other (the client or source). This association is uni-directional. A dependency is displayed as a dashed line with an open arrow that points from the client to the supplier.

#### Association 

An association represents a family of links. A binary association (with two ends) is normally represented as a line. An association can link any number of classes. An association with three links is called a ternary association. An association can be named, and the ends of an association can be adorned with role names, ownership indicators, multiplicity, visibility, and other properties.

There are four different types of association: bi-directional, uni-directional, aggregation (includes composition aggregation) and reflexive. Bi-directional and uni-directional associations are the most common ones.

For instance, a flight class is associated with a plane class bi-directionally. Association represents the static relationship shared among the objects of two classes.

![Association](https://ysjprog2.netlify.app/assets/img/topics/7uml/association.png)
*Association* 

#### Aggregation

Aggregation is a variant of the "has a" association relationship; aggregation is more specific than association. It is an association that represents a part-whole or part-of relationship. As shown in the image, a Professor 'has a' class to teach. As a type of association, an aggregation can be named and have the same adornments that an association can. However, an aggregation may not involve more than two classes; it must be a binary association. Furthermore, there is hardly a difference between aggregations and associations during implementation, and the diagram may skip aggregation relations altogether

![Aggregation](https://ysjprog2.netlify.app/assets/img/topics/7uml/aggregation.png)
*Aggregation* 

#### Composition

The UML representation of a composition relationship shows composition as a filled diamond shape on the containing class end of the lines that connect contained class(es) to the containing class.

![Composition](https://ysjprog2.netlify.app/assets/img/topics/7uml/composition.png)
*Composition* 

Two class diagrams. The diagram on the right shows Composition between two classes: A Car has exactly up to four wheels, and the wheels are part of one Car. Wheels cannot exist as separate parts, detached from a specific car. 

The diagram on the left shows Aggregation between two classes: A Pond has zero or more Ducks, and a Duck has at most one Pond (at a time). Ducks can exist separately from a Pond, e.g. it can live near a lake. When we destroy a Pond we usually do not kill all the Ducks.

#### Inheritance 

Inheritance is indicated by a line with a triangle at one end. The triangle indicates the parent class. 

![Inheritance](https://ysjprog2.netlify.app/assets/img/topics/7uml/inheritance.png)
*Inheritance* 

#### Multiplicity

This association relationship indicates that (at least) one of the two related classes make reference to the other. This relationship is usually described as "A has a B" (a mother cat has kittens, kittens have a mother cat).

The UML representation of an association is a line connecting the two associated classes. At each end of the line there is optional notation. For example, we can indicate, using an arrowhead that the pointy end is visible from the arrow tail. We can indicate ownership by the placement of a ball, the role the elements of that end play by supplying a name for the role, and the multiplicity of instances of that entity (the range of number of objects that participate in the association from the perspective of the other end).

|Symbol|Meaning|
|---|---|
|0|No instances (rare)|
|0..1|No instances, or one instance|
|1|Exactly one instance|
|1..1|Exactly one instance|
|0..*|Zero or more instances|
|*|Zero or more instances|
|1..*|One or more instances|

## Class Diagram Example

Looking back at the shape example we have used previously, we might come up with a class diagram like this. 

![Shape Class Diagram](https://ysjprog2.netlify.app/assets/img/topics/7uml/shape.png)
*Shape Class Diagram* 

I've added in an `Image` class which stores a list of `Shape` objects that make up an image.

The *abstract class* *`Shape`* is the centre of the diagram. The classes `Triangle`, `Rectangle` and `Circle` all inherit from *`Shape`* as indicated by the relationship lines with the triangles on.

The `Colour` class is has a one to one relationship with the *`Shape`* class. Each *`Shape`* object is connected to one and only one colour and we don't have colours that aren't connected to a *`Shape`* object. Remember that anything in *`Shape`* is also in all classes that inherit from it and this includes relationships to other classes. (This does not apply to inheritance relationships).

## Class Diagrams

Class Diagrams are completely static. This means that at any point in the execution of the program the class diagram is the same.  

Next we will look at object diagrams. Object diagrams are snapshots of the relationships between objects as a specific moment in time.