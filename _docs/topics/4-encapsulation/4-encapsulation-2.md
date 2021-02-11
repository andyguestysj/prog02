---
title: Public Or Private 
permalink: /docs/4-encapsulation-2/
---

We have this concept of **encapsulation** now and the ability to make *class methods* and *member variables* **private** or **public** but how should you go about using them?  

These aren't hard and fast rules but are good general guidelines


1. Class definitions should be public

Classes should be public.

```java
public class ClassName {

}
```

You want to be able to create classes from anywhere in your code. 

2. Class constructors should be public

```java
public class ClassName {

  public ClassName(){

  }

  public ClassName(String aStringParameter){
    
  }

  public ClassName(int anIntParameter){
    
  }

}
```

If you can create classes anywhere you want to be able to use your constructors anywhere. 

3. Member variables should be private

```java
public class ClassName {
  private String  name;
  private int     count;
}
```

We want to control access to our member variables to ensure they are only ever given valid values.  

4. Use public *getter methods* to return the values of member variables

```java
public class ClassName {
  private String  name;
  private int     count;

  public String getName(){
    return name;
  }

  public int getCount(){
    return count;
  }
}
```

If you need to know the values stored in member variables elsewhere in your code you can use **public** *getter methods* to return those values. Only do this for values you need to see elsewhere and think carefully about whether the value should be brought back from the object or if it should be used there. In the example above if you are only ever getting the name to print it out then perhaps you should make a public class method `printName` that prints out the name instead.  

5. If you **need** to be able to change a value directly from outside the object, create a **public** *setter method*

```java
public class ClassName {
  private String  name;
  private int     count;

  public String getName(){
    return name;
  }

  public setName(String name){
    this.name = name;
  }
}
```
However keep in mind at this point the *member variable* `name` might as well be public. 

Setters are useful if you need to control the values that the member variable can be set to.

```java
public class ClassName {
  private String  name;
  private int     count;

  public String getName(){
    return name;
  }

  public setName(String name){
    if isValidName(name){
      this.name = name;
    }
    else
    {
      System.out.println("Error, invalid name, name not changed");
    }
  }

  private boolean isValidName(String name){
    //  Does some validation on the name and returns true or false
  }
}
```

6. Create **public** interface methods

```java
public class ClassName {
  private String  name;
  private int     count;

  public void marries(ClassName other){
    // does whatever needs doing when two people get married!
  }

}
```

If there is some functionality you need to be able to trigger from outside the object then make a public method to do that.

7. Create **private** internal methods
```java
public class ClassName {
  private String  name;
  private int     count;

  public void marries(ClassName other){
    // does whatever needs doing when two people get married!
    this.connect(other);
    other.connect(this);
  }

  public void partners(ClassName other){
    // does whatever needs doing when two people get married!
    this.connect(other);
    other.connect(this);
  }

  public void hasChild(ClassName other){
    // does whatever needs doing when two people get partnered!
    this.connect(other);
    other.connect(this);
  }


  private void connect(ClassName other) {
    // do whatever connection needs doing when someone has a child
  }

}
```

If a method is essential to the functioning of the object but should only ever be triggered by the object you should create a private method to do it.  

Another example is the `isValidName()` method from above.


```java
public class ClassName {
  private String  name;
  private int     count;

  public String getName(){
    return name;
  }

  public setName(String name){
    if isValidName(name){
      this.name = name;
    }
    else
    {
      System.out.println("Error, invalid name, name not changed");
    }
  }

  private boolean isValidName(String name){
    //  Does some validation on the name and returns true or false
  }
}
```




## Bring it all together

Below is an example of all these in one class. Thinking about it this way also gives us a nice way to structure our class. While not essential, a consistent structure across all your classes will make it easier to work with them.  


```java
import java.util.ArrayList;

public class Person {

  // ****************************************************
  // private member variables
  private String  name;
  private boolean married;
  private boolean civilPartner;
  private int     childCount;
  private Person  partner;
  private ArrayList<Person> children = new ArrayList<Person>();

  // ****************************************************
  // public member variable


  // ****************************************************
  // Constructors

  public Person(String name){
    if isValidName(name) {
      this.name = name
    }
    else
    {
      this.name = "J Doe";
      married = false;
      civilPartner = false;
      childCount = 0;
    }
  }

  // ****************************************************
  // getters

  public String getName() {return name;}
  public boolean isMarried() {return married;}

  // ****************************************************
  // setters

  public setName(String name){
    if isValidName(name){
      this.name = name;
    }
    else
    {
      System.out.println("Error, invalid name, name not changed");
    }
  }

  
  // ****************************************************
  // public interface methods

  public void marries(Person other){
    // does whatever needs doing when two people get married!
    married = true;
    partner = other;

  }

  public void partners(Person other){
    // does whatever needs doing when two people get partnered!
    civilPartner = true;
    partner = other;
  }

  public void hasChild(Person other){
    // does whatever needs doing when someone has a child
    childCount++;
    children.add(other);
  }



  // ****************************************************
  // private internal methods
  
  private boolean isValidName(String name){
    //  Does some validation on the name and returns true or false
  }

}
```