---
title: Recap
permalink: /docs/3-classMethods-1/
---

Video of this lecture.  [https://web.microsoftstream.com/video/6791572e-6620-48e6-ad4d-fbbf8b3d694a](https://web.microsoftstream.com/video/6791572e-6620-48e6-ad4d-fbbf8b3d694a)


## Recap

Last week we talked about  
* **Classes** - the 'plan' or 'blueprint' for how to make..  
* **Objects** - blocks of memory containing..  
* **Member Variables** - stored within the class and..  
* **References** - 'pointers' to objects so we can find and use them

### A Simple Class

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

A number of things happened in one line `Foo f = new Foo();`  
* `Foo f` - create a label (or *reference*) called `f`  
* `new` - creates a new *object*  
* `Foo()` - using a plan (or *class*) called Foo  
* `f = ..` - attach the *reference* to the *object*  

![f points to object](https://ysjprog2.netlify.app/assets/img/topics/2oop1/simpleobject1.png)  

### Multiple Objects Of The Same Class

```java
Foo f = new Foo();
f.x = 42;
f.y = 9;

Foo g = new Foo();
g.x = 66;
g.y = 25;
```

![g.y is updated](https://ysjprog2.netlify.app/assets/img/topics/2oop1/simpleobject3.png)

### Multiple References To A Single Object

Remember the *references* and the *objects* are different things in memory. It is possible to have *multiple references* all connected to a *single object*.

```java
Foo f = new Foo();
f.x = 42;
f.y = 9;  

Foo g = f;
g.x = 77;
```

![two references to a single object](https://ysjprog2.netlify.app/assets/img/topics/2oop1/simpleobject4.png)