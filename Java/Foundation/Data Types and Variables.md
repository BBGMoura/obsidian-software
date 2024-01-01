# Variables

A variable is a container for data.

It is possible to declare  more than one variable of the same data type in one line.

```java
int appleCount, bananaCount, orangeCount;
```

# Data Types
There are Primitive and Non-Primitive types. 

**Primitive types** are data types that are pre-defined by the Java language.  Primitive types are either **numeric** or **boolean**.

**Non-primitive data types** are more complex and are types created by the programmer, not the Java language. Your computer's CPU does not have built-in instructions for non-primitive types like it has for primitives.

![[Data Types.png]]

## Primitive Types

- Holds one value, a single piece of data.
- Value fits in one computer word. (Rarely requires more than one word in resource-constrained computing systems, like a toaster.)
- Modern processors have built-in instructions to store, modify, and remove values. These instructions are triggered with operators.
-  No way to attach behaviour, in the form of methods, to the type.

|Data Type|Size|Default Value|Storage Range|
|:-:|:-:|:-:|:--|
|`byte`|1 byte|0|Whole numbers; -128 to 127|
|`short`|2 bytes|0|Whole numbers; -32,768 to 32,767|
|`int`|4 bytes|0|Whole numbers; -2,147,483,648 to 2,147,483,647|
|`long`|8 bytes|0|Whole numbers; -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807|
|`float`|4 bytes|0.0F|Fractional numbers; up to 6 to 7 decimal points|
|`double`|8 bytes|0.0d|Fractional numbers; up to 15 decimal points|
|`boolean`|1 bit|`false`|`true` or `false`|
|`char`|2 bytes|'\u0000'|single character value|

## Non-Primitive Types
These are known as reference types.

- Holds zero to many values, a collection of data. For example, a `String` is zero to many characters.
- Values span many computer words.
- No built-in processor instructions. A single reference type operation may require many processor-level instructions.
- Type names are upper case: `String`, `Scanner`, `Random`, etc.
- May attach behaviour, in the form of methods, to the type.
 
![[string-equality.svg]]

The default value for all reference types is `null`.

To check for `null`, use the `==` operator instead of calling `.equals` on a potentially-null value.