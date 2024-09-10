Bit Manipulation is a technique used in a variety of problems to get the solution in an optimized way.  It is all about bitwise operators which directly works upon binary numbers or bits of numbers that help the implementation fast.

## Bitwise Operators
- Bitwise AND &
- Bitwise OR |
- Bitwise XOR ^
- Bitwise NOT !

**Operations:**

The table below illustrates the result when the operation is performed using bitwise operators. Here 0s or 1s mean a sequence of 1 or 0 respectively.

| Operators | Operations | Result |
| --------- | ---------- | ------ |
| XOR       | X ^  0s    | X      |
| XOR       | X ^ 1s     | ~ X    |
| XOR       | X ^X       | 0      |
| AND       | X & 0s     | 0      |
| AND       | X & 1s     | X      |
| AND       | X & X      | X      |
| OR        | X \| 0s    | X      |
| OR        | X \| 1s    | 1s     |
| OR        | X \| X     | X      |

## Bit representation
All data in computer programs are internally stored as bits, i.e., as numbers 0 and 1.

In programming, an n-bit integer is internally stored as a binary number that consists of n bits. For example, the C++ type int is a 32-bit type, which means every int number consists of 32 bits.

``` json
The int number 43 = 00000000000000000000000000101011
```

The bits in the representation are indexed from right to left. To convert a bit representation $b_k ···b_2 b_1 b_0$  into a number, we can use the formula:

$$b_k2^k +…+ b_22^2 + b_12^1 + b_02^0. $$
 $$E.g., 1·2^5+1·2^3 +1·2^1 +1·2^0 = 43.$$
 