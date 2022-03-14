---
title: Assessment Exercise 2
permalink: /docs/assess-ex-2/  
---

[Video Brief](https://web.microsoftstream.com/video/6a938db7-9e21-4c40-ae11-0a87b1902167)  

## Shapes

Clone yourself a copy of **javaAssessEx1** from [https://git.ysjcs.net:8888/a.guest/javaassessex2.git](https://git.ysjcs.net:8888/a.guest/javaassessex2.git). There is an **Instructions.md** file that covers the exercise. (The instructions are repeated below).

## 1 Skills
This exercise should help you with:  

1. Member variables and member methods.
2. Unit testing.
3. Inheritance
4. Encapsulation
5. Abstraction

## 2 Shapes

The code in this project contains an abstract class `Shape` used to define the methods any shape class must possess (see the Inheritance section of the module website).  

I've created a `Triangle` class as an example shape for you.

## 3 Unit Testing

This project is set up with unit testing enabled. Unit testing is a development technique where tests can be created in advance and used to help ensure the code is corrent when it is written. See Assessment Exercise 1 for more details on Unit Testing.

## 4 Task

You need to create to classes which inherit (`extend`) from `Shape`. These are

* `Square`
* `Rectangle`

### `Square`

The `Square` class should store the information and methods related to a square shape.  

1. `size` should be used to represent the width and height of the square. 
2. `Square` should have two constructors. The first should have no parameters and set the size equal to 3. The second should take a single integer parameter and use it to set the size.  
3. You should be able to use the `getSize()` and `setSize()` methods properly for the `Square`.
4. You should correctly implement the `area()` and `circumference()` methods for `Square`.
5. You should implement a `draw()` method that will output an ascii square of the correct size. 
6. All the Square unit tests must be passed.

### `Rectangle`

The `Rectangle` class should store the information and methods related to a Rectangle shape.  

1. Instead of using `size` you should use `width` and `hieght` to represent the width and height of the rectangle. 
2. `Rectangle` should have two constructors. The first should have no parameters and set the `width` equal to 3 and the `height` equal to 4. The second should take a two integer parameter and uses them to set the `width` and `height` (in that order).  
3. You should be able to use the `getWidth()` and `setWidth()` methods properly for the `Rectangle`.
4. You should be able to use the `getHeight()` and `setHeight()` methods properly for the `Rectangle`.
5. You should correctly implement the `area()` and `circumference()` methods for `Rectangle`.
6. You should implement a `draw()` method that will output an ascii rectangle of the correct size. 
7. All the Rectangle unit tests must be passed.

## 5 Marking

25 marks are available for this exercise. This breaks down as follows.

### `Square` (10 Marks)
* constructors - 2 marks
* setSize(), getSize()  - 2 marks
* area(), circumference() - 2 marks
* draw() - 2 marks
* Pass all Square Unit Tests - 2 marks

### `Rectangle` (15 Marks)
* constructors - 3 marks
* setWidth(), getWidth(), setHeight(), getHeight()  - 3 marks
* area(), circumference() - 3 marks
* draw() - 3 marks
* Pass all Square Unit Tests - 3 marks

## 6 Submission

Your project should be uploaded to your gitlab account and you should submit a link to the gitlab project, alongside the rest of the assessment, through moodle, by 12noon 16/05/22.  