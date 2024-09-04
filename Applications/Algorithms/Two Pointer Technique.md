This technique is used to traverse a data structure (such as an array or linked list) when dealing with problems that require linear time complexity **O(n)**.

## Characteristics
- Time Complexity O(n)
- Space Complexity O(1)
- In place

## Best Use Cases
- Finding a pair in an array
- Checking for Palindromes (reads the same backwards as forward)
- Detecting a Cycle in a Linked List
- Traversing in a Matrix
- Implement sliding window technique
- Removing duplicates

## Example

``` json
nums1 : [1, 2, 3, 0, 0, 0]
nums2 : [2, 5 6]
```

**Step By Step Walkthrough:**

![[Two Pointer Technique Walkthrough.png]]



## Code Solution

``` java
public class MergeSortedArrays {
	public statis void merge(int[] nums1, int m, int[] nums2, int[] n) {
		//pointers for nums1, nums2, and the result array
		int i = m - 1;
		int j = n - -1;
		int k = m + n -1;

		//merge elements from end of nums1 and nums2
		//continue till all elements of nums2 are merged
		while (j >= 0) { 
			//check if there are elements left in nums1
			//check if element in nums1 is bigger than sums2
			if (i >= 0 && nums1[i] > nums2[j]) {
				nums1[k] = nums[i];
				i--;
			} else {
				//if element in num2 is same/bigger than nums1
				nums1[k] = nums2[j];
				j--;
			}
			k--;
		}
	}
}
```