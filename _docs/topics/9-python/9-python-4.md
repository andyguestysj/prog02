---
title: Inheritance
permalink: /docs/9-python-4/
---

## Inheritance

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

  def speak(self):
    # make a generic animal noise
    print("grrr")

class Dog(Animal):

  def __init__(self, name, type, eats):
    # call the parent's constructor - remember to include self!
    super().__init__(self, name, type, eats)
    # add any child specific code
    self.collar = True

  def speak(self):
    # make a generic animal noise
    print("woof")
```

### Abstract Classes/Methods

Python does not have abstract classes by default. There is a module called Abstract Base Classes (ABC) that can be used to create abstract classes. I'm not going to cover that here.

### Multiple Inheritance

Python also allows us to create child classes that inherit from multiple parents. Again I'm not going to cover this here.

