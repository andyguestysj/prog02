---
title: Class Basics
permalink: /docs/8-csharp-2/
---

## C# Classes Overview

Classes in c# look very similar to classes in Java.

Returning to our first inheritance example, we can define an animal class in C# as shown below.

```c#
class Animal
{
  private string name;
  private string type;
  private string eats;

  public Animal(string name, string type, string eats)
  {
    this.name = name;
    this.type = type;
    this.eats = eats;
  }

  public void run()
  {
    // makes the animal run
  }

  public string Name
  {
    get { return name; }
    set { name = value; }
  }
}
```

This is almost identical to Java. We create member variables in the same way by declaring their accessibility, type and name. Similarly we create methods, including constructors, in the same way. We even use the `.` operator in the same way to distinguish between member variables and parameters - `this.name = name`.

We create an use objects of this class just as we do in Java. 

```c#
using System;

class MainClass {
  public static void Main (string[] args) {
    
    Animal animal;

    animal = new Animal("Fred","Dog","Chum");
  }
}
```
## Fields - Member Variables

In C# member variables are called **fields**. Fields are, just as in Java, variables with names, types and a visibility (private, public, protected). 

They can be defined with or without an initial value. 

```c#
private string name = "John Doe";
private string address;
```

### Properties

**Public** access to **fields** is discouraged. Instead access should be given through **properties**.

**Properties** are a way of providing *getters* and *setters* for **fields**.

A property is typically name similarly to the field it is connected to. It usually has the same name but beginning with an uppercase letter. 

```c#
  private string name;

  public string Name
  {
    get { return name; }
    set { name = value; }
  }
```

We can then use the **property** as if it is a **public field**. 

```c#
animal.Name = "Dog";
Console.WriteLine(animal.Name);
```

We can use properties just like we can use getters and setters in Java, in the example below we format data in the get and validate in in the set. 

```c#
public string Name
{
	get 
	{
		return _name.ToUpper();
	}
	set 
	{
		if(!value.Contains(" "))
			throw new Exception("Please specify both first and last name!");
		_name = value; 
	}
}
```

You can create a property that is linked to multiple fields. 

```c#
  public string Name
  {
    private string firstname;
    private string surname;

    get { return firstname + " " + surname; }
    set { 
      string[] words = value.Split(' ');
      firstname = words[0]; 
      surname = words[1]; 
    }
  }
```
## Methods

Methods work just like in Java. There are a couple of features that can be used like optional parameters but they are beyond the scope of this module. This is true of constructors too.






