---
title: Protected 
permalink: /docs/4-encapsulation-3/
---

The `public` keyword makes member variables and class methods available to everyone.  

The `private` keyword makes member variables and class methods restricted to the object itself.  

There is one other keyword we can use `protected`.  

`protected` restricts access to member variables and class methods to the object and any objects in sub-classes derived from it.  

If we have the animals hierarchy from the inheritance section - 

![Simple animal family tree](https://ysjprog2.netlify.app/assets/img/topics/5inherit/animaltree.png)

and we create a basic `Animal` and an `Ape`, then the `Ape`.

```java
public class Animal {
  public String name;
  private String food;
  protected String type;
}

public class Ape extends Animal {
  public void doStuff(Animal other){
    animal.name = "Bob"; // Fine because name is public
    animal.food = "Steak"; // Broken, food is private
    animal.type = "Tiger"; // fine, type is protected but Ape is a child class of Animal
  }
}
public void main(){
  Animal animal = new Animal();
  Ape monkey = new Ape();

  monkey.doStuff();

  animal.name = "Fred"; // fine name is public
  animal.food = "Mushrooms"; // broken, food is private
  animal.type = "Elephant"; // broken because type is protected and main isn't a child class of animal.
}
```

*Note this isn't about a child class's access to its own methods and variables that are inherited from its parent class. It is about an object from the child class being able to access the variables and methods of an object created from its parent class.*

