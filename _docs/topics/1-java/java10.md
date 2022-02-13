---
title: Loops
permalink: /docs/java10/
---

### Basic For Loop

The basic, simplest form of the loop takes this form

```java
for (initialiser; test-expression; updater)
{
  // code to be repeated
}
```

* *initialiser* - this gets done before the loop is entered for the first time. It typically defines and initialised a counter. Usually this is in the form `int loopCounter = 0`. You can use any variable name you haven't previously used and you can start at any value you wish. It is even possible to put a method call in here (though that is unusual and would be confusing).
* *test-expression* - is any code you like which will result in a `true` or `false` when evaluated. If it evaluates to `true` the loop is entered, if it evaluates to `false` the looping ends. Typically we test a variable set in the *initialiser* to see if it hasn't reached a specified limit. `loopCounter < 10` for example. Again it is possible (though unusual) to put a function in here. You could use `dataComplete()` so long as that method returns `true` or `false`. NB be very careful doing this - be **certain** that it will return a `false` within a reasonable time or you will be stuck in an infinite loop!
* *updater* - this is carried out after you get to the end of the loop code and before you test to see if you enter it again. Typically this changes the variable set in the *initialiser* and tested in the *test-expression*. This is typically something like `loopCounter++` or `loopCounter = loopCounter +3`. Again, with the same warnings, this could be a method call.

**Example 1**

```java
for (int loopCounter = 0; loopCounter < 10; loopCounter++)
{
  System.out.println(loopCounter);
}
```

Outputs the numbers 0 to 9 on separate lines.  

**Example 2**

```java
for (int loopCounter = 10; loopCounter >= 0; loopCounter = loopCounter - 2)
{
  System.out.print(loopCounter);
}
```

Outputs the numbers 10 8 6 4 2 0.  

**Example 3**

```java
import java.time.LocalTime; // import the LocalDate class
import java.time.Duration;
import java.time.temporal.ChronoUnit;

class Main {
  public static void main(String[] args) {

    LocalTime start = LocalTime.now();
    for (
      LocalTime timePlus5 = LocalTime.now().plus(Duration.of(5, ChronoUnit.SECONDS));
      LocalTime.now().compareTo(timePlus5)<0;
      // nothing done in updater
      )
    {
      System.out.print(".");
    }
    System.out.println();
    System.out.println(start + " -> " + LocalTime.now());
  }
}
```

`for` has been split over multiple lines for "clarity", remember Java is happy for us to do this. 
* *initialiser* stores the time five seconds after now in `timePlus5`.
* *test-expression* returns true if the current time is less than `timePlus5` meaning that the time is before `timePlus5`.
* *updater* doesn't do anything, it doesn't need to, the system clock is automatically updating itself.

In practice we'd do something like this with a `while` loop.  

Ouputs dots for five seconds then something like `11:50:45.616941 -> 11:50:55.618091`.  

### While Loops

As an alternative we have two types of `while` loops. The difference between the two is when we test to see if we enter the loop.  

<div class="row">
    <div class="col-md-6">
    <B>while(){}</B>
            <pre><code class="language-java">while(test-expression)
{
  // do stuff
}
</code></pre>
    </div>
    <div class="col-md-6">
    <B>do{}while();</B>
      <pre><code class="language-java">do
{
  // do stuff
} while(test-expression);
</code></pre>
    </div>
</div>

**Examples**

<div class="row">
    <div class="col-md-6">
    <B>while(){}</B>
            <pre><code class="language-java">int x = 0;
while(x<10)
{
  System.out.println(x);
}
</code></pre>
    </div>
    <div class="col-md-6">
    <B>do{}while();</B>
      <pre><code class="language-java">int x = 0;
do
{
  System.out.println(x);
} while(x<10);
</code></pre>
    </div>
</div>

**while(){}** carries out a test before entering the loop. It will test everytime, including before entering the loop the first time. We use this if we may not need to run the loop code at all.  

```java
import java.util.Scanner;

Scanner scan = new Scanner(System.in);

System.out.print("Enter an even integer: ");
int num = scan.nextInt();

while(num % 2 == 1)
{
  System.out.print("You must enter an even integer: ");
  int num = scan.nextInt();
}

System.out.print("Even integer was : " + num);

scan.close();
```

Don't worry about the Scanner, it simply reads in input from the keyboard.  

This code asks for an integer to be entered. The `while` loop first checks to see if the number is odd. If it is odd the loop is entered and the user is prompted to enter an even number. They will stay in this loop until they enter an even number. If the first number entered was even the application will *never* enter the loop.  

**do{} while();** does not carry out the test until it has been through the loop. It **will always run through the loop at least once**.  

