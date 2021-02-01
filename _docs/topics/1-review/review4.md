---
title: Follow Up
permalink: /docs/review4/
---

I noticed some people were struggling over the same issues last week, so here are some tips and guidance.  

### Starting A New Program

When you create a new program, in Repl.it or Eclipse, you will be given a project with a `Main.java` file. In that file there will be a `Main` class and a `main()` method. This `main()` method is the entry point for the program when you run it. This should be the only `main()` in your program.  

### Program Flow

When you run your code it starts at the beginning of the `main()` method which is typically in the Main class (in the Main.java file). The `main()` can be in a different class, just remember that it is the top level of your code. Whatever class/file your `main()` is in, you **cannot** create an object of that class within your code.  

The simplest approach is to always have a `Main` class with the `main()` method in a `Main.java` file.

No objects are created unless they are created in the `main()` method or in another method called from the `main()`.  

The code is executed step by step, from the first line of `main()`. When objects are created or object methods are called, the code jumps to the method defined in the class and runs through that method, line by line, returning to `main()` when they are complete. If the called method calls another method then control passes to *that* method until it completes and then back tracks until it reaches `main()`.

### Object Lifespan and Activity

Objects exist/live in memory until they are explicitly delete or the scope in which the variable referencing that object ends. 

*However* objects are only active, only doing stuff/running methods, when their methods are called. 

If you create an object on the first line of `main()` then have one hundred lines of code before you finally call a method for that object then the object will **exist** from the start of your code but won't do anything till the hundred and second line.

### Creating A New Class

If the exercise asks you to create a new class you should create a new file and give it the name of the class. In Java the **classes** begin with an **upper case** letter, **variables** and **objects** begin with a **lower case** letter.  

So if the exercise asks you to create a class called `Simple` you should create a new file and call it `Simple.java`. Inside the file the first thing you should do is put in the basic class definition. In this case that would be :-  

```java
public class Simple {

}
```

### Creating An Object

To create an object you need to used code like :- 

```java
Simple mySimpleObject =  new Simple();
```

< ClassName > < ObjectName > = new < ClassConstructor >  

The < Class Constructor > is the constructor method from the class that is used to create an object of the class. If you do not define a constructor one is create by default with no parameters.  

If the exercise asks you to create an object of a class then this will usually happen in the `main()` method of the `Main` class (in the `Main.java` file!). Sometime you may want an object to create another object, to do this the new object would be created in a method of the original object.  

### Constructor Methods

Constructor methods are methods used to define what happens when an object is created from a class. It looks something like this, using the Simple class as an example.

```java
public class Simple {

  public Simple()
  {

  }

}
```

Note that no return type is defined. This is because a constructor always returns an object for the class it is part of.  

Just like any other method we can take advantage of **polymorphism** (we'll take about this later) to have multiple constructors with different parameters (so long as each constructor has a different combination of numbers and types of parameters).  

```java
public class Simple {

  public int aNumber;
  public String aString;

  public Simple()
  {
    aNumber = 1;
    aString = "Hello";
  }

  public Simple(int iNumber)
  {
    aNumber = iNumber;
    aString = "Hello";
  }

  public Simple(int iNumber, String sString)
  {
    aNumber = iNumber;
    aString = sString;
  }
}
```

The above is perfectly acceptable and the computer will work out which constructor to use based on the parameters you call it with.  

```java
class Main {
  public static void main(String[] args) {
    
    Simple myObject1 = new Simple();
    Simple myObject2 = new Simple(5);
    Simple myObject3 = new Simple(5,"Goodbye");
  }
}
```
