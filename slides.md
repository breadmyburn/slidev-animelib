---
# try also 'default' to start simple
theme: seriph
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: https://pbs.twimg.com/media/DfhDPspX0AAK7NC?format=jpg&name=large
# apply any windi css classes to the current slide
class: 'text-center'
# https://sli.dev/custom/highlighters.html
highlighter: shiki
# show line numbers in code blocks
lineNumbers: false
# some information about the slides, markdown enabled
info: |
  ## Slidev Starter Template
  Presentation slides for developers.

  Learn more at [Sli.dev](https://sli.dev)
# persist drawings in exports and build
drawings:
  persist: false
# page transition
transition: slide-left
# use UnoCSS
css: unocss
---

# Java Fundamentals

Learning Core Java

<div class="pt-12">
  <span @click="$slidev.nav.next" class="px-2 py-1 rounded cursor-pointer" hover="bg-white bg-opacity-10">
    Press Space for next page <carbon:arrow-right class="inline"/>
  </span>
</div>

<div class="abs-br m-6 flex gap-2">
  <button @click="$slidev.nav.openInEditor()" title="Open in Editor" class="text-xl slidev-icon-btn opacity-50 !border-none !hover:text-white">
    <carbon:edit />
  </button>
  <a href="https://github.com/slidevjs/slidev" target="_blank" alt="GitHub"
    class="text-xl slidev-icon-btn opacity-50 !border-none !hover:text-white">
    <carbon-logo-github />
  </a>
</div>

<!--
The last comment block of each slide will be treated as slide notes. It will be visible and editable in Presenter Mode along with the slide. [Read more in the docs](https://sli.dev/guide/syntax.html#notes)
-->

---
layout: image-right
image: https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSKdixBQ1b2vDy2-i75TH4SgZsshYmOE0BXUWEoyb9YQ_e2mRFJOixYl7PNSUg0mZgeRis&usqp=CAU
---

# Brief Overview of Java

Java is an Object-Oriented Language

- Majority of what is done involves manipulating objects.

- Every object belongs to a specific class.

- An object is an instance of a class.

- A class defines what an object's state can be, and what it can do.

---

# Why use Java?

- **Platform Independent** - Java code can be ran on any platform as long as Java Virtual Machine (JVM) was installed.
- **Wide Range of Applications** - Java is used in Web-based apps, mobile apps, enterprise software, embedded systems, and games.
- **Large Active Community** - Despite being nearly 28 years old, Java is still as popular as ever. Plenty of developers use it, and it has a rich set of libraries and frameworks to help make the development process easier.

---
layout: image-right
image: https://steamuserimages-a.akamaihd.net/ugc/763849701486576504/56894A65A59574D75D110B414CB20B8DD5D2308B/?imw=637&imh=358&ima=fit&impolicy=Letterbox&imcolor=%23000000&letterbox=true
---

# Hello, World!

```ts{all|4|5|1|3|6|all}
package com.breadmyburn

// First Java Program
public class HelloWorld {
    public static void main (String[] args) {
        System.out.println("Hello, World!");
    }
}
```

- `class`: the keyword used to declare a class
- `main`: first method called when the program runs
- `static`: indicates that the method does not operate on any objects
- `void`: does not return any values
- `package`: set of related classes
- `//`: comment

---
layout: image-right
image: https://steamuserimages-a.akamaihd.net/ugc/763849701486576504/56894A65A59574D75D110B414CB20B8DD5D2308B/?imw=637&imh=358&ima=fit&impolicy=Letterbox&imcolor=%23000000&letterbox=true
---

# Method Calls

```ts
// Hello World Example
System.out.println("Hello, World!");
```

- `System`: a class
- `out`: an object or instance of `PrintStream` class
- `println()`: a method of the `PrintStream` class

---

# Invoking Methods

Use the dot notation to invoke an instance method

```ts
object.methodName(arguments)
```

---
layout: image-right
image: https://refactoring.guru/images/refactoring/content/smells/primitive-obsession-01-3x.png
---

 # Data Types

 The Primitive Types

 - Not all Java values are objects.
 - Some values belong to the *primitive types*.
 - There are four (4) signed integer types, two (2) floating-point number types, one (1) character type, and one (1) boolean type.

---

 # Data Types

 The Primitive Types

 ***Signed Integer Types***

 |     |     |
 | --- | --- |
 | **Type** | **Range** |
 | `byte` | -128 to 127 |
 | `short` | -32,768 to 32,767 |
 | `int` | -2,147,483,648 to 2,147,483,647 |
 | `long` | -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807 |

- Note: If you really need an additional bit, you can interpret signed integer values as unsigned.

(ex. Changing the range of `byte` from "-128 to 127" to "0 to 255")

---

# Data Types

The Primitve Types

***Floating-Point Types***
 |     |     |
 | --- | --- |
 | `float` | Approximately ±3.40282347E+38F (6–7 significant decimal digits) |
 | `double` | Approximately ±1.79769313486231570E+308 (15 significant decimal digits) |

- Ex. 3.14, 234.5, 12.3

---

# Data Types

The Primitive Types

***The `char` Type***

- The `char` data type is a single 16-bit Unicode character.
- It used to store characters.
- Its value range lies between `\u0000` (or 0) to `\uffff` (or 65,535)

```ts
char letterA = 'A'
```

***The `boolean` Type***

- The `boolean` data type only has two (2) values: `true` and `false`.
- It is used for simple flags that track true/false conditions

```ts
Boolean one = false
```

---
layout: image-right
image: https://s3.studytonight.com/tutorials/uploads/pictures/1632807040-.png
---

# Variables

- Java is a strong typed language.
- Each variable can only hold values of a specific type.
- When you declare a variable, you specify the type name, and an optional initial value.

```ts
int total = 0;
```

- You must always initialize a variable before you can declare it in a method.

```ts
// This produces a comcpile-time error
int count;
count++
```

---

# Constants

- The `final` keyword denotes that variable's value cannot be changed once it's been assigned.
- By convention, uppercase letters are used for names of constants.

```
final int DAYS_PER_WEEK = 7;
```

- Adding the `static` keyword allows the constant to be declared outside a method, which can be used in multiple methods.

```
public class Calendar {
    public static final int DAYS_PER_WEEK = 7;
    ...
}
```

---
layout: image-right
image: https://www.processmaker.com/wp-content/uploads/2021/02/business-rules-engine-768x512.jpg
---

# Identifier Naming Rules

The name of a variable, method, or class.

- Must begin with a letter.
- It can consist of any letters (even non-Latin), digits, and the symbols `_` and `$`.
- `$` is for automatically generated identifiers.
- `_` by itself is not a valid identifier.
- Letter case is significant. `count` and `Count` are different.
- You cannot use space or symbols in identifiers.
- You cannot use keywords (i.e. `double`, `int`, etc.).

---
layout: image-right
image: https://www.processmaker.com/wp-content/uploads/2021/02/business-rules-engine-768x512.jpg
---

# Identifier Naming Conventions

- Names of variables and methods start with a lowercase letter.
- Names of classes start with an uppercase letter.
- Use `camelCase` (ex. `countOfInvalidInputs`).

---

# Java Operators

Operators are symbols in Java used to perform operations on variables and values.

### Arithmetic Operators

- Used to perform arithmetic operations on variables and data.

 |     |     |
 | --- | --- |
 | **Operator** | **Operation** |
 | `+` | Addition |
 | `-` | Subtraction |
 | `*` | Multiplication |
 | `/` | Division |
 | `%` | Modulo Operation (Remainder after divison) |

---

# Java Operators

#### Assignment Operators

- Used to assign value to variables

|     |     |     |
| --- | --- | --- |
| **Operator** | **Example** | **What it Does** |
| `=` | `a = b;` | `a = b;` |
| `+=` | `a += b;` | `a = a + b;` |
| `-=` | `a -= b;` | `a = a - b;` |
| `*=` | `a *= b;` | `a = a * b;` |
| `/=` | `a /= b;` | `a = a / b;` |
| `%=` | `a %= b;` | `a = a % b;` |

---

# Java Operators

#### Relational Operators

- Used to check the relationship between two (2) operands.

|     |     |     |
| --- | --- | --- |
| **Operator** | **Description** | **Example** |
| `==` | Is Equal To | `1 == 2` returns `false` |
| `!=` | Not Equal To | `1 != 2` returns `true` |
| `>` | Greater Than | `1 > 2` returns `false` |
| `<` | Less Than | `1 < 2` returns `true` |
| `>=` | Greater Than or Equal To | `1 >= 2` returns `false` |
| `<=` | Less Than or Equal To | `1 <= 2` returns `true` |

---

# Java Operators

#### Logical Operators

|     |     |     |
| --- | --- | --- |
| **Operator** | **Examaple** | **Meaning** |
| `&&` (Logical AND) | expression1 && expression2 | `true` only if BOTH expressions are `true` |
| `\|\|` (Logical OR) | expression1 && expression2 | `true` if either expressions are `true` |
| `!` (Logical NOT) | !expression | `true` if expression is `false`, and vice versa |

---

# Java Operators

#### Unary Operators

|     |     |
| --- | --- |
| **Operator** | **Meaning** |
| `+` | Unary plus |
| `-` | Unary minus |
| `++` | Increment operator |
| `--` | Decrement operator |
| `!` | Logical complement operator |

---

# Strings

- It is a sequence of characters.

#### Concatenation

- Use the `+` operator to concatenate two strings.

```ts
String greeting = "Hello";
String phrase = greeting + "World";
// Output: "Hello World"
```

- Concatenating another data type with a string converts it to a string.

```ts
int age = 42;
String output = age + " years";
// Output: "42 years"
```

#### Text Blocks
```
String greeting = """
Hello
World""";
```

---

# Strings

#### `String.join()`

- Using `join` method to combine strings.

```ts
String names = String.join(",", "Bon", "Jovi", "Montes")
// Sets names to "Bon, Jovi, Montes"
```

#### `StringBuilder`

- Using `StringBuilder` to concatenate a large number of strings.

```ts
StringBuilder builder = new StringBuilder();
while (*more strings*) {
    builder.append(*next string*);
}
```

#### `substring` method

 - Takes strings apart

 ```ts
String greeting = "Hello, World!";
String location = greeting.substring(7, 12); 
// Sets location to "World"
 ```

---

# Strings

#### `split` method

- Extract all substrings from a string that are separated by a delimeter.

```ts
String names = "Peter, Paul, Mary";
String[] result = names.split(", ");
// An array of three string ["Peter", "Paul", "Mary"]
```

#### String Comparison

```ts
location.equals("World");
"World".equals(location);
"world".equalsIgnoreCase(location);
```

#### Compare Dictionary Order

```ts
first.compareTo(second);
```

---

# Converting Between Numbers and Strings

#### `Integer.toString` method (Integer to String)

```ts
int n = 42;
String str = Integer.toString(n); // Sets str to "42"
```

#### `Integer.parseInt` method (String to Integer)

```ts
String str = 42;
int n = Integer.parseInt(str); // Sets str to "42"
```

#### `Double.toString` method (Double to String)

```ts
double x = 3.14;
String str = Double.toString(x); // Sets str to "3.14"
```

#### `Integer.parseInt` method (String to Integer)

```ts
String str = 3.14;
int n = double.parseDouble(str); // Sets str to "3.14"
```

---

# Input/Output

#### Reading Input (CLI)

```ts
import java.util.Scanner;

Scanner scanner = new Scanner(system.in);

System.out.println("A Question:");
String name = scanner.nextLine() // String input
int age = scanner.nextInt(); // Integer input
double x = scanner.nextDouble(); // Double input
```

#### Output (CLI)

```ts
System.out.println("Hello, World!")
```

#### Output (Formattted)
```ts
System.out.printf("Hello, %s. Next year, you'll be %d.\n", name, age);
System.out.println("Hello, %s. Next year, you'll be %d.\n".formatted(name, age))
```

---

# Conditional Statements

#### If...Else if...Else Statements

```ts
if (count > 0) {
		double average = sum / count;
		System.out.println(average);
} else if (count == 0) {
		System.out.println(0);
} else {
		System.out.println("Huh?");
}
```

#### Switch Statements

```ts
switch (seasonCode) { // switch statement
		case 0 -> seasonName = "Spring";
		case 1 -> seasonName = "Summer";
		case 2 -> seasonName = "Fall";
		case 3 -> seasonName = "Winter";
		default -> {
				System.out.println("???");
				seasonName = "";
		}
}
```

---

# Loops

#### `while` Loop

```ts
while (*condition*) {
    *expressions*
}
```

#### `while` Loop (with `break` statement)

```ts
while (*condition*) {
    *expressions*
    if (*condition*) break;
    *expressions*
}
```

#### `while` Loop (with `continue` statement)

```ts
while (*condition*) {
    *expressions*
    if (*condition*) continue;
    *expressions*
}
```

---

# Loops

#### `do/while` Loop

```ts
do {
  *expressions*
} while (*condition*);
```

#### `for` Loop

```ts
for (int i = 1; i < target; i *= 2) {
		System.out.println(i);
}
```

---

# Arrays

- For every type, there is a corresponding array type.

- The length of an array can never change.

```ts
String[] names = new String[100];
int[] primes = { 2, 3, 5, 7, 11, 13 };
```

- You can access each element in the `names` array using `names[i]`.

- `array.length()` provides the length of the array.

---

# ArrayList

- A resizable array found in the `java.util` package.

```ts
ArrayList<String> friends = new ArrayList<String>();
```

- Add elements to the end

```ts
friends.add("Peter");
friends.add(0, "Paul"); // Adds before index 0
```

- Remove elements

```ts
friends.remove(1);
```

- Get and replace elements'

```ts
String first = friends.get(0);
friends.set(1, "Mary");
```

- `size()` method returns the current size of the array list.

---

# Array List

- Primitive types use wrapper classes for ArrayList. 

- `ArrayList<Integer>`

- `ArrayList<Byte>`

- `ArrayList<Short>`

- `ArrayList<Long>`

- `ArrayList<Character>`

- `ArrayList<Float>`

- `ArrayList<Double>`

- `ArrayList<Boolean>`

---

# Objects

- Each object can have its own state.

- The state affects the results that you get form calling a method.

- Constructing objects is one of the key aspects of Java.

```ts
Random generator = new Random();
System.out.println(generator.nextInt())
```

---

# Classes and Methods

```ts
public class Employee {
    private String name;
    private double salary;

    public Employee(String name, double salary) {
        this.name = name;
        this.salary = salary;
    }

    public String getName() {
        return name;
    }
}
```

```ts
Employee fred = new Employee("Fred", 1000);
fred.getName() // returns name
```

---

# Extending Classes

### Super- and Subclasses

```ts
public class Manager extends Employee {
    *added fields* 
    *added or overrided methods
}
```

### Example

```ts
public class Manager extends Employee {
    
    public Manager(String name) {
		    super(name);
    }
    
    public String getName() {
        return super.name + " is a manager.";
    }
}
```

---

# Packages

- In Java, you place related classes into a package.
- Packages are convenient for organizing your work and for separating it from code libraries provided by others. 

#### Declaration
```ts
package com.breadmyburn 
```

#### Import Classes
```ts
import java.util.Random
import java.util.*
```

---

# Interfaces

- A template that can be applied to a class.
- Similar to inheritance, but specifies what a class has/must do.

```ts
public interface Predator {
    void hunt();
}
```

#### Implementing Interfaces

```ts
public class Tiger implements Predator {
    public void hunt() {
        System.out.println("Time to hunt!")
    } 
}

public class Fish implements Predator, Prey {
    public void hunt() {
        System.out.println("Time to hunt!")
    } 

    public void flee() {
        System.out.println("I'm out!")
    }
}
```

---

# Abstract Methods and Classes

#### Abstract Classes
- A class that you can't instantiate. You can't create an object from abstract classes.
- The abstract class enforces and organizes what every subclass of the superclss has to have.

#### Abstract Method
- When it doesn’t make sense to implement a method in an abstract class since the child classes will have different outputs for that method

```ts
public abstract class Animal {
    String name;

    public Animal(String name) {
        this.name = name;
    }

    public String getName() {
        return name;
    }

    public abstract void greeting();
}
```

---

# Abstract vs Interface

- Every method is an interface is assumed to be abstract.
- You can implement as many interfaces as you want, but can only extend one class.
- Every field declared in an interface is going to be `static` and `final`.

#### When to Use?
- **Abstract class:** If you have a lot of closely related classes that you want to have the same functionality and the same types of fields available.

- **Interface:** if you have a lot unrelated classes that you all want to be able to do a certain thing that makes it so you can guarantee that other types of classes are able to use that method despite not being a subclass of a certain class.

---

# Lambda Expressions

- A lambda expression is a block of code that you can pass around so it can be executed later, once or multiple times.

```ts
(String first, String second) -> first.length() - second.length()
```

```ts
(String first, String second) -> {
		int difference = first.length() < second.length();
		if (difference < 0) return -1;
		else if (difference > 0) return 1;
		else return 0;
}
```

---

# Exception Handling

#### Throwing Exceptions

```ts
if (low > high)
		throw new IllegalArgumentException(
				"low should be <= high but low is %d and high is
%d".formatted(low, high));
```

#### Try-Catch

```ts
try {
		statements
} catch (Exception ex) {
		handler
}
```

---

# Exception Handling

#### Try-Catch (more than one exception)

```ts
try {
statements
} catch (ExceptionClass1 ex) {
		handler1
} catch (ExceptionClass2 ex) {
		handler2
} catch (ExceptionClass3 ex) {
		handler3
}
```

#### Try-Catch (Alternative)

```ts
try {
		statements
} catch (ExceptionClass1 | ExceptionClass2 | ExceptionClass3 ex) {
		handler
}
```

---

# Exception Handling

#### The `finally` Clause

- The finally clause is executed when the try block comes to an end, either normally or due to an exception.

```ts
try {
		statements
} catch (Exception e) {
		handler
} finally {
		statements
}
```

---

# Annotations

- Tags you insert into your code that can be processed.

#### Example

`@Override`: Makes the compiler check that the annotated method really overrides a method from the superclass.

---

# Standard Libraries (Stdlib)

- `java.lang`: Provides classes that are fundamental to the design of the Java programming language.
- `java.math`: For performing arbitrary-precision integer arithmetic (`BigInteger`) and arbitrary-precision decimal arithmetic (`BigDecimal`).
- `java.util`: Contains the collections framework. 

---

# Libraries

- **Jackson:** A suite of data processing libraries. 
- **Maven:** Repository that manages configurations, documentation, build configuration, and dependency which is specified in the `pom.xml` file.
- **Log5j:** A logging library.
- **JUnit:** Writing unit tests.

---

# Frameworks

- **Spring:** Framework for building Java-based web applications.
- **Hibernate:** establish comunication between Java and RDBMS.

---

# References

- Core Java for the Impatient 3rd Edition
- Javatpoint Java Tutorial
- Learn Java Programming - Programiz
- Abstract Classes and Methods in Java Explained in 7 Minutes by Coding with John
- Java interface 🦅 by Bro Code
- Java™ Platform, Standard Edition 7 API Specification
- java.util (Java Platform SE 8)
