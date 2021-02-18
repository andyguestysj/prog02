---
title: Collections
permalink: /docs/5-inheritance-5/
---

We can easily make collections of different child classes providing we stick to a few basic rules.  

Lets start with a new abstract `Shape` class.

```java
public abstract class Shape {
  public double positionX;
  public double positionY;
  

  public Shape(double posX, double posY){
    this.positionX = posX;
    this.positionY = posY;
  }

  abstract public double draw();
  
  public double move(double x, double y){
    this.positionX = posX;
    this.positionY = posY;
  }
}
```

We'll add some shapes.  


```java
public class Square extends Shape {
  public double positionX;
  public double positionY;
  public double width;
  

  public Square(double posX, double posY, double width){
    super(posX, posY);
    this.width = width;
  }

  public double draw(){

  }
}

public class Rectangle extends Shape {
  public double positionX;
  public double positionY;
  public double width;
  public double height;
  

  public Rectangle(double posX, double posY, double width, double height){
    super(posX, posY);
    this.width = width;
    this.height = height;
  }

  public double draw(){
    
  }
}

public class Circle extends Shape {
  public double positionX;
  public double positionY;
  public double radius;
  

  public Square(double posX, double posY, double radius){
    super(posX, posY);
    this.radius = radius;
  }

  public double draw(){
    
  }
}
```

We now have three different classes that all inherit from `Shape`.  

Remember the *ArrayList*?

We can use an ArrayList to store **variables**, providing they are all of the same **type**.   

```java
import java.util.ArrayList; // import the ArrayList class

public class Main {
  public static void main(String[] args) {
    ArrayList<String> cars = new ArrayList<String>();
    cars.add("Volvo");
    cars.add("BMW");
    cars.add("Ford");
    cars.add("Mazda");
    System.out.println(cars);
  }
}
```

We can use an ArrayList to store **objects**, providing they are all of the same **class**.   

```java
import java.util.ArrayList; // import the ArrayList class

public class Main {
  public static void main(String[] args) {
    ArrayList<Square> squares = new ArrayList<Square>();
    cars.add(new Square(5,6,7));
    cars.add(new Square(1,3,2));
    cars.add(new Square(17,2,13));
    System.out.println(squares);
  }
}
```

We can use the **for** loop to access each object in the ArrayList.  

```java
import java.util.ArrayList; // import the ArrayList class

public class Main {
  public static void main(String[] args) {
    ArrayList<Square> squares = new ArrayList<Square>();
    cars.add(new Square(5,6,7));
    cars.add(new Square(1,3,2));
    cars.add(new Square(17,2,13));
    

    // Call each squares draw() method
    for (Square s : squares) {
      s.draw(); 
    }
  }
}
```

The only limitation is that all the objects have to be the same type. Or do they? We can exploit a feature of inheritance here. Each of our shape classes `Square`, `Rectangle` and `Circle` are their own classes. But they are also *all `Shape`s*. We can create an ArrayList of `Shape` and store any of the shape objects in it.  

```java
import java.util.ArrayList; // import the ArrayList class

public class Main {
  public static void main(String[] args) {
    ArrayList<Square> squares = new ArrayList<Square>();
    cars.add(new Square(5,6,7));
    cars.add(new Rectangle(1,3,2,5));
    cars.add(new Circle(17,2,13));
    

    // Call each squares shape's method
    for (Square s : squares) {
      s.draw(); 
    }
  }
}
```

We have to be careful. We can use whichever constructors we like but we can only use the methods that are declared in `Shape`, abstract or normal.  
