---
title: Branching
permalink: /docs/java09/
---

Without branching we can only write the simplest of applications.  

### if then else

The simplest form of branching is the `if` statement.

 ```java
 if (this is true){
   do this
 }
 else if (this is true){
   do this
 }
 else {
   do this
 }
 ```

#### Simple Comparisions

`this is true` can be anything that returns a `true` or `false` value. Typically this is a simple comparison.  

```java
int a = 5;
int b = 7;

if (a==5){

}
else if (b!=5){

}
else { 

}
```

#### Compound Comparisions

We can compund multiple comparisions with logical ANDs, ORs and NOTs.  

|Operator|Operation|
|---|---|
|&&|logical AND|
|\|\||logical OR|
|!|logical NOT|

```java
if ((a>3) && (a<6)){
  do this
}
```

I strongly recommend using brackets to enforce precedence. Also rememberr that you can insert whitespace and blank lines to make things clearer.  

```java
if (
      (a==5)
      || 
      ((a==6) && (b==6))
      || 
      (a==b)
   )
   {
     do this
   }
```

is easier to follow than  

```java
if ((a==5)||((a==6) && (b==6))||(a==b)){
  do this
}
```

and if statements can get much trickier than that!  

### Switches

Sometimes we want to examine a single variable and react in a number of different ways depending on its value. A `switch` is typically easier to follow than a long set of ifs.  

```java
int myVariable = 2;
switch (myVariable){
  case 0:     do this;
              do this too;
              break;
  case 1:     do this;
              do this too;
              break;
  case 2:     do this;
              do this too;
              break;
  default: 
              do somthing generic;
}
```

Here the value that is stored in the variable is matched to the case and the code associated with it is run. If the variable doesn't match any case the default is run. Note that the reason only the code for the case is run is the `break`. If you remove the `break` all the code from the matching case onwards will be run.  