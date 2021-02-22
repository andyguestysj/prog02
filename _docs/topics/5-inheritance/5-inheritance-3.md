---
title: Inheritance & Polymorphism
permalink: /docs/5-inheritance-3/
---

## Polymorphism

We looked at **polymorphism** before. Polymorphism is what allows us to have multiple methods with the same name.  

```java
public class Animal {
  public String name; // The animal's name e.g. "Bob"
  public String type; // The animal's type e.g. "Badger"
  public String eats; // What it likes to eat "Worms"
  public Image  picture;

  public Animal(String name, String type, String eats){
    this.name = name;
    this.type = type;
    this.eats = eats;
  }

    public Animal(String name, String type, String eats, Image picture){
    this.name = name;
    this.type = type;
    this.eats = eats;
    this.picture = picture;
  }

  public void run() {
    // make the animal run
  }

  public void run(int velocity) {
    // make the animal run at velocity
  }
}
```

We can **overload** existing methods with new ones.  

## Inheritance and Polymorphism

By combining inheritance with polymorphism we can use the same method names in the children classes but make them do different things.  

(cutting out of the rest of the code for clarity)  

```java
public class Animal {

  public void speak() {
    // make a generic animal noise
    System.out.println("grrr");
  }
}

public class Dog extends Animal {
  public void speak() {
    // bark
    System.out.println("Woof");
  }
}

void main() {
  Animal catCassie = new Animal("Cassie","Cat","Cat Food");
  Dog dogDan = new Dog("Dan","Dog","Dog Food");

  catCassie.speak();
  dogDan.speak();
}
```

Will give the output  

```console
grrr
Woof
```

The system will look first for a method of the name `speak()` in the class and if it doesn't find one it will look in the parent class and use it if it finds one.  

```java
public class Animal {

  public void speak() {
    // make a generic animal noise
    System.out.println("grrr");
  }
}

public class Dog extends Animal {
  public void speak() {
    // bark
    System.out.println("Woof");
  }
}

public class Cat extends Animal {
}

void main() {
  Animal catCassie = new Animal("Cassie","Cat","Cat Food");
  Dog dogDan = new Dog("Dan","Dog","Dog Food");

  catCassie.speak();
  dogDan.speak();
}
```

Will still give the output  

```console
grrr
Woof
```

because the `Cat` class doesn't implement a `speak()` method.  

### Deliberately Accessing The Parent's Methods

Sometimes we deliberately want to access the parent's version of a method. Sometimes it is a more appropriate method but more often we want to do everything the parent's method does and do something else too. Consider the set up below.

```java
public class Animal {
  public String name; // The animal's name e.g. "Bob"
  public String type; // The animal's type e.g. "Badger"
  public String eats; // What it likes to eat "Worms"
  public Image  picture;

  public Animal(String name, String type, String eats){
    this.name = name;
    this.type = type;
    this.eats = eats;
  }
}

public class Dog extends Animal {
  public boolean collar; // Does the dog have a collar
}
```

We've added a new member variable to the `Dog` class to indicate if it has a collar or not. We want a constructor that does everything the Animal constructor does *and* set the collar variable to true or false. We *could* add a complete constructor to `Dog`. 

```java
public class Dog extends Animal {
  public boolean collar; // Does the dog have a collar

  public Dog(String name, String type, String eats, boolean collar){
    this.name = name;
    this.type = type;
    this.eats = eats;
    this.collar = collar;
  }
}
```

But then if we change how the Animal constructor works we'll have to make the same changes to the Dog class, and any other classes. Instead we can use the **super** keyword to access the parent class and call its constructor.  

```java
public class Dog extends Animal {
  public boolean collar; // Does the dog have a collar

  public Dog(String name, String type, String eats, boolean collar){
    super(name,type, eats);
    this.collar = collar;
  }
}
```

Used in this form **super()** refers to the constructor for the parent class. Now the `Dog` constructor calls the `Animal` constructor and passes on the relevant values. Once that is complete it sets the `collar` variable.  

You can also use **super** to access other methods in the parent in the form **super.methodName();**.  

```java
public class Animal {
  public String name; // The animal's name e.g. "Bob"
  public String type; // The animal's type e.g. "Badger"
  public String eats; // What it likes to eat "Worms"
  public Image  picture;

  public Animal(String name, String type, String eats){
    this.name = name;
    this.type = type;
    this.eats = eats;
  }

  public void run(){

  }
}

public class Dog extends Animal {
  public boolean collar; // Does the dog have a collar

  public void run(){
    super.run();
    // do dog specific running stuff here!
  }
}
```


## Inheritance & Methods

Three things you can do with methods and inheritance.  

* **Add a new method**
* **Replace a method**
* **Extend a method**

```java
public class A {

  public void foo() {
    // do some clever stuff
  }

  public void crash() {
    // do some clever stuff
  }
}

class B extends A {  

  // Add a method
  public void bar() {
    // do some other stuff
  }

  // Replace a method
  public void foo() {
    // do some other stuff
  }

  // Extend a method
  public void crash() {
    super.crash();
    // do some clever stuff
  }
}
```
