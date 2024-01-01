An array which stores arrays is called a multi-dimensional array. It is like a table of data. It has rows and columns.  

There are no limits to this, you can create an array which stores arrays. These arrays can also store more arrays.

## Declaration

```java
int[][] values = new int[10][12];
```

This initialises a multi-dimensional array with a specific capacity pf 10 rows and 12 columns.

All arrays are reference types, so their default value is `null`. If you omit the second capacity, all arrays in the second dimension start as `null` but can be assigned later.

```java
// there are 45 null int[] in values
int[][] values = new int[45][];

// the array at index 5 is no longer null
// it's now an int array with a capacity of 6.
values[5] = new int[6];

// the array at index 15 is no longer null
// it's now an int array with a capacity of 22.
values[15] = new int[22];
```

Omitting the first capacity, `int[][] values = new int[][];`, is not valid. It's a syntax error.

Array literal notation works with multi-dimensional arrays.

```java
String[][] threeOfAKind = { 
    { "Strawberry", "Blueberry", "Gooseberry" }, 
    { "Red", "Yellow", "Blue" },
    { "Atlantic", "Pacific", "Indian" } 
};

int[][][] valueCube = { 
    { 
        { 1, 2, 3 }, 
        { 4, 5, 6 }, 
        { 7, 8, 9 } 
    }, 
    { 
        { 11, 12, 13 }, 
        { 14, 15, 16 }, 
        { 17, 18, 19 } 
    },                
    { 
        { 21, 22, 23 }, 
        { 24, 25, 26 }, 
        { 27, 28, 29 } 
    }
};
```

## Reading

To access an element in a multi-dimensional array, provide an index for each dimension.

```java
// Read from the second "row" and third "column";
String element = threeOfAKind[1][2];

System.out.println(element);            // Blue
System.out.println(threeOfAKind[2][0]); // Atlantic
```

If we omit a dimension, the value of the expression is one of the sub-arrays. A sub-array can be replaced.

```java
int value = valueCube[1][1][1];
System.out.println(value);               // 15

int[] oneDimension = valueCube[1][1];
System.out.println(oneDimension[2]);     // 16

int[][] twoDimensions = valueCube[1];
System.out.println(twoDimensions[1][0]); // 14

// Replace a sub-array.
valueCube[2][2] = new int[] { 37, 38, 39 };
System.out.println(valueCube[2][2][0]);  // 37
```
## Writing 
Replace values using the index of the element:
```java
// Replace the element in t~
he third row, first column.
threeOfAKind[2][0] = "Arctic";
```
## Looping
To visit every element in a multi-dimensional array, loops must be nested. One loop is required per dimension. 

```java
for (int row = 0; row < threeOfAKind.length; row++) {
    for (int col = 0; col < threeOfAKind[row].length; col++) {
        System.out.println(threeOfAKind[row][col]);
    }
}
```

Use caution when looping over multi-dimensional arrays, because there's no guarantee that a sub-array is not null.

```java
for (int row = 0; row < values.length; row++) {

    System.out.printf("Row %s: ", row);

    if (values[row] == null) {
        System.out.println("null");
        continue;
    }

    for (int col = 0; col < values[row].length; col++) {
        System.out.print(values[row][col] + " ");
    }

    System.out.println();
}

/**
Row 0: 1 2 3
Row 1: null
Row 2: 7 8 9
Row 3: null
Row 4: null
*/

```

