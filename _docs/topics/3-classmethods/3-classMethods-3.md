---
title: Class Methods
permalink: /docs/3-classMethods-3/
---

You can put methods as well as variables into classes. These methods can see the variables of the object (as defined by the class).  

```java
class Foo{
  int x;
  int y;

  int sum() {
    return x + y;
  }
}

Foo f = new Foo();
f.x = 42;
f.y = 9;
int s = f.sum();
```

Within the method `sum()` any and all class *member variables* are in scope. Remember that *member variables* are variables that are declared as part of the class. 

```java
class Foo{
  int x;
  String y;

  int bye() {
    y = “Goodbye”;
  }
}

void main() {
  Foo f = new Foo();
  f.x = 42;
  f.y = “Hello”;
  System.out.println(f.y);
  f.bye();
  System.out.println(f.y);
}
```

produces  

```console
Hello
Goodbye
```

Note 1: that while all *member variables* are in scope in all *class methods*, *variables* created in a *class method* are *only available within that method*. The code below will not compile because the *parameter z* and the *method variable w* are out of scope in `broken()`.

```java
class Foo{
  int x;
  int y;

  int sum(int z) {
    int w = 5;
    return w + x + y + z;
  }
  
  int broken() {
    return w + x + y + z;
  }
}
```

You will hear variables declared in methods called *local variables*. The scope of these variables is limited to the methods they are in, they are only available *locally*.

Note 2: this rule applies even when the same name is used for local variables in different methods.

```java
class Foo{
  int x;
  int y;

  int sum(int z) {
    int w = 5;
    return w + x + y + z;
  }
  
  int brokenIsFixed(int z) {
    int w = 6;
    return w + x + y + z;
  }
}
```

The *parameter z* and the *method variable w* in `sum()` and completely different variables from the *parameter z* and the *method variable w* in `brokenIsFixed()`. Changing `w` in `sum()` has no effect on the `w` in `brokenIsFixed()`. *Member variables* `x` and `y` have a scope which encompasses both methods so they are the same `x` and `y` in both.  

However there can be some ambiguity..

```java
class Foo{
  int x;
  int y;

  void setX(int x) {
    System.out.println(x);
  }
}

void main() {
  Foo f = new Foo();
  f.x = 42;
  f.y = 9;
  f.setX(17);
}
```

What does this print? Does it use the *member variable x* which is set to 42 in the line `f.x = 42;` or does it print 17 which is the parameter value from `f.setX(17);`?  

The correct answer is it prints 17. Why? Where there is an ambiguity the system will choose the one with the most local scope. Or to put it another way, the most recently defined variable with that name. In this case that is the parameter x.  

How do you use the *member variable* in these circumstances? You can always access member variables (within class methods) by using the `this` keyword.  

```java
class Foo{
  int x;
  int y;

  void setX(int x) {
    System.out.println(x);		// Local x, the method parameter
    System.out.println(this.x);	// this is reference to the object the
  }			// method is called on
}

void main() {
  Foo f = new Foo();
  f.x = 42;
  f.y = 9;
  f.setX(17);
}
```

will output  

```console
17
42
```

Note 3: you can always use `this` to access the member variables, even if you don't need to.  

```java
class Foo{
  int x;
  int y;

  void setX(int x) {
    System.out.println(y);		
    System.out.println(this.y);	
  }
}

void main() {
  Foo f = new Foo();
  f.x = 42;
  f.y = 9;
  f.setX(17);
}
```

will output  

```console
9
9
```

