---
title: Inheritance
permalink: /docs/8-csharp-3/
---

## Inheritance

Inheritance in C# works very similarly to inheritance in Java but has a few formatting/syntax differences. 

```c#
public class Animal
{
  private string name;
  private string type;
  private string eats;

  public Animal()
  {    
  }

  public Animal(string name, string type, string eats)
  {
    this.name = name;
    this.type = type;
    this.eats = eats;
  }

  public string Name
  {
    get { return name; }
    set { name = value; }
  }

  public virtual void speak() {
    // make a generic animal noise
    Console.WriteLine("grrr");
  }
}

public class Dog : Animal
{
  public Dog(string name, string type, string eats):base(name, type, eats){
    
  }
  public override void speak() {    
    Console.WriteLine("woof");
  }
}
```

### Constructor Changes

You must provide a zero argument **constructor** in a parent class. 

```c#
  public Animal()
  {    
  }
```

And you must provide the constructor in the child class, even if you want it to function the same as the parent class. 

```c#
  public Dog(string name, string type, string eats):base(name, type, eats){
    
  }
```

In the child class we can use the `:base()` to first call the parent's constructor. This is equivalent to the Java below

```java
  public Dog(string name, string type, string eats){
    super(name, type, eats);
  }
```

### Overriding Methods

To override a method you have to mark the method in the **parent** as `virtual` and in the **child** as `override`.

```c#
public class Animal
{
  public virtual void speak() {
    // make a generic animal noise
    Console.WriteLine("grrr");
  }
}

public class Dog : Animal
{
  public override void speak() {    
    Console.WriteLine("woof");
  }
}
```

Note that the `virtual` method in the parent is an actual method, it is not abstract. 

You can call the parent's method by using the `base` keyword.

```c#
public class Dog : Animal
{
  public override void speak() {    
    base.speak();
    Console.WriteLine("woof");
  }
}
```

### Abstract Classes

Abstraction works similarly to Java. We cannot create objects for abstract classes. In child classes we *must* implement any **abstract methods** declared in the parent.  

```c#
abstract class FourLeggedAnimal
{
    public abstract string Describe()
    {
        return "This animal has four legs.";
    }
}


class Dog : FourLeggedAnimal
{
    public override string Describe()
    {
        string result = base.Describe();
        result += " In fact, it's a dog!";
        return result;
    }
}
```

