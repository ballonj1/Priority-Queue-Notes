## Priority Queues
Ex. Computer is capable of running multiple applications at the same time.  The effect is typically achieved by assigning a priority to events associated with the application.  Cellphones are likely to process an incoming call over a particular app.  The priority queue should provide the functionality to remove the maximum and insert.

Uses
1. Can be used as the basis of a sorting algorithm by inserting a sequence of items and then removing the smallest item one by one.
2. Building block for other algorithms.

API
1. Remove the max/min
2. Insert
3. Constructor
4. Compare

## Elementary implementations
1. We can use an array or linked list (ordered or unordered)
-> Unordered sequences -> Prototypical lazy approach to this problem, where we defer doing the work until necessary
-> Ordered sequences -> Prototypical lazy approach to this problem, where we do as much work as we can upfront, keeping the sequence ordered so later operations are more efficient
The heap data structure helps us create implementations of priority queues that can remove the min/max and insert quickly


## Understanding Heaps
Three public methods
1. Peek
-> Will return whatever the current minimum item in the heap is.
-> If they are integers, it will show us what the smallest integer is.
-> Done in constant time.

2. Insert
-> Will put in the appropriate place in the heap.
-> Better than linear time.
-> We will swap the inserted node until it obeys the heap property (Heapify up)
-> At most you will swap the number of levels in the heap
-> O(logn)

3. Extract
-> Similar to pop - You remove the minimum value in the data structure and removes it
-> In order for the completeness property to remain true, we should remove the bottom-most and right-most thing
-> We should swap the node at the top of the heap with the item in the bottom-most right-most position and then reorder
-> The swapped item should loop at its children and heapify down until it is in the correct position


-> A heap is a binary tree that follows a certain set of constraints

1. Root node will have at least 2 children
Full binary tree -> every node (except for the last row) has two children

We care about completeness when we're working with heaps
1. We fill in nodes from top to bottom and left to right.
2. A complete tree cannot have any gaps
3. A heap must be a complete tree.
For each node, its parent must be less than or equal to it.
-> Each node must obey the heap property
1. The node must be greater than or equal to its parent
