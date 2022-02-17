---
title: Java Arrays
permalink: /docs/java12/
---

### Creating An Array

You can create filled arrays easily.  

```java
int[] numbersArray = { 1, 2, 3 };
float[] floatArray = { 5.6, 2.7, 9.1 };
String[] names = {"Andy", "Bob", "Chuck"};
```

Alternatively you might want to create an empty array of a specific size and fill it later.  

```java
int[] anotherNumbersArray = new int[3];
```

This creates an array of integers with three elements. Each element is initialised to `0`.  

The array can then be filled using the index of the position you wish to fill.  

```java
int[] anotherNumbersArray = new int[3];

anotherNumbersArray[0] = 5;
```

### Looping Through Arrays

We can loop through an array just as you'd expect.  

```java
int[] anotherNumbersArray = new int[3];

for (int x = 0; x < anotherNumbersArray.length; x++)
{
  anotherNumbersArray[x] = x;
  System.out.println(anotherNumbersArray[x]);
}
```

Java also gives us a `for each` loop we can use.  

```java
for (int num : anotherNumbersArray){
  System.out.println(num);
}
```

This uses the format  

for(`type` `variableName` : `arrayName`){  
}

### Multidimensional Arrays

We can have two-dimensional arrays  

```java
int[][] twoDArray = new int [50][10];

twoDArray[0][5] = 7;

for (int loop1=0; loop1 < 50; loop1++) 
{
  for (int loop2=0; loop2 < 10; loop2++) 
  {
    twoDArray[loop1][loop2] = loop1 * loop2;
  }
}
```

The `for each` with multi-dimensional arrays is a little tricky, to use it properly you need to understand how a multi-dimensional array actually works.  

In the example above `int[][] twoDArray = new int [50][10];` creates a two dimensional array. As far as Java is concerned this is the same as a one dimensional array of 50 items where each item is an array of 10 items. As such the `for each` works like this.  

```java
import java.util.Arrays;

int[][] twoDArray = new int [50][10];

for (int[] littleArray : twoDArray)
{
  System.out.println(Arrays.toString(littleArray));
}
```

Will output fifty lines, each line containing ten items.  

```console
[0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
[50, 51, 52, 53, 54, 55, 56, 57, 58, 59]
[100, 101, 102, 103, 104, 105, 106, 107, 108, 109]
[150, 151, 152, 153, 154, 155, 156, 157, 158, 159]
[200, 201, 202, 203, 204, 205, 206, 207, 208, 209]
[250, 251, 252, 253, 254, 255, 256, 257, 258, 259]
[300, 301, 302, 303, 304, 305, 306, 307, 308, 309]
[350, 351, 352, 353, 354, 355, 356, 357, 358, 359]
etc
```

To access each individual integer you still need two loops.  

```java
int[][] twoDArray = new int [50][10];

for (int[] littleArray : twoDArray)
{
  for (int aNumber : littleArray)
  {
    System.out.println(aNumber);
  }  
}
```

### Even More Dimensions Are Possible

```java
int[][] threeDArray = new int [100][50][10];

for (int[][] twoDArray : threeDArray)
{
  for (int[] littleArray : twoDArray)
  {
    for (int aNumber : littleArray)
    {
      System.out.println(aNumber);
    }  
  }
}
```

