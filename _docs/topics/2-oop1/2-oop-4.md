---
title: References & Methods
permalink: /docs/2-oop-4/
---

## Method Variable Parameters

What happens when we have a method that has parameters and we use it?  

```java
void myGreatMethod(int n)
{
  System.out.println(n);
}

void main()
{
  int x = 42;
  myGreatMethod(x);
}
```

* `int x = 42;` creates a variable in memory called `x` and stores the value 42 in it.
* `myGreatMethod(x);` calls the method `myGreatMethod` (and passed in the value stored in `x`)
* `void myGreatMethod(int n)` means that when the method is called a variable called `n` is created in memory. The value in `x` is **copied** in to the new variable `n`.
* `System.out.println(n);` outputs the value stored in `n` to the screen.

The variables `x` and `n` are completely separate from each other but store the same value. 

```java
void myGreatMethod(int n)
{
  n = n + 5;
  System.out.println("n is " + n);
}

void main()
{
  int x = 42;
  myGreatMethod(x);
  System.out.println("x is " + x);
}
```

Because they are different variables, this modified code will result in the following output.  

```
n is 47
x is 42
```

Changing `n` in the method does not change `x` in main().

## Method Reference Parameters

We can pass *references* as method parameters just as easily as we pass variable parameters.

```java
class Frobozz {
  String a;  
  String b;
}

void main ( String [] args ) 
{  
  Frobozz f = new Frobozz();  
  f.a = "Hello world";  
  my GreatMethod(f);
}

void my GreatMethod (Frobozz g) 
{  
  System.out.println(g.a);
}
```

* `Frobozz f = new Frobozz()` creates a *reference* in memory called `f`. It creates a new `Frobuzz` *object* and connects the `f` *reference* to it.
* `f.a = "Hello world";` sets the `a` member variable of the *object* that `f` *refers* to to "Hello world"
* `myGreatMethod(f);` calls the method `myGreatMethod` (and passed in the *reference* stored in `f`)
* `void myGreatMethod(Frobuzz g)` means that when the method is called a reference called `g` is created in memory. The *reference* in `f` is **copied** in to the new reference `g`.
* `System.out.println(g.a);` outputs the String stored in `g.a` to the screen.

The *references* `f` and `g` are completely separate from each other but store the same *reference*.  

![passing a reference to a method](https://ysjprog02.netlify.app/assets/img/topics/2oop1/passref.png)

So passing a *reference* is just like passing a *variable* right? Unfortunately no, there is one big difference. Remember what happened before when we had two references to the same object? When you use a *reference* to change an *object* **you change the *object***.

```java
class Frobozz {
  String a;  
  String b;
}

void main ( String [] args ) 
{  
  Frobozz f = new Frobozz();  
  f.a = "Hello world";  
  my GreatMethod(f);
  System.out.println("f is " + f.a);
}

void my GreatMethod (Frobozz g) 
{  
  g.a = "Hello Mum";
  System.out.println("g is " + g.a);
}
```

The output of the above looks like this  

```
g is Hello Mum
f is Hello Mum
```

Because we passed a *reference* to an object to the method, changes within the method remain after we leave the method.  

>Another way of putting it is that we **don't pass the *object* to the method**. The *object* is sitting somewhere else in memory. We have a *reference* that tells us where to find the *object*. When we pass the *reference* to a method what we are doing is copying the *address* of the object to a new *reference* in the method. That new *reference* now refers to the original object.  

So the tl:dr version is if you pass a *variable* to a method then any changes made to that variable in the method are lost when you leave the method. If you pass a *reference* to a method then any changes you make using the *reference* are changes to an *object* which remain when you leave the project.  

