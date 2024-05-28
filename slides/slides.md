---
author: Philipp Mühlehner
lang: en
title: Slides
theme: white
highlightTheme: monokai
revealOptions:
  transition: 'fade'
  slideNumber: false
---

# Literals, Constants, Variables, Data Types

----

## Literals, Constants, Variables

* A **Literal** is a value appearing in your program. Examples:
  * String literal: `"Hello World"`
  * Character literal: `'A'`
  * Integer literal: `42`
  * Floating point literal: `3.1415`
  * Boolean literal: `true`, `false`

----

* A **Constants** is a symbolic name for a literal
  * The value of a constant *cannot* change!
  * The names of constants in Java are usually written in *UPPERCASE LETTERS*.
  * E.g. `final int ANSWER = 42;` or `final string GREETING = "Hello World";`

----

* A **Variable** is a symbolic name whose value *can* change
  * The names of constants in Java are usually written in *lowercase letters*.
  * **Assignment**: Statement that assigns a value to a variable
  * E.g. `int answer = 42;` or `String greeting = "Hello World";`
* The **data type** defines what values the constant or variable can contain
  * E.g. Strings, integer numbers

----

## Literals

Let's use **Literals** of different types in a short program:

```java [|1|2|4|8]
System.out.print("Take ");                    // "Take " is a String Literal
System.out.print(3);                          // 3 is an Integer Literal
System.out.print(" pizzas and bake it for ");
System.out.print(1.5);                        // 1.5 is a Floating Point Literal
System.out.println(" minutes.");
System.out.print("Believe me, it is ");
System.out.print(true);                       // True is a Boolean Literal
System.out.println(" that the pizza will be delicious!");
```

----

## Constants

Let's use **constants** of different types in a short program:

```java [|1-3|6,9-10|12-14]
// Let's define a String constant for the address of our school. The address is
// very unlikely to change -> a constant is a good choice.
final String SCHOOL_ADDRESS = "Limesstraße 12-14, 4060 Leonding";
System.out.print("I go to school at ");
System.out.println(SCHOOL_ADDRESS); // Here we use the constant
System.out.print("Please drive me to school at ");
System.out.println(SCHOOL_ADDRESS); // Here we use the constant again.
                                   // We DO NOT have to repeat the school's address 👍
// Let's define an Integer constant and use it
final int NUMBER_OF_STUDENTS = 31;
System.out.print(NUMBER_OF_STUDENTS);
System.out.println(" students are in our class.");
```

----

## Variables

Let's use a **Variable** in a short program:

```java [|2-3|9-11]
Scanner myObj = new Scanner(System.in);
System.out.print("Please type in your name: ");
String name = myObj.nextln();  // Here we declare a variable called name 
                                // and we assign it the value of the user input.
System.out.print("Your name is ");
System.out.print(name);         // Here we use the variable to print out the entered name.
System.out.println();
System.out.print("Please type in the name of a friend: ");
name = myObj.nextln();         // Here we let the user enter another name.
                                // The value of name changes! Therefore, it has to be
                                // a VARIABLE and cannot be a constant.
System.out.print("Your friend's name is ");
System.out.print(name);
```

----

## Scanner

```java [|1|4|7]
import java.util.Scanner;  // Import the Scanner class
class UsersInput {
    public static void main(String[] args) {
        Scanner myObj = new Scanner(System.in);  // Create a Scanner object
        System.out.println("Enter username");

        String userName = myObj.nextln();  // Read user input
        System.out.println("Username is: " + userName);  // Output user input
    }
}
```

----

## Scanner

```java [|1|4|9,12,13|16-18]
import java.util.Scanner;
class InputTypes {
    public static void main(String[] args) {
        Scanner myObj = new Scanner(System.in);

        System.out.println("Enter name, age and salary:");

        // String input
        String name = myObj.nextln();

        // Numerical input
        int age = myObj.nextInt();
        double salary = myObj.nextDouble();

        // Output input by user
        System.out.println("Name: " + name);
        System.out.println("Age: " + age);
        System.out.println("Salary: " + salary);
    }
}
```

----

## Data Types

