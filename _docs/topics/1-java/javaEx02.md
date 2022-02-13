---
title: Week 2 Exercises
permalink: /docs/javaEx02/
---

However far you get, please ensure you do Exercise 11 before finishing.

### Exercise 1 - Create A Project

In this module I will often create a repository with some code in it to start an exercise off. Sometimes you will need to create a project from scratch. This exercise will walk you through this process.  

Since we have the `Project Manager For Java` extension installed this is a painless process. (If you don't have it installed then go back to the exercises for week 1 and get VSCode set up with the extensions!).  

1. Open VSCode.
2. Close all files/projects
3. Open the Explorer in the side bar
4. Click on **Create Java Project**
5. Select "No Build Tools"
6. Select the parent folder you want your project folder to be in
7. Enter a name for your project
8. VSCode will do the rest 
9. Open src/App.java in VSCode 
10. Run it and make sure it works

### Exercise 2 - Variables

1. Using your project from Exercise 1 create the following variables and output them
   1. An integer called `daysPerWeek` with a value of 7
   2. An integer called `numberOfWeeks` with a value of 6
   3. An integer called `totalDays` that uses the previous two variables to calculate the number of days in that many weeks.
   4. A true or false variable called `onHoliday` that is set to false. For this you should output a string that says if you are on holiday or not
   5. A real number called `approxPI` that is set to 3.14. Use it to calculate and output the circumference of a circle with a radius of 3. (Use circumference = 2 * PI * radious)
   6. Strings called
      1. `greetingString` with a value of "Hello"
      2. `introductionString` with a value of "My name is Inigo Montoya"
      3. `reminderString` with a value of "You killed my father"
      4. `threatString` with a value of "Prepare to die!"
      5. and then use them to output "Hello, My name is Inigo Montoya, You killed my father, Prepare to die!"
     
### Exercise 3 - Comments

1. Add a block comment to the top of your project explaining that these are the exercises for Week 2, the date they were done (i.e. today) and who made them (i.e. you)
2. Add a comment to the end of each variable created for Exercise 2 the shows the exercise and step number. So on the line you create `daysPerWeek` you should have a comment `// Ex 1.1`
3. Test your code to make sure it still works

### Exercise 4 - Branching - if then else

Extend your previous code

1. Add a new variable to the start of your main called `fingersOnRightHand` and set it to 5. 
2. Modify the code so the String is only output if `fingersOnRightHand` is 6
3. Test your code to make sure it doesn't output the string
4. Change `fingersOnRightHand` to 6, test your code to ensure it now outputs the string
5. Add an `else` to your `if` so that if `fingersOnRightHand` isn't 6 you output the explanation "I am searching for the man who killed my father."

### Exercise 5 - Branching - switch

Extend your previous code

1. Add an integer variable called `month` that will store a number between 1 and 12 inclusive.
2. Use a `switch` to output the name of the month based on the value stored in `month` (1 = January, 2 = February, 3 = March, etc). It should also output "Not a valid month" if the value is less than 1 or greater than 12.

### Exercise 6 - Looping - for loop

Extend your previous code

1. Put your `switch` from Exercise 5 inside a loop. The loop should start at an index of 1 and end at an index of 14.
2. Use the loop index instead of the `month` variable in the `switch` 
3. Test your code, it should output each month in order and then "Not a valid month" once

### Exercise 7 - Looping - while(), do{} while()

Extend your previous code

1. Replicate Exercise 6 using a `while() {}` loop
2. Replicate Exercise 6 using a `do{} while()` loop

### Exercise 8 - Methods

Extend your previous code

1. Move your code for exercise 1 parts 1 to 4 to a method called `countDays`. This method should have no parameters and no return value. It should output the value calculated in step 4. Call this method from `main` and ensure it works correctly
2. Move your code from exercise 1 part 5 to a method called `circumference`. Call this method from `main` and ensure it works correctly
3. Add an integer parameter called `radius` to `circumference` and use it to calculate teh circumference
4. Move your code from Exercise 1.6 and Exercise 4 (the Inigo Montoya strings stuff) to a method called `inigoSpeech`. This method should have a parameter of `numFingers` that it uses instead of `fingersOnRightHand`. It should also return the string rather than outputting it directly
5. Call the `inigoSpeech` method from `main` and store the results in a string. Output the string. Test your code to ensure it works.

### Exercise 9 - isItALeapYear()

Extend your previous code

1. Create a new method call `isItALeapYear`. This methods should take an integer parameter `year` and return true if `year` is a leap year and false if it isn't.

### Exercise 10 - daysBetween()

Extend your previous code

1. Create a new method call `daysBetween`. This methods should take six integer parameters. These are startDay, startMonth, startYear, endDay, endMonth, endYear. Without using any of Java's date functions count the number of days between start and end.  

**Tips**  
1. You can use your `isItALeapYear` method
2. You might want to create other methods like `daysInYear(int year)`, `daysInYearFrom(int day, int month, int year)`, `daysInYearTo(int day, int month, int year)` and `daysInMonth(int month)`

### Exercise 11 - Save to your gitlab

However far you've got, make sure you create a new repository in your gitlab and upload this code to it. You can use lasts weeks exercise to guide you.