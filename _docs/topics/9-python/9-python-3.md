---
title: Class Basics
permalink: /docs/9-python-3/
---


## Python Classes Overview

Classes in Python don't look as similar to Java as C# classes do.

Returning to our first inheritance example, we can define an animal class in Python as shown below.

```python
class Animal:
  # Class Variable - for all objects of the class Animal they share the same values
  # i.e. change this value for one Animal object and you change it for all of them
  itemType = "Animal"  

  def __init__(self, name, type, eats):
    # Instance Variable - each object has a distinct value store in these
    self.name = name
    self.type = type
    self.eats = eats

  def run(self):
    # makes the animal run
    # You can't have a block that does nothing, you have to explicitly say it does nothing with pass
    pass

  def setName(self,name):
    self.name = name    

  def getName(self):
    return self.name 
```

At first glance this looks pretty familiar. It has the usual Python syntax changes - indentation rather than curly brackets for scope, no semi-colons, etc. 

The class name line ends in a colon. This is just like the `for` and `if` structure.  

The methods look like we've already seen with a couple of differences.  

Every method in a class must have `self` as the first parameter. `self` isn't passed as a parameter when the method is called, it is added automatically by Python. It is used the same way as `this` is in Java.  

The other difference is the constructor. Instead of having a method called `Animal()` to construct the object we instead have a method called `__init__`. This methods is called automatically when you create the object. Which, confusingly, you do by calling `Animal()`.

```python 
myAnimal = Animal("Hobbes", "Tiger", "Tuna Sandwiches")
```

Note that no `self` parameter is used when the method gets called.  

## Class And Instance Variables

Python distinguishes between `class` and `instance` variables.  

**Class variables** are values that are associated with every object from that class. That is, every object of that class not only has that variable but that variable is set to the same value and if you change that value for one object you change it for every object (of that class). In Java these would be static member variables.

**Instance variables** are what we would call member variables in Java. Every object of the class has those variables but they each have their own individual values for those variables.  

```Python
class Animal: 
  # define class variables here
  location = "zoo"

  def __init__(self,name,animal_type):
    # define instance variables here
    self.name = name
    self.type = animal_type
    self.count = 1

  def describe(self):
    print ("Name", self.name, "Type", self.type, "Location", self.location)

anim1 = Animal("Bob", "Dog")
anim2 = Animal("Kate", "Cat")

anim2.describe()

anim1.location = "house"
anim1.name = "Fred"

anim2.describe()
```

will output the following

```console
Name Kate Type Cat Location zoo
Name Kate Type Cat Location house
```

Changing `location` for `anim1` has also changed it for `anim2`.  
Changing `name` for `anim1` has also **not** changed it for `anim2`.  



