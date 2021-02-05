---
title: Constructor Methods
permalink: /docs/3-classMethods-4/
---

This code is a bit clumsy.  

```java
class Point{
  double x;
  double y;

  void set(double x, double y) {
    this.x = x;
    this.y = y;
  }
}

void main() {
  Point p = new Point();
  p.set(4.2, 5.6);
}
```

What if you forget to call set? What if you want to create multiple points? Can we tidy this up?  

## Constructors

* You can write a special method called a *constructor*.  
* This is just another method, except it is called *automatically* when an object is created.  
* It has the same name as the class.

```java
class Foo{
  int x;
  int y;

  Foo() {
    System.out.println(“Constructing!”);
  }
}

Foo f = new Foo();
```

The method `Foo()` is called automatically when you create a Foo *object* using the line `Foo f = new Foo();`.  

Just like any other method we can pass parameters to a constructor.

```java
class Foo{
  int x;
  int y;

  Foo(int x, int y) {
    System.out.println(“Constructing! ” + x + “ “ + y);
  }
}

Foo f = new Foo(4, 9);
```

This allows us to write much tidier code that is easier to follow.  

```java
class Point{
  double x;
  double y;

  void set(double x, double y) {
    this.x = x;
    this.y = y;
  }
}

void main()
{
  Point p = new Point();
  p.set(4.2, 5.2);
}
```
becomes
```java
class Point{
  double x;
  double y;

  Point(double x, double y) {
    this.x = x;
    this.y = y;
  }
}

void main()
{
  Point p = new Point(4.2, 5.2);
}
```

You can write as many constructors as you like and Java will pick the appropriate one.

```java
class Point{
  double x;
  double y;

  Point(double x, double y) {  // Constructor 1
    this.x = x;
    this.y = y;
  }
  Point() { // Constructor 2
    this.x = 0;
    this.y = 0;
  }
}

void main()
{
  Point p = new Point(4.2, 5.2);  // Calls Constructor 1
  Point p = new Point();  // Calls Constructor 2
}
```

The only restriction to this is that the arrangement of parameter types must be different for every constructor.  

So we could add `Point(double x, double y, String name)` but if we tried to add `Point(double a, double b)` we would get an error because we would have two constructors that both had two doubles as their parameters. The parameter names don't matter, only their types.  

Just to add a little more confusion we can have `Point(int x, String name)` and `Point(String name, int x)` because the order is different.  

So, basically, if you imagine stripping out the parameter names `Point(double a, double b)` becomes `Point(double double)` and we already have one constructor with those types in that order. Simple!  

## Polymorphism
This ability to have multiple methods is called **overloading**. We *overload* the *method name* with *multiple methods*. This can be done with any method, not just constructors

Overloading methods is part of a concept called **polymorphism**.
* **poly** – many
* **morph** – forms

Polymorphism is one of the key features of object oriented programming.  