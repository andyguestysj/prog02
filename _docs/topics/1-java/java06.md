---
title: Variables
permalink: /docs/java06/
---

In Java, as in any programming language, we often need to store values. We do this using variables. Variables have types and thier type defines the type of values they store - integers, real numbers, strings and boolean values are the most frequently used. 

Python is *dynamically typed language*. Python assigns and changes the type of variables as you change how they are used.  

```python
myVariable = 50
myVariable = 12.2
myVariable = "Fred"
```

In the Python code above the first line creates a variable called myVariable and assigns the value 50 to it. 50 is an integer so myVariable is an integer type. The second line assigns the value 12.2 to myVariable. This is a real number so myVariable becomes a real type. In the final line it becomes a string type. 

Java, in contrast, is a *statically typed language*. When a variable is given a type it cannot be changed. In addition the coder **must** define the variable type when it is created.  

```java
myVariable = 50;
```

The code above will generate an error because the type of myVariable has not been defined previously. (But well done on remembering the ; :-)  

To create a variable we need to define it as shown below

```java
int myVariable = 50;

int anotherVariable;

myVariable = 25;
```

We don't have to assign a value to a variable when we create it but we must give it a type. Once we have created a variable we can reuse it without having to redefine it, as shown in the last line.  

Now we have a variable we must remember that its type is fixed.  

```java
int myVariable = 50;

myVariable = 12.2;

myVariable = "Bob";
```

`myVariable` is an integer type (`int`), it cannot store a real number. The line `myVariable = 12.2;` will generate an error. We could convert the `12.2` to an integer, turning it into `12` which could be stored but we would not be storing 12.2. Similarly we cannot store a string in and int type variable.  

### Variable Types - Primitive Variables

Java provides us with a selection of basic variable types.  


|**type**|**description**|**range**|  
|---|---|---|  
|**int**|integer value (32 bits)| -2<sup>31</sup> to 2<sup>31</sup>-1|
|**float**|real value (32 bits)| huge! |
|**boolead**|boolean value (1 bit)| `true` or `false` |
|**char**|single character (16 bits)| |

And because we sometimes want to store a wider range of numbers, or sometimes want to use a smaller range to use less memory, the following are also available.   

|**type**|**description**|**range**|  
|---|---|---|  
|**short**|integer value (16 bits) | -32,768 to 32,767|
|**long**|integer value (64 bits)| -2<sup>63</sup> to 2<sup>63</sup>-1|
|**double**|real value (64 bits)| staggeringly huge! |

We also have a `String` option which is not a primitive variable but is actually a Java object. This means we can create string "variables" like `String name = "Andy";` but strings don't quite work like other primitive variables.  

For example;

```java
String name1 = "Andy";
String name2 = "Andy";

if (name1 == name2){
  System.out.println("Same");
}
else{ 
  System.out.println("Different");
}
```

will result in the output `Different` because the `==` is asking if the two are the same object which they are not, they are different objects with the same data. We'll look in to what this means when, yep, we look at OOP.  

For now, use the code below 

```java
String name1 = "Andy";
String name2 = "Andy";

if (name1.equals(name2)){
  System.out.println("Same");
}
else{ 
  System.out.println("Different");
}
```

or

```java
String name1 = "Andy";
String name2 = "Andy";

if (name1.toString() == name2.toString()){
  System.out.println("Same");
}
else{ 
  System.out.println("Different");
}
```

### Full Primitive List (+ String!)

|**type**|**description**|**range**|  
|---|---|---|  
|**int**|integer value (32 bits)| -2<sup>31</sup> to 2<sup>31</sup>-1|
|**float**|real value (32 bits)| huge! |
|**boolead**|boolean value (1 bit)| `true` or `false` |
|**char**|single character (16 bits)| |
|**short**|integer value (16 bits) | -32,768 to 32,767|
|**long**|integer value (64 bits)| -2<sup>63</sup> to 2<sup>63</sup>-1|
|**double**|real value (64 bits)| staggeringly huge! |
|**String**|any text string| |

### Constants

Sometimes we want to create a named "variable" that we want to have a fixed value. We often do this to avoid using *magic numbers*. We do this by starting the variable definition with the keyword `final`. Variables created this way cannot be changed. We typically use full uppercase for such variables to make them stand out.  

```java
final int MONDAY = 1;
```