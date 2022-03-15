---
title: Assessment Exercise 1
permalink: /docs/assess-ex-1/  
---

[Video Brief](https://web.microsoftstream.com/video/6054b7ba-362e-4ea8-ad34-f43000a6b16f)  

## Complex Numbers 

Clone yourself a copy of **javaAssessEx1** from [https://git.ysjcs.net:8888/a.guest/javaassessex1.git](https://git.ysjcs.net:8888/a.guest/javaassessex1.git). There is an **Instructions.md** file that covers the exercise. (The instructions are repeated below).

## 1 Skills
This exercise should help you with:  

1. Member variables and member methods.
2. Unit testing.
3. Creation of a class to a specification without necessarily understanding the details.

## 2 Background
A complex number is one that has two parts: **real** and **imaginary**. They are written (by engineers  at least) like this  

* 4.1 + j9.9
* 0.5 + j3.2
 
Or in general

* a + *j*b

There are a few operations defined for complex numbers. If a complex number has a real part called **a** and an imaginary part called **b** we have    

* **magnitude** = square root of (**a** squared + **b** squared) (using `Math.sqrt()` in java)
*	**argument** = tan−1(b/a) (using `Math.atan2(b,a)` in Java)
 
**Addition**  

To add two complex numbers we add the real parts to give the new real part and the imaginary parts to give the new imaginary part.  

CN1 = a +*j*b  
CN2 = c +*j*d   
CN1 + CN2 = (a+c) + *j*(b+d)  

## 3 Unit Testing

This project is set up with unit testing enabled. Unit testing is a development technique where tests can be created in advance and used to help ensure the code is corrent when it is written.  

Click on the `Testing` icon in the left hand tool bar. It looks like a flask. Open up `javaAssessEx1`, then `<Default Package>`, then `AppTest`. You should now see a list of tests.

* testConstructor()
* testMagnitude()
* testArgument()
* testAdd()
* testToString()

You can right click on `AppTest` and choose `Run Test` to run all the tests or you can run each test individually by right clicking on each one and choosing `Run Test`.

## 4 Task

You need to complete the following methods.  

* public double magnitude()
* public double argument()
* public String toString()
* public Complex add(Complex complexNum)

Looking at the tests in AppTest.java might help you see how these methods will be used. Section 2 above will show you how to calculate the magnitude and argument and how to add two complex numbers together.  

`toString()` should return a string in the format `a + jb` where `a` is the real component and `b` is the imaginary component. Note the rules below should be followed.  

|Real Part|Imaginary Part|String|
|---|---|---|
|`2.6`|`5.2`|`2.6 + j5.6`|
|`2.6`|`0`|`2.6`|
|`0`|`5.2`|`j5.2`|
|`2.6`|`-9.8`|`2.6 - j9.8`|

If the real or imaginary part is 0 it should not be shown. If the imaginary part is negative the negative symbol should be before the j not the number (i.e. `4.3 - j2.1` not `4.3 + j-2.1`).

If you have completed the methods correctly all the unit tests will pass. Please note that hardcoding the methods to return the correct answers for the tests carried out in the unit tests you will get zero marks.  

## 5 Marking

25 marks are available for this exercise. This breaks down as follows.

* public double magnitude() - 5 marks
* public double argument() - 5 marks
* public String toString() - 10 marks
* public Complex add(Complex complexNum) - 5 marks

## 6 Submission

Your project should be uploaded to your gitlab account and you should submit a link to the gitlab project, alongside the rest of the assessment, through moodle, by 12noon 16/05/22.  