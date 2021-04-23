---
title: Basics
permalink: /docs/9-python-2/
---

## Python Syntax Oddities

Python works in its own special way. It kinda makes sense when you are focusing on Python but when you are changing between languages it can get confusing/frustrating.

### Comments

Comments in Python begin with the hash `#` and continue to the end of the line.

### Variable types

Python doesn't have variable types. Well that's not true, it does have variable types but you don't declare variables with types. 

You want to create an integer called myInteger with a value of 1? `myInteger = 1`. Python will work out the type for itself. But even then `myInteger` isn't an integer variable as we would normally think of it. If you then did `myInteger = myInteger + 2.3` it would change to being a float so it could store the result of 3.3. 

Java (and C#) are what we call *strongly typed* languages. Each variable has a *type*, that type is defined when the variable is created and that variable will remain that type until the programme ends. Python is not a *strongly typed* language. Variables store whatever type is required at the time and will change if they need to.

### End of statement

Java used the semi-colon `;` to indicate that a statement has finished. Python does not, in Python the statement continues till the end of the line. This isn't a big change most of the time its just a bit of a pain and you'll constantly keep putting semi-colons at the end of lines in Python and then have to delete them. By the time you stop doing that you'll be using Java again and then screwing up by not putting semi-colons at the end of lines.

### Scope

We talked about scope and which variables are in scope previously. In Java scope is defined (mostly) by curly brackets `{ }`. They are use to determine the scope of variables and also to determine the scope of code associated with something. The code that makes up a method is defined by the curly brackets that begin immediately after the parameters. 

```java
public void aMethod(int anInteger){
  // any code in here is part of the method
}
```

Similarly we use the brackets to determine what is part of loops and if statements. 

```java
for (int i=0; i<10; i++){
  // code in here is part of loop
  if (i % 2 == 0){
    // code here is carried out if i % 2 == 0
  } else {
    // code here is carried out if i % 2 != 0
  }
}
// Code here is not part of the loop
```

Python does not use brackets to define scope, instead it used **indentation**. Code is part of a method, loop, if statement, etc. if it is *indented once* from the start of the statement.

```python
for i in range(0,10):
  # code in here is part of loop
  if i % 2 == 0:
    # code here is carried out if i % 2 == 0
  else:
    # code here is carried out if i % 2 != 0  
# Code here is not part of the loop
```

You **must** use indentation to denote scope and you **cannot** use indentation for any other reason.

### For Loops

Since we've just used a for loop we'll cover them now. 

A standard for loop is in the form  

```python
for variable in range(start, end):
  print variable
```

`range(start, end)` generates a set of numbers that start at `start` and don't include the end point `end`. So to loop from 0 while <10 (as in the Java example) we would use `range(0,10)`. 

Note also the for line ends in a colon `:`.  

#### range()

`range()` can be used with one, two or three parameters.

`range(5)` will count from 0 to 4.
`range(4,7)` will count from 4 to 6.
`range(10, -10, -3)` will start at 10, subtract 3 each time and stop when it gets to, or gets past) -10.

`range(start, stop, step)`  

For loops can also work with sequences. 

```python
for x in [4,7,3,8]:
  # x will work its way through 4,7,3,8
```

and sequences can be anything

```python
for x in ["cat", "dog", "mouse"]:
  # x will work its way through "cat", "dog", "mouse"
```

and because Python is not a typed language the type of data in the sequence can vary.

```python
for x in ["cat", 1, 2.5, int(5.6)]:
  # x will work its way through "cat", 1, 2.5, int(5.6)
```

You just need to be careful how you use those items.  

### If

If statements in Python work as normal but they have some formatting/syntax differences. 

```python
a = 200
b = 33
if b > a:
  print("b is greater than a")
elif a == b:
  print("a and b are equal")
else:
  print("a is greater than b")
```

Indentation is used to determine what code is part of each condition.  
A colon is used to indicate the end of the test condition.  
The keyword `elif` is used instead of `else if`.  

### pass

Python doesn't like scope without code. You can't create methods without any code in them, if you create a condition in an `if` then you need to include code in there (not just comments).  

Thankfully Python includes the keyword `pass`. This keyword does nothing other than fulfil the requirements for there to be some code.

```python
a = 200
b = 33
if b > a:
  print("b is greater than a")
elif a == b:
  pass
else:
  print("a is greater than b")
```

## Method Definition

The way methods work in Python is the same as most other languages. They have a name, they may have one or more parameters passed in to them and they may return a value.  

However since Python is not a typed language we do not give our parameters types, nor do we define a return type. Indeed the first line of the method does not even tell us if the method returns a value or not.

The keyword `def` indicates the start of a method. It has a name and a list of parameters(without types) as normal. The first line ends with a colon `:` to indicate the code begins on the next line.  

Code that makes up the method is indented in from the level the method is declared at.

Any return value is returned with `return value`. The return type can be anything, more than that it can be different things at different times.  

```python
def methodName(param1, param2):
  # method code here
  # if returning a value do it as shown below
  # return value 
```







