---
title: References, Classes & Objects
permalink: /docs/2-oop-2/
---

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

![f points to object](../../assets/img/topics/2oop1/simpleobject1.png)

Previously you've thought of `f` **being** the *object*. I'd like you to start thinking now about `f` and the *object* being two separate things. A *reference* called `f` is created in one place in memory and it *refers* to the *object* which is stored somewhere else in memory.  



