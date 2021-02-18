---
title: Abstract Methods
permalink: /docs/5-inheritance-4/
---

You can insist that subclasses have particular methods in them, but not say what they should do.

```java
public class Shape {
  abstract public double area();
}
```

The code above says that `Shape` must have a method called `area()` with no parameters that returns a double but doesn't provide a method called `area()`. So how do we create `Shape` objects if they must have an `area()`?  

Well the simple answer is we can't. You can't create an object of any class that has an **abstract** method. The class *only exists to define how its children **must** be*.  

The above example is actually wrong. If **any** class method is marked as abstract the *entire class **must** be abstract*.

```java
public abstract class Shape {
  abstract public double area();
}
```

Why do we create **abstract** classes? We create them to define how children classes must behave. It also gives us a way to make collections of child objects of shape (more on this on the next page).  

So if we have a `Shape` class like so  

```java
public abstract class Shape {
  abstract public double area();
  abstract public double circumference();
}
```

and we want to create a `Square` child class, we know we have to implement those two methods in `Square`.

```java
public class Square extends Shape {

  double width;


  public Square(double width){
    this.width = width;
  }

  public double area(){
    return width * width;
  }

  public double circumference(){
    return width + width + width + width;
  }
}
```

We are free to add any other variables and methods we like but we must include the **abstract methods** from `Shape`.

An **abstract class** can define member variables as usual. It can even have constructors. The constructors cannot be used to create objects of the abstract class but they can be used by its children. Our children classes can use those variables and methods.  

```java
public abstract class Shape {
  public int red;
  public int green;
  public int blue;

  public Shape(int red, int green, int blue){
    this.red = red;
    this.green = green; 
    this. blue = blue;
  }

  public void setColour(int red, int green, int blue){
    this.red = red;
    this.green = green; 
    this. blue = blue;
  }

  abstract public double area();
  abstract public double circumference();
}

public class Square extends Shape {

  double width;
  

  public Square(double width, int red, int green, int blue){
    super(red, green, blue);
    this.width = width;
  }

  public double area(){
    return width * width;
  }

  public double circumference(){
    return width + width + width + width;
  }
}

void main(){
  Square shape1 = new Square(5,255,0,0);
  shape1.setColour(0,255,0);
}
```
