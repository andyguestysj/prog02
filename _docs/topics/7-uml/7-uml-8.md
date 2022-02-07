---
title: Exercises
permalink: /docs/7-uml-8/
---

You should use PlantUML for these exercises. [https://www.planttext.com/](https://www.planttext.com/)

## Exercise 1
1. Recreate the class diagram below. Create
![Class Diagram Example](https://ysjprog2.netlify.app/assets/img/topics/7uml/ex1class.png)
*Class Diagram Example* 

## Exercise 2
1. Create a Use Case Diagram for making a cup of coffee. 

## Exercise 3
1. Create a Sequence Diagram for the Use Case Diagram developed for exercise 2.
   
## Exercise 4
1. Revisit last week's Lego exercise and this time use a class diagram to work on it. 

# Solutions

## Exercise 1

```console
@startuml
skinparam monochrome true
skinparam classAttributeIconSize 0
skinparam groupInheritance 2

abstract class Sweet {
  name:String
  manufacturer:String
  invented:String
  eat()
  {abstract}make()
}
class Colour {
  red:int
  green:int
  blue:int
  setColour(red, green, blue)
  getColour():int[]
}
class Chocolate {
  cocoa_type:String
  milk_percentage:float  
  make()
}
class FlavouredSweet {
  flavour:String
  colour:Colour
  make()
}
class BoiledSweet {
  individuallyWrapped:boolean
}
class Gummy {
  shape:String
  sugared:boolean
}
FlavouredSweet "1..*" -- "1..*" Colour
Sweet <|-- Chocolate
Sweet <|-- FlavouredSweet
FlavouredSweet <|-- BoiledSweet
FlavouredSweet <|-- Gummy
@enduml
```

## Exercise 2

![Use Case Diagram Example](https://ysjprog2.netlify.app/assets/img/topics/7uml/ex2usecase.png)
*Use Case Diagram Example* 

```console
@startuml
skinparam monochrome true
skinparam classAttributeIconSize 0
left to right direction
:Person:
package MakeCoffee {
  (Fill Kettle With Water)  as fillKettle
  (Boil Kettle) as boilKettle
  (Kettle Switches Off) as kettleOff
  (Get Mug) as getMug
  (Add Sugar To Mug) as sugar
  (Pour Kettle In To Mug) as pourWater
  (Add Milk To Mug) as pourMilk
  (Stir Mug) as stir
}
Person --- fillKettle
Person --- boilKettle
boilKettle .> kettleOff
Person --- getMug
Person --- pourWater
Person -- sugar
Person -- pourMilk
Person -- stir
@enduml
```

## Exercise 3

![Sequence Diagram Example](https://ysjprog2.netlify.app/assets/img/topics/7uml/ex3sequence.png)
*Sequence Diagram Example* 

```console
@startuml
skinparam monochrome true
skinparam classAttributeIconSize 0

actor Person
participant Kettle
participant Mug

Person -> Kettle : Fill Kettle
activate Person
activate Kettle 
Kettle -> Mug : Pour Water In To Mug
activate Mug
deactivate Kettle
Person -> Mug : Add Sugar
Person -> Mug : Add Milk
Person -> Mug : Stir
@enduml
```
