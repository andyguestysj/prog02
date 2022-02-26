---
title: Encapsulation
permalink: /docs/4-encapsulation-1/
---
## Recap

Last week we talked about  
* **Class Methods**
* **Scope** of variables and member variables in particular

## Public & Private

So far we have been not using (or ignoring) public and private keywords (for the most part). These can be used to decide who can access parts of our objects.  

## private & public

```java
class Foo {  
  private int x;
  int y;

  void setup() {
    x = 42;  // Ok
  }
}

class Bar {
  public static void main (String [] args) { 
    Foo f = new Foo();
    f.x = 42; // !!! Error !!!
    f.y = 71; // Ok
  }
}
```

`f.x` is **private** so it can only be accessed in the object. We can alter it in `setup()` with `x = 42;` because `setup()` is part of the object. We cannot access it in `main()` because `main()` is not part of the object.  

**private** means that only methods in the same class can access that variable. Any other attempts to access will fail to build.  

**public** means that anybody can access the variable.

Not specifying anything is a little strange — it means ‘package private’. This is like private except that classes in the same package can also see it. I think this is confusing — I suggest always using either public or private.  

There is also **protected** but we can ignore that for the time being. We will come back to it later.  

**private** and **public** can also be used with methods. They decide who can call a method.  

### public and private methods

```java
public class Foo {  
  private int x;  
  private int y;

  public Foo( int x, int y) {  
    this.x = x;
    this.y = y;
  }

  private void printMe () {  
    System.out.println(x + y);
  }
}

public class Bar {
  public static void main( String [] args) {  
    Foo f = new Foo (42 , 99);
    f.printMe(); // error;
  }
}
```

From now on we should try to make sure that all *member variables* and *class methods* are declared as **public** or **private**. At least until we need to use protected :-).  

Note also that we are declaring the class itself to be **public** with the line `public class Foo`.  

**Why public and private?**

It is useful for us that an object can keep control of its data and hide how it works. This is called **encapsulation** and it is another of the fundamental principles of object oriented programming.  

## Encapsulation

Consider the class below.  

```java
public class Date {
  private int day;
  public int month;
  public int year;

  public void setDay(int d) {
    if (d>31) {
      d = 31;
    }
    day = d;
  }

  public int getDay() {
    return day;
  }
}
public static void main(String [] args) {
  Date d = new Date();
  d.setDay(42);
  System.out.println(d.getDay());
}
```

By making `day` *private* we force other objects to use the `setDay()` method to change its value. This means we can control how day is changed. In this case we are forcing a simple bit of data validation. If anyone tries to set `day` to a number greater than 31 the method restricts it to 31. No month has more than 31 days. Of course we aren't checking the month and year to find out the real limit and we aren't stopping numbers less than one but its a start!  

**Encapsulation** lets us hide our internal workings. This isn't so much about secrecy as it is convenience.  

### Public & Private : a car

**PUBLIC**
* Turn the key, put it in gear and press ‘accelerate’: we hear a rumbling noise and we  start moving forwards.  

**PRIVATE**
* Turn on the electrical system.  
* Check that the keycode is correct for the ECU.  
* Power the starter motor.
* Open throttle body to increase air intake.

As a *driver* we don't care about the private stuff. We don't care what happens when we turn the key, we only case that the engine starts. 

**Encapsulation** is about distinguishing between the **public interface** and the **private operation** of a class.  

Consider the following classes.

```java
public class Date {
  private int day;
  private int month;
  private int year;

  public Date(int day, int month, int year)
  {
    this.day = day;
    this.month = month;
    this.year = year;
  }
}

public class Date {
  private int[] theDate;

  public Date(int day, int month, int year)
  {
    theDate = new int[3];

    this.date[0] = day;
    this.date[1] = month;
    this.date[2] = year;
  }

}
```

When we are working with the `Date` class anywhere outside of `Date` in our program we don't need to care or even know how the date is actually stored. Either version of the `Date` looks and works the same to other objects.  

So **encapsulation** lets us hide the internal workings of a class and present a public interface for it to the rest of the code. The rest of the code is forced to use the public interface, the public methods (and sometimes member variables) to use the class/object. This means we can control *how the class is used*, giving us control over how member variables are set and methods are used.  

We can use this to make developing and testing code easier since we know that the class will only be used properly, providing we code it that way of course :-).   

It also makes it easier to maintain the class. We can go in to the class and make any changes we want, providing we keep the public method names, parameters and return values the same.  

