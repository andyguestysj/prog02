---
title: Inheritance
permalink: /docs/5-inheritance-2/
---

## Inheritance

Imagine we are creating a game with lots of different types of animals in. We might start by creating an *animal* class something like this.  

```java
public class Animal {
  public String name; // The animal's name e.g. "Bob"
  public String type; // The animal's type e.g. "Badger"
  public String eats; // What it likes to eat "Worms"

  public Animal(String name, String type, String eats){
    this.name = name;
    this.type = type;
    this.eats = eats;
  }

  public void run() {
    // make the animal run
  }
}

void main() {
  Animal catCassie = new Animal("Cassie","Cat","Cat Food");
  Animal dogDan = new Animal("Dan","Dog","Dog Food");

  catCassie.run();
  dogDan.run();
}
```

That's good, we can create objects for each of our animals and make Dan run after Cassie.  

Then we decide to add a Monkey to the mix.  

```java
  Animal monkeyMel = new Animal("Mel","Monkey", "Bananas");

  robinRobin.run(); // ??
```

Monkeys climb trees. So we'll want that as an option so lets make an `Ape` class to handle the different behaviour.

```java
public class Ape {
  public String name; // The animal's name e.g. "Bob"
  public String type; // The animal's type e.g. "Badger"
  public String eats; // What it likes to eat "Worms"

  public Ape(String name, String type, String eats){
    this.name = name;
    this.type = type;
    this.eats = eats;
  }

  public void run() {
    // make the ape hop
  }

  public void climb() {
    // make the ape fly.
  }
}
```

All fine now. We use `Ape` for all the apes and `Animal` for everything else.  

Oh, maybe we need a snake. They don't run either, they slither. No problem, we'll create a *snake* class and replace `run()` with `slither()`.  We now have three classes. 

```java
public class Animal {
  public String name; // The animal's name e.g. "Bob"
  public String type; // The animal's type e.g. "Badger"
  public String eats; // What it likes to eat "Worms"

  public Animal(String name, String type, String eats){
    this.name = name;
    this.type = type;
    this.eats = eats;
  }

  public void run() {
    // make the animal run
  }
}

public class Ape {
  public String name; // The animal's name e.g. "Bob"
  public String type; // The animal's type e.g. "Badger"
  public String eats; // What it likes to eat "Worms"

  public Ape(String name, String type, String eats){
    this.name = name;
    this.type = type;
    this.eats = eats;
  }

  public void run() {
    // make the ape hop
  }

  public void climb() {
    // make the ape fly.
  }
}

public class Snake {
  public String name; // The animal's name e.g. "Bob"
  public String type; // The animal's type e.g. "Badger"
  public String eats; // What it likes to eat "Worms"

  public Snake(String name, String type, String eats){
    this.name = name;
    this.type = type;
    this.eats = eats;
  }

  public void slither() {
    // make the bird hop
  }
}
```

It is starting to get a bit clunky. Say we want to add a picture of the animal to each object, then we'll need to go through and add the same code to each object. That's manageable with three classes but what if we've ended up adding classes for fish and insects? What if we want dogs to be able to `fetch()` but not cats? We could quickly end up with many very similar classes with repeated code all over the place. It would be awful to use and worse to maintain.  

Fortunately object orientation offers us a solution called **inheritance**. Inheritance lets us set up a family tree like structure of classes.

![Simple animal family tree](https://ysjprog02.netlify.app/assets/img/topics/5inherit/animaltree.png)

We can create an `Animal` *class* as before, but when we create our new classes we can let them **inherit** *member variables* and *class methods* from the `Animal` class.  

```java
public class Animal {
  public String name; // The animal's name e.g. "Bob"
  public String type; // The animal's type e.g. "Badger"
  public String eats; // What it likes to eat "Worms"

  public Animal(String name, String type, String eats){
    this.name = name;
    this.type = type;
    this.eats = eats;
  }

  public void run() {
    // make the animal run
  }
}

public class Ape extends Animal {

  public void climb() {
    // make the ape fly.
  }
}

void main() {
  Animal catCassie = new Animal("Cassie","Cat","Cat Food");
  Animal dogDan = new Animal("Dan","Dog","Dog Food");
  Ape monkeyMel = new Monkey("Mel", "Monkey", "Bananas");

  catCassie.run();
  dogDan.run();
  monkeyMel.climb();
}
```

In the above example the `Animal` *class* works the same as before. The `Ape` *class* **inherits** all the *methods* and *variables* from `Animal` and adds a new *method* `climb()`.

```java
void main() {
  Ape monkeyMel = new Monkey("Mel", "Monkey", "Bananas"); 
  // uses the inherited constructor to set the inherited variable names
  monkeyMel.run(); // uses the inherited run() method
  monkeyMel.climb(); // uses its own climb() method
```

When one class **inherits** from another we say the new class **extends** the old one. This is used in the first line of the class definition.  

```java
public class Monkey extends Animal {
```

Now if we decide that we want our dogs, and only our dogs, to `fetch()`, we can create a new `Dog` class that **extends** Animal.  

```java
public class Dog extends Animal {

  public void fetch() {
    // make the dog fetch.
  }
}
```

If we decide we want to add a picture to every animal we simply update the `Animal` *class*.

```java
public class Animal {
  public String name; // The animal's name e.g. "Bob"
  public String type; // The animal's type e.g. "Badger"
  public String eats; // What it likes to eat "Worms"
  public Image  picture;

  public Animal(String name, String type, String eats, Image picture){
    this.name = name;
    this.type = type;
    this.eats = eats;
    this.picture = picture;
  }

  public void run() {
    // make the animal run
  }
}
```

Now **every** class based on the `Animal` class has a picture included.

## Inheritance Terms

* The class you are inheriting from is called the **parent** or **superclass**.
* The class that is inheriting is called the **child** or **subclass**.