---
title: Introduction
permalink: /docs/java02/
---

* Contents
  * What is Java?
  * Why Java?
  * Java vs Python
  * How Java Works
  * The Differences
  * Recommended Sources

### What Is Java?

Java is and Objected Oriented (we'll talk about this bit soon) Programming Language. Work started on the language that would eventually become Java in 1990 but it was fully realeased until 1995 after Sun bought it, developed it for the internet and renamed it Java.  

Java is probably the most widely used programming language today. It is available in 32 and 64 bit versions, for Windows, Linux and Mac platforms.  

Java is available directly from Oracle in the proprietary version called Oracle JDK (Java Development Kit). It is also available freely in the open source version OpenJDK which is supported by Oracle and the Java community.  

The machines in our labs all have a JDK installed on them. If you are working from home you may need to install a JDK. You can get one from [adoptopenjdk.net](adoptopenjdk.net).  

### Why Java?

Well, as already mentioned, Java is probably the most widely used programming language today. It is ideal for writing code for the internet.  

Java is an Object Oriented Language (we will get to this I promise!) and learning about Object Orientation is essential for modern software developers.  

### Java vs Python

If Java is so important why did we start with Python?  

Python is easier to learn. You can learn Python without messing around with all this OOP stuff.  

Python is an interpretted language, meaning you can more easily see the effects of your code.  

```

An *interpretted* language is a script that is run line by line as you execute it. The computer reads each line of code, converts it to instructions that it can run and runs them.  

A *compiled* language is compiled before it is run so it is converted to instructions the computer can execute. You do not "run" the code, instead you run the pre-compiled executable.  

Compiled language programmes generally run much faster because the instructions were converted in advance. Interpretted language programmes are generally slower but easier to write and change.  

**Python** is an interpretted language. **C++** is a compiled language. 

**Java** is an odd case. It is compiled to Java app code but that code then runs as interpretted code on a *Java Virtual Machine*. 

```

### How Java Works

I've just mentioned something called a **Java Virtual Machine (JVM)** - what is it and why does it matter?  

The Java Virtual Machine is central to the widespread use of Java. 

With compiled languages like C++ programs have to be written and compiled for specific types of computer operating systems and versions (Windows, Mac, Linux). They need to be compiled differently for different chipsets, sometimes even for different hardware and drivers. This is because when code is compiled it is converted to machine code that is specific to the machine it will run on.  

Programs in interpretted language do not have this problem. The program code is like a script which each computer compiles, at run time, to machine code that will run locally.  

As previously mentioned, Java is both compiled and interpretted, how does this work?  

Java code gets compiled down to Java byte code (.class files). The compilation to byte code optimises the original program so it is faster and easier to interpret (though still not as fast as truly compiled code). The Java Virtual Machine knows how to interpret the byte code for the machine it is running on. There are different JVMs for different computers.  

![Java Virtual Machine](https://ysjprog02.netlify.app/assets/img/java-virtual-machine.png)  

This means that you can write a Java application once and be confident it will run on any machine that has its own JVM (or at least as confident as you can be in computing..).  

### The Differences

There are many differences between Java and Python when you start digging in to the more interesting parts of the languages (like Object Orientation), but the languages are very similar for the most part.  

When you look at a Java program you should be able to understand a lot of it. Functions look like functions, variables look like variables, loops and if statements should be familiar enough to follow. We'll talk about the differences as we look at different aspects of Java but there are two worh pointing out now.  

In Python you indicate *scope* by indenting code. All the code that makes up a function are indented one tab space from the first line of the function. In a loop the code that gets repeated is indented from the start of the loop. In Java we indicate scope using {} "curly brackets".  

In Python each line of code ends when we press return. In Java each line of code ends with a semi-colon **;** (mostly anyway). In Java we can put multiple instructions on a single line of code providing we put a semi-colon between them. We generally don't because it makes the code harder to read but we can.  

<div class="row">
    <div class="col-md-6">
    <B>Python</B>
            <pre><code class="language-python">for x in range(2, 6):
  print(x)
</code></pre>
    </div>
    <div class="col-md-6">
    <B>Java</B>
      <pre><code class="language-java">for (int x=2; x<6; x++)
{
  System.out.println(x);
}
</code></pre>
    </div>
</div>

**NB** We do generally still indents scope in Java but this is for readability reasons, not because we are required to. We could write our Java version as shown below.  

<div class="row">
    <div class="col-md-6">
    <B>Java</B>
      <pre><code class="language-java">for (int x=2; x<6; x++){System.out.println(x);}
</code></pre>
    </div>
    <div class="col-md-6">
    <B>Java</B>
      <pre><code class="language-java">for (int x=2; x<6; x++)
     {
                 System.out.println(x);
}
</code></pre>
    </div>
</div>

### Recommended Sources

#### Books 

There are number of good books on Java. I'm recommending two that are at opposite ends of the spectrum. **You do not need to buy either of them**, these are simply my recommendations if you want a text book.  

The first is **"Java In Easy Steps"** by Mike McGrath (7th Edition, 2019, In Easy Steps Ltd). This book is a very good introduction to the basics of Java. It is clearly laid out and easy to follow. However it barely even mentions Object Oriented Programming. If you want a nice little book to help you switch from Python to Java this book is my recommendation. As an added bonus you can get it for less than £10 on Amazon.  

The second book is **"Thinking In Java** by Bruce Eckel (4th Edition, 2006, Pearson). This is a beast of a book which, despite being over fifteen years old, covers everything you could ever want to know about Java and Object Oriented Java. This is a big book that will give you back problems if you carry it around and will punch a £50 hole in your wallet. It is available in the library thankfully.  

I also like the **Head First** books. *Head First Java* and *Head First Object-Oriented Analysis and Design* are both good and useful for this module.  

#### Websites 

There are number of good websites out there with Java reference and tutorial material.  

This list is a starting point and by no means exhaustive.  

* [https://www.tutorialspoint.com/java/index.htm](https://www.tutorialspoint.com/java/index.htm)
* [https://www.programiz.com/java-programming](https://www.programiz.com/java-programming)
* [https://www.w3schools.com/java/default.asp](https://www.w3schools.com/java/default.asp)
  
#### Youtube

There are many good Youtube Java channels. I'll link the good general ones here and ones with specific content on the pages about that content.  
