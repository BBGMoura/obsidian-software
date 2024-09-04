A Sorting algorithm is used to rearrange a given array or list of elements according to a _comparison operator_ on the elements.

Sorting means reordering of all the elements either in ascending or in descending order.

O(1) - Constant: fixed amount of memory/time and does not depend on input.                 
O(n) - Linear: depends on the input. memory usage/time grows linearly with the input size.
### Terminology
- **In-place Sorting**: uses constant space for producing the output  or copying elements to a temporary storage. Examples: Selection Sort, Bubble Sort, Insertion Sort and Heap Sort.
- **Internal Storage**: all data is placed in the main memory or internal memory. In internal sorting, the problem cannot take input beyond its size. Example: Heap Sort, Bubble Sort, Selection Sort, Quick Sort, Sell Short, Insertion Sort.
- **External Sorting**: all the data that needs to be sorted cannot be placed in memory at a time. It is used for sorting massive amounts of data. Examples: Merge sort, Tag sort, Polyphase Sort, Four tape Sort, External radix Sort. 
- **Stable Sorting**: when two same items appear in the same order in sorted data as in the original array. Examples: Merge Sort, Insertion Sort, Bubble Sort.
- **Unstable Sorting**: when two same data appear in the different order in  stored data. Examples: Selection Sort, Quick Sort, Heap Sort.

### Characteristics 
- **Time Complexity**: how long it takes to run an algorithm. Is used to categorize sorting algorithms. The worst-case, average-case, and best-case performance of a sorting algorithm can be used to quantify the time complexity of the process.
- **Auxiliary Space**: amount of extra space (apart from the input array) needed to sort. For example, Merge Sort 0(n) and and Insertion Sort O(1) auxiliary space.


## Sorting Algorithms
| Algorithm          | Time Complexity | Auxiliary Space | Description                                                                             |
| ------------------ | --------------- | --------------- | --------------------------------------------------------------------------------------- |
| [[Counting Sort ]] | `O(n+k)`        | `O(k)`          | Linear sorting algorithm which runtime depends on two different variables, `n` and `k`. |
