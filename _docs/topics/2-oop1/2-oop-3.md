---
title: More Referencing
permalink: /docs/2-oop-3/
---

## Multiple References To A Single Object

Remember the *references* and the *objects* are different things in memory. It is possible to have *multiple references* all connected to a *single object*.

```java
Foo f = new Foo();
f.x = 42;
f.y = 9;  

Foo g = f;
g.x = 77;
```

![two references to a single object](https://ysjprog02.netlify.app/assets/img/topics/2oop1/simpleobject4.png)

`g.x = 77;`  
* `g` - look in the object labelled `g`  
* `.y` - find its variable `y`  
* `= 77;` - and set it to 77

Since `f` and `g` both *refer* to the same *object*, using either has the same effect.  

## **null** references

What if we have..

```java
class Ostrabagalous {
  int x;
  String y;
}

Ostrabagalous o;
```

What does **o** *refer* to?  

It hasn't been attached to a new *object* by using `= new Ostrabagalous;`. It is basically a blank label that is ready to be attached to an **Ostrabagalous** **object*.  

In Java we say that `o` refers to a **null**. 

We should think of 

```java
Ostrabagalous o;
```

as being equivalent to  

```java
Ostrabagalous o = null;
```

> Note that while this is true in Java it is **not true** of many other languages. In those languages you cannot be sure that a new *reference* will be set to null and you should do it manually for safety reasons. 

So what happens if we do `o.x = 42;`?  

Well, we can't. `o` isn't connected to an object, there is no `x` to set to 42. Java won't even let us try, it will fail to compile.  

So is a null reference useless? No, it comes in useful if we have a number of objects and we need to keep track of them all and we need to know which one of them is special in some way. Imagine we have a racing game. We have objects for each of our racers - PenelopePitstop, DickDastardly, PeterPerfect and ProfessorPatPending. We want to be able to access the race leader quickly without having to check every time, so we create an unlinked reference called Leader and change which racer Leader connects to as the race proceeds.  

```java
Racer PenelopePistop = new Racer();
Racer DickDastardly = new Racer();
Racer PeterPerfect = new Racer();
Racer ProfessorPatPending = new Racer();
Racer Leader;

boolean stillRacing = true;

while (stillRacing)
{
  PenelopePitstop.move();
  DickDastardly.move();
  PeterPerfect.move();
  ProfessorPatPending.move();

  Leader = whoIsWinning();

  Describe(Leader);

  if (hasFinishedRace(Leader))
  {
    stillRacing = false;
  }

}

void Describe(Racer leading)
{
  System.out.println("And in the lead is " + leading.Description());
}
```

We can use `Leader` like a temporary *reference*. There isn't a specific `Leader` *object*, instead `Leader` becomes a second *reference* to whichever racer is in the lead.  

### Exercise 1
1. Fork yourself a copy of **javaPoints** from [https://replit.com/@andyguest/javaPoints#Main.java](https://replit.com/@andyguest/javaPoints#Main.java). There is an **Instructions.md** file that covers the exercise.  

