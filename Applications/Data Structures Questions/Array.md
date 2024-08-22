1. What is an array?
An array is a data structure consisting a collection of elements, each identified by an array index.

2. Can array be resized at runtime?
No, in Java the array size is defined at creation.

3. What is the time complexity for accessing an element in an array?
O(1) as it can be accessed directly using it's index.

4. What is the difference between an array and a linked list?
An array is static -> have fixed size and are stored consecutively in memory
A LinkedList is dynamic ->  can grow and do not require contiguous memory allocation. 

contiguous = refers to things being next to each other or forming an unbroken sequence

Contiguous memory allocation -> a single block of memory is reserved for a particular data structure or array. Elements of the data structure or array is stored in consecutive memory locations. 

5. How would you find the smallest and largest element in an array?
Iterate through the array and keep track of smallest and largest elements encounters.

6. Explain the concept of a multi-dimensional array.
It is an array that contains other arrays. For example, 2D array, each element in an array contains another array.
- **Two-Dimensional Array**: `int[][] matrix = {{1, 2, 3}, {4, 5, 6}, {7, 8, 9}};`
- **Three-Dimensional Array**  : `int[][][] cube = {{{1, 2}, {3, 4}}, {{5, 6}, {7, 8}}};` 

7. What is an array index index out of bounds exception?
Exception is thrown when you try to access an array at an index which is outside the bounds of the array

8. How would you reverse an array in-place and in linear time and constant space?

**constant space** -> the space used by the algorithm remains constant regardless of the size of the input array. So, modify the array directly without using any additional data structures.

Using a two pointer technique, the additional space used remains constant -> few variables. Therefore, the space complexity is O(1).

**linear time** -> the time it takes to complete the algorithm grows linearly with the size of the input. If you have an array with `n` element

Using two pointer technique, when you reverse the array:
- traversal: you only have to pass through the array once
- swapping: each element is swapped once with its counterparts

Therefore, the time complexity is O(n).

``` java
public static void resverseArray(int[] array) {
	int left = 0;
	int right = array.length - 1;

	while (left < right) {
		int temp = array[left];
		array[left] = array[right];
		array[right] = temp;

		left++;
		right--;
	}
}
```

9. Explain the concept of a jagged array
A jagged array is an array of arrays, where each sub-array could be of a different length.

10. How can you find duplicate elements in an array?
Add elements to a hash set, as hash sets do not allow duplicate elements. You need to override both equals() and hashCode(). O(n) complexity for space and time.


Otherwise, you can sort through the array, iterate it to find consecutive duplicates. Time complexity is O (n log n). Space complexity is O(1) for in-place sorting or O(n) for non-in place sorting.

Arrays.sort() can be in-place or not. It depends on the type of array being sorted. Primitive types use a variant of Quick sort which is in-place. 
Object arrays uses a variant of Timsort which is a merge between merge sort and insert sort.  Therefore it is O(n) as it requires additional temporary storage.

11. Discuss the advantages and disadvantages of an Array

**advantages:** simple implementation, efficient storage for contiguous data , constant time access O(1) by index
**disadvantages:** not dynamic (Cant be resized), inefficient for insertions and deletions.

12. Explain the concept of a sparse array
An array which most of the elements have the same value. It can be represented using a data structure that only stores non-default (non-zero) values.

Example usage, in engineering FEA where the stiffness matrix for a large structure is often sparse so most of the elements a zero and the interacting elements have none zero values. Stiffness matrix is a concept used to describes the relationship between forces and displacements. 

