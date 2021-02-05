---
title: Developing With Classes
permalink: /docs/3-classMethods-2/
---

## Standard Practice

* One of the key advantages of OOP is reusability – making it easy to use code you’ve already developed again. 
* To support this it is standard practice to keep each class in its own file.
* This allows us to simply copy the class file from one project to another.

## Variable Scoping

* **Variable scoping** answers the question: what variables can I use here?
* Basic rule in Java: variables last as long as their enclosing curly brackets (their 'scope’).
* This isn’t quite true but it’s close

```java
void fred(int x) {
	int y = 42;
	String z = “Ostrabagalous”;

	// What variables can I use here?
}
```
* **int x**
* **int y**
*	**String z**

Parameters (the variables in the round brackets that hold values passed in) are available throughout the method. The variables created in the method are also available throughout it.  

```java
void fred(int x) {
	int y = 42;
	String z = “Ostrabagalous”;

	for (int i=0; i<10; i++) {
    int j = 10;
	  // What variables can I use here?
  }
	// How about here?

}
```
**What variables can I use here?**
* **int x**
* **int y**
*	**String z**
* **int j**
* **int i** - but be careful, if you change it you will affect how the loop proceeds

**How about here?**
* **int x**
* **int y**
*	**String z**

**i** and **j** are no longer available as we have passed outside their scope. Their scope is limited to the curly brackets.

```java
for (int i=0; i<10; i++) {
    int j = 10;
	  // What variables can I use here?
}
```

NB **i** is limited to the length of the *loop*. **j** is limited to the length of the curly brackets {} it is made in. It just happens that both are the same length in this case.  

```java
void fred(int x) {
	int y = 42;
	String z = “Ostrabagalous”;
}

void jim(int a) {
	int b = 42;
	String c = “fish”;

	// What variables can I use here?
}
```
**What variables can I use here?**
* **int a**
* **int b**
* **int c**

**x**, **y** and **z** are out of scope in `jim()`.  


