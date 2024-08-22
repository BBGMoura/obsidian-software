1. What is a queue?
A queue is a linear data structure which follows the FIFO principle. Where elements are added at the rear(enqueue) and removed from the front (dequeue).

2. What are different types of queues?
- Simple/linear queue
- circular queue -> last position is connect tot eh first position to make a circle
- priority queue -> elements assigned priority and dequeued based on that
- double ended queue -> insertion and deletion on both ends

3. How is a queue implemented in an array?
Use two pointers, one for rear one for tail. front points to the first element and rear points to the next available position.

4. How is a queue implemented in a linked list?
Creating a node for each element and maintaining a head and tail pointer. Enqueueing adds a node to the tail and dequeueing removes a node from the head.

5. Time complexity for enqueue and dequeue?
O(1)
O(1) for simple and circular, O(n) for priority

6. What is the difference between a queue and a stack?
queue is FIFO and stack is LIFO

7. What are applications of a queue?
- task scheduling
- message passing
- simulation of real word scenarios

8. how do you handle overflow and underflow conditions in a queue?
- overflow -> when queue is full, throw exception or return error code
- underflow -> when queue is empty, throw exception or return a null value

9. What is a circular queue?
rear pointer wraps around to the beginning of the array after reaching the end

10. what is a priority queue?
Queue is dequeued in order of priority 

11. how is priority queue implemented?
using binary heap or self-balancing binary search tree

12. what is double ended queue?
can be queued or dequeued from tail or head.

13. how is a deque implemented?
Using two stacks or circular buffer

14. advantages of a queue?
- simple & efficient FIFO
- easy to enqueue and dequeue elements
- supports multiple producers and consumers

15. disadvantages?
- limited access from head or tail
- inefficient if elements need to be accessed in a non-sequential order

