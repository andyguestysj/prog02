---
title: Methods
permalink: /docs/java11/
---

### Methods

In Java functions are known as methods.  

They are usually part of classes. We'll come back to this when we look are OOP but for now we will focus on methods that are part of the `App` class and are  used directly in `main()` (or in another method called from `main()`).  

These methods have a specific format that must be used and they must be place in the correct place in your code.

#### Placement

These methods must be place within the `App` class.  

```java
public class App { // they must be placed after this curly bracket

    // they can be placed here

    public static void main(String[] args) throws Exception {
        System.out.println("Hello, World!");        
    }

    // but we generally prefer to place them here
    // that way the main() method stays at the top of the file
    // which makes working out what is going on easier

} // and before this curly bracket
```

#### Format

Methods must be formatted correctly. The format is as follows :-

`accessibility` `static` `return-type` methodName(`parameters`) {

  // your code here

  // `return` `return-value`; if `return-type` is anything except `void`
}

* *accessibilty* detemines where the method can be called from, it can be `public`, `private` or `protected`. Until we start working with classes use `public`  
* *`static`* is a keyword that allows us to use a method that belongs to an object even if we haven't created that object. We don't use it very often, mostly just for methods in `App`. We'll look at this later but for the time being just use the `static` for all methods in `App`
* `return-type` - Java is less flexible than Python. In Java you have to specify if a method will return a value and what type of value it will be when you create the method.  
  * If you do not intend to return a value use `void` for *return-type*
  * If you do intend to return a value use the variable type (or Class name for an object) for *return-type*
* *methodName* should be as informative as possible without being too long. It shouldn't be a reserved keyword.
* *parameters* are a list of variables you want to recieve as parameters. You **must give both type and a name** eg `int age, String name`. Multiple parameters should be separated by commas. If you don't want to pass in a value the brackets can be left empty
* if you wish to return a value from the method the last line of code in the method should be `return` followed by a value, variable or object. You can also place `return` elsewhere in the method to exit the method early. You must ensure it is impossible to step through the method without hitting a return eventually. You **must** include return unless the *return-type* is void.  

You call the method using its name, putting the parameters in round brackets.

#### Examples

**No Parameters, No Return Type**

```java
public class App {
    public static void main(String[] args) throws Exception {
        System.out.println("Hello, World!");
        boo();
    }

    public static void boo(){
      System.out.println("Boo!");
    }
}
```

**One Parameter, No Return Type**

```java
public class App {
    public static void main(String[] args) throws Exception {
        System.out.println("Hello, World!");
        boo("Andy");
    }

    public static void boo(String name){
      System.out.println("Boo!" + " I scared you " + name);
    }
}
```

**Two Parameters, No Return Type**

```java
public class App {
    public static void main(String[] args) throws Exception {
        System.out.println("Hello, World!");
        boo("Andy", 4);
    }

    public static void boo(String name, int numberOfTimes){
      System.out.println("Boo!" + " I scared you " + numberOfTimes + " times " + name);
    }
}
```

**Two Parameters, Return A String**

```java
public class App {
    public static void main(String[] args) throws Exception {
        System.out.println("Hello, World!");
        System.out.println(boo("Andy", 4));
    }

    public static String boo(String name, int numberOfTimes){
      String returnValue = "Boo!" + " I scared you " + numberOfTimes + " times " + name;
      return returnValue;
    }
}
```

**Two Parameters, Return A To A String Variable**

```java
public class App {
    public static void main(String[] args) throws Exception {
        System.out.println("Hello, World!");
        String result = boo("Andy", 4);
        System.out.println("Returned string is ");
        System.out.println(result);
    }

    public static String boo(String name, int numberOfTimes){
      String returnValue = "Boo!" + " I scared you " + numberOfTimes + " times " + name;
      return returnValue;
    }
}
```

**Two Parameters, Return A To A String Variable, Multiple Paths/Returns**

```java
public class App {
    public static void main(String[] args) throws Exception {
        System.out.println("Hello, World!");
        String result = boo("Andy", 4);
        System.out.println("Returned string is ");
        System.out.println(result);
    }

    public static String boo(String name, int numberOfTimes){      
      if (numberOfTimes==0)
      {
        return "";
      }
      String returnValue = "Boo!" + " I scared you " + numberOfTimes + " times " + name;
      return returnValue;
    }
}
```

**Multiple Methods**

```java
public class App {
    public static void main(String[] args) throws Exception {
        System.out.println("Hello, World!");
        String result = boo("Andy", 0);
        System.out.println("Returned string is ");
        System.out.println(result);
    }

    public static String boo(String name, int numberOfTimes){      
      if (numberOfTimes==0)
      {
        whyNoScare();
        return "";
      }
      String returnValue = "Boo!" + " I scared you " + numberOfTimes + " times " + name;
      return returnValue;
    }

    public static void whyNoScare(){
      System.out.println("Why no scare?");
    }
}
```