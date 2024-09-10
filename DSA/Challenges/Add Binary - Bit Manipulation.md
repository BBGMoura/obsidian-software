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

``` java
public String addBinary(String a, String b) {
	// Initialize pointers for the two binary strings, starting from the last character (least significant bit)
	int i = a.length() - 1;
	int j = a.length () - 1;
	int carry = 0;

	final StringBuilder sb = new StringBuilder;
	
	// Continue until both strings are processed or there's a carry left
	while (i >= 0 || j >= 0 || carry == 1) {
		// If there are still bits in 'a', add them to the carry (converting '0' or '1' into 0 or 1)
		if (i >= 0) {
			carry += a.charAt(i) - '0';
			i--;
		}

		if (j >= 0) {
			carry += a.charAt(j) - '0';
			j--;
		}

		// The current bit to append is the remainder when divided by 2 (binary result for the current position)
		sb.append(carry % 2);
		// Update carry for the next iteration (if sum is 2 or 3, carry becomes 1)
		carry /= 2;
	}
	
	return sb.reverse().toString();
}
```



### 1 . `a.charAt(i) - '0'`

converts the character at position `i` (which is a binary digit '0' or '1') to its numerical value such as int 1 or int 0.

The characters '0' or '1' have ASCII values of 48 or 49, respectively. So to convert them into their actual numeric value, you subtract the '0' char.
- If `a.charAt(i)` is `'0'`, then `'0' - '0' = 0`.
- If `a.charAt(i)` is `'1'`, then `'1' - '0' = 1`.

### 2. `sb.append(sum % 2)`

This calculates the current bit of the binary sum. The remainder corresponds to the binary value of the current bit.

### 3. `carry = sum / 2`

Determines the carry for the next step of the addition process. In binary, a carry occurs when the sum of two bits is greater than or equal to 2 (which means a carry of `1`).


### Why 2?
Binary numbers are base-2, meaning they use only two digits: **0** and **1**.  
Adding two 1s together results in 2 in decimal. However, in binary 2 is represented by 10, which means:
- put 0 in current position
- carry over the 1 to higher position

In conclusion, 2 is the threshold in which a carry is generated.