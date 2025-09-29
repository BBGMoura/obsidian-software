Iterator is a design pattern that lets you traverse  elements of a collection without exposing its underlying representation (list, stack tree, etc)

## Problem

## Solution
The main idea of the iterator pattern is to extract the traversal behaviour of a collection into separate object called iterator.![[Pasted image 20240916182447.png]]

In addition to implementing the algorithm itself, an iterator object encapsulates all of the traversal details, such as current position and how many elements are left till the end. 