> Java has [a lot of data types](https://www.w3schools.com/java/java_data_types.asp). For now, you will need:

| Data Type | Description |
|--|--|
| [`String`](https://www.w3schools.com/java/java_strings.asp) | Sequence of zero or more characters (Unicode) |
| [`char`](https://www.w3schools.com/java/java_data_types_characters.asp) | Single character (Unicode) |
| [`boolean`](https://www.w3schools.com/java/java_data_types_boolean.asp) | Boolean value (`true` or `false`) |
| [`int`, `long`, `short`, etc.](https://www.w3schools.com/java/java_data_types_numbers.asp) | Integral numeric values (no decimal places) |
| [`float`, `double`](https://www.w3schools.com/java/java_data_types_numbers.asp) | Floating point numeric values (general guideln: Use `double` for mathematical calculations

----

## Literals for Data Types

| Data Type | Example Literal | Notes |
|--|--|--|
| `String` | `"Hello World"` | Double quotes|
| `char` | `'A'`|Single quotes |
| `boolean` | `true`, `false` | |
| `int` | `42` | |
| `long` | `42L` | Suffix *L* (=long)|
| `float` | `42f` | Suffix *f* (=float)|
| `double` | `42d` | Suffix *d* (=double)|


<!--String Parsing -->
----

## Important Operators

* For numeric types: [Arithmetic Operators](https://www.w3schools.com/java/java_operators.asp)
  * Basic algorithmic operations (`+`, `-`, `/`, `*`)
  * Increment (`++`, `+=`) and decrement (`--`, `-=`)
  * Remainder (often referred to as *Modulo*) (`%`)
* To compare values: [Comparison Operators](https://www.w3schools.com/java/java_operators.asp)
  * Relational operators (`>`, `<`, `>=`, `<=`)
  * Check if equal (`==`)
  * Check if not equal (`!=`)
* Not all operators make sense for all types. Examples:
  * `+` for integer values 👍 - obviously works
  * `/` for string values 🤔 - makes no sense
  * `>` for Boolean values 🤔 - also makes no sense

----

## Examples: Increment, Decrement

```java[|3-4|6-7|9-10]
int i = 1;
i = i + 1; // i is now 2
i = i - 1; // i is now back to 1
i++; // i is now 2
i--; // i is now back to 1
i += 2; // i is now 3
i -= 2; // i is now back to 1
```

----

## Example: Area Calculator

```java [|1|4|7-8|9]
System.out.println("Welcome to the AREA CALCULATOR\n");   // Note: \n for additional empty line

System.out.print("Please enter the length of the room: ");
int length = myObj.nextInt();                             // Note: Variable declaration and assignment
System.out.print("Please enter the width of the room: ");
int width = myObj.nextInt();
int area = length * width;                                // Note: Variable declaration and assignment
                                                          // Also note: Multiplication operator
System.out.println("The area of the room is: " + area);   // Note: String concatination with + operator
```

----

## Area Calculator Flowchart

<div class="container" data-markdown><div class="col" data-markdown>

> A flowchart is a diagram that depicts a process, system or computer algorithm.

* Flowcharts have successfully been used for a long time
  * Also outside of computer programming
* Readable for programmers and end users
  * Great way to communicate process structure between technical and business experts
* Read [more](https://www.lucidchart.com/pages/what-is-a-flowchart-tutorial)

</div><div class="col" data-markdown>

[![](https://mermaid.ink/img/pako:eNpNUV1rwjAU_SshTzo6O9utamEDmb7tYczBYK0Psbltw9KmJLcTEf_7krTKnnLPxz0cbs60UBxoSkupjkXNNJLPTd4SskM7TzL_7Kfk_v6FfIEsVANZ-K5Fi-Q4QNKAMayCcO_WRo_3v0FbYZ2Fa_NDSqWJ9HjwDdoQK_h_19HBMcyN3rPWwLJXJoteMgTCLCTPYyC5G3b8ijP6jQ8wvcRrV-3RkDoo3rRD1U2ybcv3UxrQBnTDBLfHODtfTrGGBnKa2tE2A4M5DUbFAyfUIKUiR6Ulz2neXmwO61HtTm1BU9Q9BLTvuC29EazSrKFpyaS5sVsuUOkbKRXjYOGZ4qlz31IJgzayUG0pKsf3Wlq6RuxMGoZOnlUC6_4ws3cPjeDuD-vfVRImUbJkUQzJImZPccyLw3y1LKPHeckXD_OI0csloB1rv5W6trr8AX-7r0I)](https://mermaid.live/edit#pako:eNpNUV1rwjAU_SshTzo6O9utamEDmb7tYczBYK0Psbltw9KmJLcTEf_7krTKnnLPxz0cbs60UBxoSkupjkXNNJLPTd4SskM7TzL_7Kfk_v6FfIEsVANZ-K5Fi-Q4QNKAMayCcO_WRo_3v0FbYZ2Fa_NDSqWJ9HjwDdoQK_h_19HBMcyN3rPWwLJXJoteMgTCLCTPYyC5G3b8ijP6jQ8wvcRrV-3RkDoo3rRD1U2ybcv3UxrQBnTDBLfHODtfTrGGBnKa2tE2A4M5DUbFAyfUIKUiR6Ulz2neXmwO61HtTm1BU9Q9BLTvuC29EazSrKFpyaS5sVsuUOkbKRXjYOGZ4qlz31IJgzayUG0pKsf3Wlq6RuxMGoZOnlUC6_4ws3cPjeDuD-vfVRImUbJkUQzJImZPccyLw3y1LKPHeckXD_OI0csloB1rv5W6trr8AX-7r0I)

</div></div>

----

## Number Analyzer

```java [|2|4|5-6|8-9|11-12]
System.out.print("Please enter a number: ");
int number = myObj.nextInt();
int remainder = number % 2;
boolean isEvenNumber = remainder == 0;
System.out.println("It is " + isEvenNumber + " that the number is even.");
boolean isGreaterThanFive = number > 5;
System.out.println("It is " + isGreaterThanFive + " that the number is greater than 5.");
number++;
System.out.println("The next number is " + number);
```

----

## `Math`

* The class `Math` contains a large number of very useful mathematical functions and Constants
  * PI, absolute value, trigonometric functions (sin, tan, cos, etc.), etc.
  * Next slide contains a table with the most important functions that you should remember for now

----

## `Math`

|Function|Description|
|--|--|
| [`Math.PI`](https://www.w3schools.com/java/java_math.asp) | The constant π |
| [`Math.abs`](https://www.w3schools.com/java/java_math.asp) | Absolute value of a specified number |
| [`Math.floor`](https://www.w3schools.com/java/java_math.asp) | Returns largest integral value <= the specified number (e.g. 1.4 becomes 1, 1.9 becomes 1, 2.1 becomes 2) |
| [`Math.ceil`](https://www.w3schools.com/java/java_math.asp) | Returns smallest integral value >= the specified number (e.g. 1.4 becomes 2, 1.9 becomes 2, 2.1 becomes 3) |
| [`Math.min`](https://www.w3schools.com/java/java_math.asp),&nbsp;[`Math.max`](https://www.w3schools.com/java/java_math.asp) | Returns the smaller/larger of two numbers. |
| [`Math.pow`](https://www.w3schools.com/java/java_math.asp) | Returns a specified number raised to the specified power |
| [`Math.round`](https://www.w3schools.com/java/java_math.asp) | Rounds a value to the nearest integer or to the specified number of fractional digits |

----

## Area Calculator Circle
> Build an area calculator like before, but this time for circles, not rectangles
* Ask the user for the radius of the circle.
* The formula for calculating the area of a circle is `A = π * r²`
  * Use a *constant* for π and use the value 3.1415927
  * Tip: Use the pre-defined constant [`Math.PI`](https://www.w3schools.com/java/java_math.asp)
* Print the area of the circle on the screen.

----

## Expressions

> We call calculations that result in a value of a certain type **Expressions**
* Expressions from previous examples:
  * `length * width` - result is a number
  * `number % 2` - result is a number
  * `remainder == 0` - result is a Boolean value (`true` or `false`)
  * `number > 5` - result is a Boolean value (`true` or `false`)
  * `"The next number is " + number` - result is a string
* As you can see, expressions do *not* end with a semicolon
* Expressions will become very important in more advanced code examples