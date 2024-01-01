##  If Statement
 If the boolean expression evaluates to `true`, code inside the block executes. If it evaluates to `false`, the code block is skipped.

```java
if (true) {
    System.out.println("It's true.");
}  else {
    // does not execute
}
```

An `else` clause is useful when there's always an alternative to the `if` condition. If a second chunk of code _must_ run when an `if`'s condition is `false`, use an `else`.

## Else if
An `if` statement may be added immediately after an `else` clause to check multiple boolean conditions.

```java
if (packageWeight > 100.0) {      // check first condition
    System.out.println("too big for standard shipping");
} else if (packageWeight < 1.0) { // check a second condition
    System.out.println("too small. send a letter.");
} else {                          // the `else` clause executes if all other conditions are false.
    System.out.println("can ship");
}
```

#### Bad Example

```java
int age = 64;
boolean isGoldMember = true;

// WARNING: BAD CODE below!
if (age > 59) {
    System.out.println("senior discount");
} else if (age > 59 && isGoldMember) {
    // this will never happen because 
    // the "if" condition will always evaluate to true first!
    System.out.println("senior AND gold member discount");
} else if (age <= 18) {
    System.out.println("student discount");
} else if (age < 5) {
    // will never happen because the student discount
    // was true first!
    System.out.println("kids eat free!");
} else {
    System.out.println("standard rate");
}
```

## Switch Statement
The `switch` statement inspects a value and then executes code for specific value conditions.

```java
int place = 2;
String ribbonColor;

// 1. switch keyword, then an expression (often a variable) in parentheses, followed by a block
switch (place) {
    case 1: // 2. case keyword, then a literal value, then colon.
        // if the switch's expression resolves to the case's value,
        // all code nested inside the case executes.
        ribbonColor = "blue";
        System.out.println("first place!");
        break; // 3. break keyword, immediately exits the switch's block
    case 2:
        ribbonColor = "red";
        System.out.println("second place!");
        break;
    case 3:
        ribbonColor = "white";
        System.out.println("third place!");
        break;
    default: // 4. default keyword, happens when no other case matched
        ribbonColor = "unknown";
}
```

A `switch` statement only matches specific values. It can't evaluate boolean conditions like `value < 2.34`. If a condition is required, use an `if/else`.

Case clauses can be stacked. Since execution falls through when a case matches, we can group cases together to trigger one code block for several cases.

```java
String color = "orange";

switch (color) {
    case "red":
    case "yellow":
    case "blue":
        System.out.println("primary color");
        break;
    case "green":
    case "purple":
    case "orange":
        System.out.println("secondary color");
        break;
    default:
        System.out.println("regular color");
}
```

## Ternary Operator

```java
backpack[i] == null ? "[empty]" : backpack[i]
```


## Conclusion
`if` statements are useful when:

- We are evaluating an expression, like `x < 5`, instead of checking a specific value.
- Conditions are complex.
- A range of values triggers a single code block.

`switch` statements are useful when:

- We have a relatively small, fixed set of values to evaluate.
- Each value's branching is unique.