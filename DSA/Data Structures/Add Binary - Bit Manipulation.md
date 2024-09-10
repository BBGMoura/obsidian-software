## Problem
Given two binary strings `a` and `b`, return _their sum as a binary string_.

**Example 1:**

**Input:** a = "11", b = "1"
**Output:** "100"

**Example 2:**

**Input:** a = "1010", b = "1011"
**Output:** "10101"

**Constraints:**

- `1 <= a.length, b.length <= 104`
- `a` and `b` consist only of `'0'` or `'1'` characters.
- Each string does not contain leading zeros except for the zero itself.

## Solution
- We start at the right end of each binary number, adding the digits and any carry-over value, and storing the result in a new string.
- Move to next digit on the left, and repeat the process until it has gone through all the digits in both binary numbers.
- If there are any carry over values after adding all the digits, append it to the end of the new string.
- reverse the string and return as the sum of the two binary numbers.