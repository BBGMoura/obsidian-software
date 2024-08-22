1. What is a Linked List?
A linked list is a linear data structure consisting of a sequence of elements, where each element points to the next one, forming a chain.

2. What are the different types of linked lists?
Circular, singly and doubly linked list

3. Advantages of linked list:
- dynamic memory allocation so can be resized -> do not need to allocate a certain amount of memory beforehand. Allocates small blocks of memory for each node as you insert more elements
- efficient insertion and deletion -> dont need to shift, only need to change the pointers a few elements so O(1) time if you have the reference.
- can represent complex data structures -> build trees and graphs. one node can point to various nodes
- can be used to implement queues and stacks -> can implement a queue by maintaining pointers to the front and the rear of the list. can implement a stack by adding and removing elements from the head of the list
- can be used for memory management and caching -> can manage memory pools by frequently allocation and reallocation. can be used for caching algorithms  with doubly linked list  if need frequent updates or variable size
- can be used for garbage collection

4. Disadvantages of linked list:
- slow random access -> access to elements by index is needed bc u need to traverse the list from beginning
- more memory overhead -> need to store references (pointers)
- difficult to debug -> bc of node complexity 
- not cache-friendly -> can also be bad for caching because of their non contiguous memory allocation
- can suffer from memory leaks -> Improper management of pointers can lead to memory leaks in linked lists, where unused nodes are not properly deallocated.


5. what is a cycle/loop in a singly linked list 
A cycle/loop in a singly linked list, occurs when a node in the list points back to a previous node, creating a circular path. This usually occurs accidentally due to errors in list manipulation as there should be a null pointer in a singly linked list.

6. complexity of linked list operations?
**Insertion**: 
- beginning O(1)
- end O(n)
- specific position O(n)

**Deletion**
- beginning O(1)
- end O(n)
- specific position O(n)

**Search**: O(n)
**Traversal**: O(n)

7. How would you compare a Dynamic Arrays Vs Linked List?
Dynamic Array Advantages:
- Fast random access O(1)
- Efficient for large data sets
- contiguous memory allocation

Dynamic Array Disadvantages:
- slow insertion and deletion in middle O(n)
- Resizing overhead as it copies elements

Linked List Advantages:
- efficient insertion and deletion in middle
- can grow and shrink dynamically
- represent complex data structures

Linked List Disadvantages:
- slow random access O(n)
- more memory overhead due to pointers
- not cache friendly (not contiguous)


