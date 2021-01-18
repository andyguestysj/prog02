---
title: References, Classes & Objects
permalink: /docs/2-oop-2/
---

On this page we are going to take a close look at what happens behind the scenes when we carry out some basic *object* operations. The code below should be familiar and easily understandable, the important thing to learn and to think about is what the code actually does.  

## A Simple Class

```java
class Foo {
  int x;
  int y;
}

Foo f = new Foo();
```

What just happened?  

A number of things happened in one line `Foo f = new Foo();`  
* `Foo f` - create a label (or *reference*) called `f`  
* `new` - creates a new *object*  
* `Foo()` - using a plan (or *class*) called Foo  
* `f = ..` - attach the *reference* to the *object*  

Previously you've thought of `f` **being** the *object*. I'd like you to start thinking now about `f` and the *object* being two separate things. A *reference* called `f` is created in one place in memory and it *refers* to the *object* which is stored somewhere else in memory.  

![f points to object](https://ysjprog02.netlify.app/assets/img/topics/2oop1/simpleobject1.png)

Above we have `f` the *reference* and the *object* as separate location in memory. We say that `f` *refers to* or is a *reference to* the object. 

> `Aside 1` You might also read about `f` storing the *address* of the *object*. Deep down in the code this is what `f` is actually storing. `f` is a variable, much like an integer, where the number stored in `f` is the start of the *object* in memory. `f` is storing the *memory address* of the *object*. You don't need to worry about this in this module, just remember that the *reference* and the *object* are different data, and that the *reference* refers to the *object*.

> `Aside 2` You might also read about `f` *pointing to*, or being a *pointer to*, an *object. This terminology is from the C programming language and is based on how *references* are used in that language. Again you don't need to worry about that in this module. You have to worry about that in Programming 03 next year!

### Changing The Object

```java
class Foo {
  int x;
  int y;
}

Foo f = new Foo();
f.x = 42;
f.y = 9;
```

What just happened?  

Once again a number of things happened in one line `f.y = 9;`  
* `f` - look in the object labelled `f`  
* `.y` - find its variable `y`  
* `= 9;` - and set it to 9

![f.y is updated](https://ysjprog02.netlify.app/assets/img/topics/2oop1/simpleobject2.png)

### Reading The Object

```java
class Foo {
  int x;
  int y;
}

Foo f = new Foo();
f.x = 42;
f.y = 9;
System.out.println(f.x);
```

What just happened?  

Once again a number of things happened in one line `System.out.println(f.x);`  
* `f` - look in the object labelled `f`  
* `.y` - get its variable `y`  
* `System.out.println()` - and print it out

![f.y is read](https://ysjprog02.netlify.app/assets/img/topics/2oop1/simpleobject2.png)

### Multiple Objects Of The Same Class

```java
Foo f = new Foo();
f.x = 42;
f.y = 9;

Foo g = new Foo();
g.x = 66;
g.y = 25;
```

![g.y is updated](https://ysjprog02.netlify.app/assets/img/topics/2oop1/simpleobject3.png)

`g.y = 25;`  
* `g` - look in the object labelled `g`  
* `.y` - find its variable `y`  
* `= 25;` - and set it to 25

It shouldn't surprise you that changing the attributes of `g` has no affect on the attributes of `f`.  

### Why Multiple Objects Of The Same Class

A *class* represents a generic description of some item we have in our system. If we have a number of different items which are very similar and differ only in their details then we can use multiple objects of the same class, with each object representing a different item. 

```java
class Coordinate {  
  int x;
  int y;
}

Coordinate player = new Coordinate(1,5);
Coordinate baddie = new Coordinate(8,12);
```

```java
class Person {
  String name;
  String address;
  String phone;
}
Person personA = new Person();
personA.name = "Fred";
personA.address = "10 Downing Street";
personA.phone = "999";

Person personB = new Person();
personB.name = "Wilma";
personB.address = "10 Downing Street";
personB.phone = "333";
```

### Multiple References To A Single Object

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

### Exercise 1
1. Colours are often represented using a scheme called ‘RGB’. With RGB we specify how much red, green
and blue makes up a colour. 
2. In repl.it create a new Java programme called `RGBColours`
3. Make a Colour class which can hold red, green and blue ints and use it to create objects to represent three colours:
|Colour|Red|Green|Blue|
|---|---|---|---|
|Yellow|255|255|0|
|Purple|128|0|128|
|Orange|255|165|0|

### Exercise 2
1. Fork yourself a copy of **javaPlayers** from [https://repl.it/@andyguest/javaPlayers#Main.java](https://repl.it/@andyguest/javaPlayers#Main.java). There is an **Instructions.md** file that covers the exercise.  

### Exercise 3
1. Fork yourself a copy of **javaPoints** from [https://repl.it/@andyguest/javaPoints#Main.java](https://repl.it/@andyguest/javaPoints#Main.java). There is an **Instructions.md** file that covers the exercise.  


