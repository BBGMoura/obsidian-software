Arrays manage a single data type. To define an array, you must define the data type and how many variables it can hold. You **cannot**  change the length of the array. You must create a new array and clone the elements.

Arrays can also be store in an array. This is called a [[Multi-Dimensional Array]].
## Declaration
```java
String[] names = new String[7];
```

In this case, the datatype is String and it can store 7 elements.

When initialised,  elements have their default value. In this case, a **String** defaults to null. An **int** has a default of 0.

_note: you can initialise an array with 0. This is an array which cannot hold any data._

Assigning values index by index is fussy and error-prone.  You may also initialise it using an array literal syntax. Instead of using `new type[]` .

```java
String[] planets = { "Mercury", "Venus", "Earth", "Mars", "Jupiter", "Saturn", "Uranus", "Neptune" };
```

You can also use this way of initialising:
```java
values = new int[] { 4, 5, 6 };
```

## Writing
Assign an array based on it's index: 
```java
planets[0] = "Mercury";
planets[1] = "Venus";
planets[2] = "Mars";
```
This can also be used to reassign values to an index in an array.
## Reading
Read an array using square brackets and an integer index:
```java
planets[0]
```

Referring to an index in the array which does not exist will cause a run-time exception.

## Looping
We can loop through and array using `length` function on an array and a `for loop`.

```java
String[] elements = { "Hydrogen", "Helium", "Lithium", "Beryllium" };

// loop from front to back
for (int index = 0; index < elements.length; index++) {
    String elementName = elements[index];
    System.out.printf("The element at index %s is %s.%n", index, elementName);
}
```

