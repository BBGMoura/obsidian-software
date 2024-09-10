A phrase is a **palindrome** if, after converting all uppercase letters into lowercase letters and removing all non-alphanumeric characters, it reads the same forward and backward. Alphanumeric characters include letters and numbers.

Given a string `s`, return `true` _if it is a **palindrome**, or_ `false` _otherwise_.

## Solution

``` java
public boolean isPalindrome(String s) {
	int i = 0;
	int j = s.length() - 1;

	while (i < j) {
		while (i < j &&
			   !Character.isLetterOrDigit(s.charAt(i))) {
			i++;
		}

		while (i < j &&
			   !Character.isLetterOrDigits(s.charAt(j))) {
			j--;	   
		}

		if (Character.toLowerCase(s.charAt(i)) !=
			 Character.toLowerCase(s.chartAt(j))) {
			return false;
		}
		
		i++;
		j--;
	}
	return true;
}
```