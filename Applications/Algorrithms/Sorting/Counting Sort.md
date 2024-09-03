**Counting Sort** non-comparison-based sorting algorithm.  It is efficient when when the range of the input values _(i.e., the difference between the minimum and maximum values)_ is not significantly larger than the number of items to be sorted. It works by counting the **frequency** of each distinct element in the input array and use that information to place the elements in their correct sorted positions.

### Characteristics 
1. **Non-Comparison-Based** - does not compare elements against each other
2. **Stable Sorting** - maintains relative order of elements with equal values
3. **Space Complexity**: `O(n+k)`
	- uses additional space for count array of size `k` and an output array of size `n`.
4. **Time Complexity**: `O(n+k)`
	-  O(n): comes from iterating over the input array, to count the occurrences of each element. Then iterating again to place elements in the output array. `n` is the number of elements in the input array.
	- O(k): comes from creating and processing the count array. `k` is the range of the input of values (difference between min and max values plus one)
5. **Not In-Place**: uses an extra array of input size and the range of input values to sort. 

## Best Use Cases
- large number of elements to sort but range of values is not much large than n
- need stable sorting to maintain order of equivalent integers

``` java
//Example of good use case:
Suppose you have a list of student exam scores, and you need to sort them. The scores range from 0 to 100, and you have 1000 students.

n (no. of elements) = 1000
k (range) = 100 - 10 = 100 

k is much smaller than the number of scores ( k < n )
```

## Execution
Consider the following array of integers:

``` json
Input array : [4, 2, 2, 8, 3, 3, 1];
```

1. Determine the Range
``` json
k = max - min = 8 - 1 = 7
```

2. Initialize count array

Create an array of size m + 1 (where m is maximum value). Initialize all counts to 0.
``` json
Count array : [0, 0, 0, 0, 0, 0, 0, 0, 0] // max +1 = 8 + 1 = 9
```

3.  Count occurrences

Iterate through the input array and increment the count for each value:
``` json
Input: [4, 2, 2, 8, 3, 3, 1]
Count: [0, 1, 2, 2, 1, 0, 0, 0, 1] // 0 based index
```

4. Compute cumulative counts:

Transform the count array to store cumulative counts:
``` json
Cumulative : [0, 1, 3, 5, 6, 6, 6, 6, 7]
```

5. Build the Output Array:

Create output array with same size as the input array. Use the cumulative to count to place elements in the correct position an decrement the count.
``` json
Output: [1, 2, 2, 3, 3, 4, 8]
```


## Coding Java Example

``` Java
import java.util.Arrays;

public static int[] countSort(int[] input) {
	//input= Input array: [4, 2, 2, 8, 3, 3, 1]
	int n = input.length;
   
    // Step 1: find the max value
	int max = input[0];

	for ( int = 0 ; i < n ; i++ ) {
		if (input[i] > max ) {
			max = input[i]
		}
	}

	// Step 2: Initialize the count array with size max + 1
	int[] count = new int[max + 1];

	// Step 3: count the occurances of each number in input array
	for (int i = 0 ; i < n ; i++) {
		count[input[i]]++; //input[0] = 3, count[3] ++ so = 1 
	}

	// Step 4: transforms count array to cumulative count array
	//each index contains the no. of elements less or equal to the index
	// Cumulative count: [0, 1, 3, 5, 6, 6, 6, 6, 7]
	for ( int i = 1 ; i <= max ; i++) {
		count[1] += count[i-1]; //ad count of previous index
	}

	// Step 5: build outpout array using cumulative count array
	//traverse input array right to left
	int[] output = new int[n];
	
	for (int i = n - 1 ; i >= 0 ; i--) {
		int currentValue = input[i]; // i = 6, input[6] = 3
		int position = count[currentValue] - 1; // count[6] -1 = 6 -1 = 5
		output[postion] = currentValue;
		count[currentValue]--; //ensures duplicates are placed in consecutive postions;
	}

	return output;
}
```