In Fibonacci series, the _next number is the sum of the previous two numbers_. 

For example, 0, 1, 1, 2, 3, 5, 8, 13, 21, 34, 55, etc.

The first two numbers of the Fibonacci series is 0, 1.

There are two ways to write the Fibonacci series in java:
- using a loop
- using recursion 

## For Loop
``` java
static void Fibonacci(int n) {
	int num1 = 0;
	int num2 = 1;

	for (int i = 0; i < N; i++) {
		System.out.print(num1 + " ");
		int num3 = num2 + num1;
		num1 = num2;
		num2 = num3;
	}
}
```

## Recursion 
Since Fibonacci Number is the summation of the two previous numbers, we can use recursion as per the following conditions:
1. Get the number whose Fibonacci series needs to be calculated.
2. Recursively iterate from value N to 1.

``` java
public int fibonacci(int n) {
	if (n <= 1) {
		retun n;
	}

	return fibonacci(n - 1) + fib(n - 2);
}

public static void main(String args[]) {
	int N = 10;

	for (int i = 0; i < N; i++) {
		System.put.println(fib(i));
	}
}
```