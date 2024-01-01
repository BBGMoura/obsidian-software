## While Loop

### Steps
1. Evaluate the `while` condition.
2. If `true`, execute the block.
3. If `false`, skip the block and execute the first line of code after it.
4. After the block is complete, go back to step 1.

```java
while (true) {
    System.out.println("this message is repeated forever.");
}
```

## Do/While Loop

### Steps
1. Execute the code block.
2. Evaluate the `while` condition.
3. If `true`, go back to step 1.
4. If `false`, execute the first line of code after the loop.

```java
do {
    System.out.println("repeats forever");
} while (true);
```

## For Loop
The `for` statement is a specialized loop with three clauses:

- The first initializes variables or state.
- The second is a boolean expression. If it evaluates to `true`, the `for`'s code block executes, just like a `while` statement.
- The third clause runs after each loop. It can be used to update variables or state.

Clauses are separated by semicolons. All clauses are optional.

```java
String message = "Looping...";

// Standard format
for (int index = 0; index < message.length(); index++) {
    System.out.println(message.charAt(index));
}
```

Counting down:

```java
System.out.println("Countdown:");
for (int i = 10; i > 0; i--) {
    System.out.println(i);
}
System.out.println("Blast off!");
```

Clauses can also include method calls.

```java
Scanner console = new Scanner(System.in);
System.out.print("Guess a fruit: ");
for (String input = console.nextLine(); !input.equals("persimmon"); input = console.nextLine()) {
    System.out.printf("%s isn't correct.%nGuess a fruit: ", input);
}
System.out.println("You got it!");
```

## Break and Continue Keywords

### Break

The `break` keyword immediately terminates a loop when the `break` statement is executed, regardless of the loop's boolean condition.
```java
for (int i = 0; i < 10000; i++) {
    System.out.println("First line in the block: " + i);

    // a 10% chance to break out of the loop
    if (Math.random() > 0.9) {
        System.out.println("breaking!");
        break; // exit the for's code block immediately
    }

    System.out.println("Last line in the block: " + i);
}
```


### Continue

The `continue` keyword stops the current iteration (or repetition) but keeps looping. When a `continue` statement is executed, the remaining code in the block is skipped and the next iteration begins as long as the loop condition evaluates to `true`.

A `break` or `continue` inside a nested loop only affects the nearest code block. It never controls the outer loop.