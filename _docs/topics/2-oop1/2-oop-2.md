---
title: Classes In Java
permalink: /docs/2-oop-2/
---

If we want to use objects in Java we first need to know how to create them and to create them we need to know how to define classes.   

## Class Definition

>In Java it is considered good practice to define each class in its own file. This is not essential but it does make code easier to read and maintain.

```java
class name {

    Properties : variable declarations and constants

    Behaviours : method definitions
}
```

The start of the class definition is the `class` keyword followed by a `<classname>`. All the properties and behaviours are defined within the curly brackets that begin after the class name.

Most of this you've done before, you've created variables, constants and methods. The syntax for creating them in a class is very similar. 


### Class Structure
The ordering of properties and behaviours in the class do not matter. However coders generally stick to the order below. This coding convention makes maintaining and reading code, especially other people's code, much easier.  

* Static Data - data which is shared by every object of the class - i.e. change the value for one object, change it for all of them
* Instance Data - data which is specific to the object. All objects of a class have the same data but they all have distinct values for that data.
* Methods grouped by functionality
    * Constructor(s) - methods called when an object is created
    * Destructor - method called when an object is destroyed
    * Getters & Setters - methods to change and return object properties
    * Other Specific Functionality by grouping

Don't worry about what any of the above means, we will cover all of it in the course of the module.  

## Simple Class Example

Let's create a simple ball class. We'll call the class `Ball` and give it two properties, `size` and `colour`

```java
class Ball {
    int size;
    
}
