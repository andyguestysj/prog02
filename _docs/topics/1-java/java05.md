---
title: App Structure
permalink: /docs/java05/
---

### App Class & App Object

Java apps have a specific structure. This structure is due to Java's nature as an OOP language. We will get fully in to what OOP means in a couple of weeks but for the time being we'll use this definition;

> An **object** is a single item, a cat, a car, a planet. It has *attributes* or values associated with it - colour, age, name, address, etc. and it has *actions*, things it can do - run, purr, indicate left, orbit the sun, etc.
> A Java app is an object that has *data* as attributes and *methods* as actions.

> A **class** is a template that is used to define and create *objects*. A *car design* is like a class for multiple actual car *objects*. Multiple objects can be created from a single class

> **Objects** created from a single **class** have the same *methods*. The also have the same *attributes* but the values in those attributes may differ. Every cat object has a name and a colour but one may be Jeans who is a tortiseshell and another might be Jorts who is ginger[*](https://www.cnet.com/how-to/jorts-the-cat-everything-you-need-to-know-about-the-internets-new-favourite-cat/).  

Using the definition above, the code for a Java app describes a clas, when you compile and run that code an App object is created.  

In practice Java apps will contain multiple classes. There will be one class that describes the app at a high level and other classes that describe various parts of it. This is like having a design for a car and sub-designs for wheels, doors, seats, etc.  

### App Structure

Our hello world app from last week shows this structure.

```java
public class App {
    public static void main(String[] args) throws Exception {
        System.out.println("Hello, World!");
    }
}
```

The app class is created with the first and last line. The keyword `class` indicates a class will be created and it will be with the next word. Here that is `App` but it could be any non-restricted word. The curly brackets indicate the scope of the class/app. Everything between the matching curly brackets is part of the app. The keyword `public`  we will cover later but here it simply means it can be used from anywhere.  

```java
public class App {

}
```

Within the `App` class we have a single method.  

```java
public static void main(String[] args) throws Exception {    
}
```  

In all Java programmes **main** is the entry point for the code. When the programme is run, it starts running the code in **main**. 

The `main` method here has three keywords before it.
* **public** we have previously mentioned  
* **static** is hard to explain without diving deeper into classes and objects. Let us say for the time being that it is required for methods in the `App` class.
* **void** means this method does not return a value. We'll look at this more when we talk about methods. In Java if a method returns a value the method must define that value when it is defined. If `main` returned an integer the line would be `public static int main ...` 

Within the round brackets the parameters for the method are defined. For `main` this almost always consists of an array of strings. We'll look at defining variables and arrays soon. For now the major difference between Java and Python is that *when we create a variable we **must** give it a type*.  

`throws Exception` allows our code to try to handle run-time errors gracefully instead of just falling over. This code doesn't do anything to handle errors so it will still just fall over!  

Finally, the curly brackets define the scope of the method. Everything from the opening curly bracket after `Exception` to the matching closing curly bracket is part of the method.  

### App Structure

That is about it. At least that's it for the simplest Java apps. We'll look again at the structure when we start creating our own classes.  