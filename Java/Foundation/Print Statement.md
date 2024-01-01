Print statements output information to the output terminal. It is useful when debugging programs and finding errors.

## System.out.println

``` java
System.out.println("Hello World");
//Hello World
```

- `system`  is a built-in Java class that contains useful tools for our programs.
- `out`  is short for "output".
- `println`  is short for "print line".

## System.out.print

Similarly we can also use :
``` java
System.out.print("Hello");
System.out.print(" World");
//Hello World
```

`print()` instead of `println()` . This outputs all statements on one line.

It’s important to remember where you left your program’s “cursor”. If you use `println()` the cursor is moved to the next line. If you use `print()` the cursor stays on the same line.

## System.out.printf

The `printf` method accepts one or more arguments. The first and most important is a format string. A **format string** is a Java string with its own special syntax. The percent character, `%`, defines a placeholder. `printf`'s remaining arguments replace placeholders in order.

```java
System.out.printf("%s has %s %s and can jump %s inches vertically.", "Nomi", 3, "dogs", 37.68);
```

## Format Strings
The `String.format` method uses a format string and arguments to generate a new string.

```java
String firstName = "Husein";
String lastName = "Vaan";

// fullName becomes "Husein Vaan"
String fullName = String.format("%s %s", firstName, lastName); 

// title becomes "Name: Husein Vaan, Occupation: Game Developer"
String title = String.format("Name: %s, Occupation: %s", fullName, "Game Developer");
```

As a general rule, if we're building a string from two or three parts, string concatenation is okay. Beyond that, professional software developers prefer formatted strings.

