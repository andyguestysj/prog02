---
title: Object Oriented Programming
permalink: /docs/oop-1/
---

## Objects & Classes

Java is an object-oriented programming language (OOP). In Programming 01 you were briefly introduced to objects and classes, these are the core of object oriented programming. This module will cover OOP in much more detail and examine the fundamental concepts and features that make OOP so powerful.  

We will begin with a recap of the basics of objects and classes.  

## Objects

An **object** is a collection of *properties* and *behaviours* that embody a *concept*.   

The **concept** is usually a *thing*, an entity that exists within the scope of the software we are developing. It might be an employee, a file, an account, a location. In a game it might be a level, a boss or a power-up. The *concept* is something essential to the *system* we are modelling.  

>In Computing we use the word **system** to describe situation we are working with. If we were asked to develop new software to replace some old software we would refer to the old system and the new system. If we were asked to develop software to manage a cafe we would refer to the processes, paperwork and people of the cafe as the system we were modelling.  

Every *object* has a **properties** that define its state. Which *properties* it has depends upon its *concept*. If our object has the concept of a *ball* then its properties might be *size=football*, *colour=orange*, *material=leather*. It might have more abstract properties such as *location=Garage* or *owner=Bob*. It probably also have a property like *velocity* which describes the current state of the ball. 

Note that **properties** have to parts to them - a name and a value. size, colour, material, location and owner are the *names of properties*. football, orange, leather, Garage and Bob are the *values of properties*. Every **ball** has the *same property names* but *differing property values*. (For the most part anyway, Bob could have fifty identical footballs in his garage!).  

Every object has **behaviours** that define what it can do. These mostly define actions the object can do or can be use to do, though they may also include things that can be done to the object. Our **ball** object might have behaviours like *Bounce* or *Burst* to represent things it can do, it might have behaviours like *Inflated* or *Deflated* to represent things that can be done to it. 

It is unlikely to have a *Kick* behaviour. *Kick* is more likely to be a behaviour of a *footballer object*. The ball might have a *Kicked* behaviour to make the ball move when a footballer kicks it.  

In **Java** terms the object has **data** and **methods**.  

The *data* consists of variables that are stored within the object. These can be primitive variables like integers and characters or more complex variables like arrays or even other objects.  

The *behaviour* consists of methods that are also part of the object.  

## Classes

Classes are how we define the properties and behaviours an object will have. They are a template or blueprint for how to create an object. A class is a set of instruction on how to create items of a specific *concept* by describing the *property names* and *behaviours* that item will possess.

An object is a specific, single item of the concept defined by a class. We call an object an **instance** of an object. Each object is a *distinct* item. We considered the possibility that Bob might have fifty identical balls in his garage, in that case there would be fifty objects of the ball concept. Each would have the same properties but would be distinct from each other.

## Classes and Objects

Classes and objects go hand in hand. You can't have an object without having a class that it is made from. You *can* have classes without objects and later on we will look at why you might want to do that.  

For the time being think of them like this -
* a **class** describes a *concept* by defining its *property names* and *behaviours*
* an **object** is an *instance* (or instantiation) of a **class**. Objects have *property values* that (usually) differ from other objects of the same class.  