Please note the **`;`** after the `test-expression` in the `do{} while();` loop.

```java
import java.util.Scanner;

Scanner scan = new Scanner(System.in);
int num;


do
{
  System.out.print("Enter an even integer: ");
  num = scan.nextInt();
}while(num % 2 == 1);

System.out.print("Even integer was : " + num);

scan.close();
```

Functionally, this does the same as the `while()` loop above.  

`do{} while()` can be tidier if you can use it, but sometimes we know we may never need to enter the loop so a `while()` can be a better option.  

**Example 1 Use A While()**

Imagine that we have a situation where we need to `doSomeWork()` and then `doSomeMoreWork()`. There needs to be at least a five second gap between starting `doSomeWork()` and starting `doSomeMoreWork()` for some reason. `doSomeWork()` might take more than five seconds to run, if it does that's fine we can immeadiately run `doSomeMoreWork()`. On the other hand `doSomeWork()` might run in one second, in which case we have to hang around and wait till four more seconds pass before we `doSomeMoreWork()`. We could do that like this.  

```java
import java.time.LocalTime; // import the LocalDate class
import java.time.Duration;
import java.time.temporal.ChronoUnit;

LocalTime endTime = LocalTime.now().plus(Duration.of(5, ChronoUnit.SECONDS));

doSomeWork();

while (LocalTime.now().compareTo(endTime)<0))
{
  // do nothing we are just gonna hang around till the time has passed..
}

doSomeMoreWork();

```

>In practice this is a terrible approach has a couple of different ways to make the application `sleep` for a specified time before continuing. If you ever need to do something like this store the time before calling `doSomeWork()`, calculate how much time has passed once `doSomeWork()` has completed, subtract that from the time you need to wait till and `sleep` that long.

**Example 2 do{} while()**

In the game you are collecting playing cards, trying to get as close as possible to 21 without going over. If you go over 21 you go bust and lose. We might code this something like. Face cards have a value of ten, aces can be one or ten but in this example we will make them one for simplicity.  

```java
import java.util.concurrent.ThreadLocalRandom;
import java.util.Scanner;



public static int getCard(){   
  int c = ThreadLocalRandom.current().nextInt(1,14); // generates a random number from 1 to 13 inclusively.
  if (c>10) { c = 10; }; // convert face card numbers to 10
  System.out.println("Card adds " + c + " to your total");
  return c;
}

int total = 0;
int count = 0;
int num;
boolean keepPlaying = true;

Scanner scan = new Scanner(System.in);

do { 
  System.out.println("Total is " + total);
  if (count<2){ // always get dealt two cards
    total += getCard();
    count++;
  }
  else
  { // once you have two or more cards it is your choice to get more
    System.out.print("Enter 1 to draw another card, any other number to stop.");
    num = scan.nextInt();
    if (num==1){
      total += getCard();
      count++;
    }
    else
    {
      keepPlaying = false;
    }
  } 
} while (keepPlaying && (total<=21));

System.out.println("Your total is " + total);
if (total>21){
  System.out.println("Your went bust");
}
```

Here we always want to draw the first two cards. Then we want to offer the player the chance to stop or draw more. We will keep looping until the player chooses to stop or goes bust. (Technically we keep looping while the player chooses to keep playing **and** they haven't gone bust).

This code is available [here](https://github.com/andyguestysj/javaBlackjack.git).  

### `break` and `continue`

We have two keywords we can use that manipulate how loops work.  

**`break`** will force the code to completely leave the loop regardless of the `test-expression`.

**`continue`** will exit the *current go round the loop* but will continue to the next go round.

```java
for (int i = 0; i < 10; i++){
  if (i==2){
    continue; // exit this trip round the loop if i is 2
  }
  if (i==5){
    break;
  }
  System.out.println(i);
}
```

will produce the output 

```console
0
1
3
4
```

1. On the first trip round the loop `i` is `0` so both `if` tests fail so the code moves on to the `System.out.println(i)` and outputs `0`.  
2. On the second trip round the loop `i` is `1` so both `if` tests fail so the code moves on to the `System.out.println(i)` and outputs `1`.  
3. On the third trip round `i` is `2` so the first `if` test passes, the code hits the `continue` instruction and exits this trip round the loop and starts the next one.  
4. On the fourth trip round the loop `i` is `3` so both `if` tests fail so the code moves on to the `System.out.println(i)` and outputs `3`.  
5. On the fifth trip round the loop `i` is `4` so both `if` tests fail so the code moves on to the `System.out.println(i)` and outputs `4`.  
6. On the sixth trip round `i` is `5` so the first `if` test fails but the second passes, the code hits the `break` instruction and exits the loop completely.  



