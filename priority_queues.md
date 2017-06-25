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

## Implementation
Under the hood, the heap is stored as an array.
1. Peek will look at the element in the first index -> store[0]
2. Insert -> We'll push on an element and look at that elements parent to see if it should be swapped.  This process will continue until the item above it is less than or equal to it
3. Extract -> We'll swap the min element with whatever is in the last node.  We then heapify down until that swapped element is in the correct place.
-> Formula
1. Given parent index, its children are located at 2i+1 and 2i+2


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


## Heapsort
-> A relatively common sort -> quicksort or mergesort
1. Our input is an array
-> The input does not effect the runtime
2. We add each element to the heap and heapify up
-> For each element that we insert, we'll look at its parents to see if it's in the correct position
-> In the resulting heap, we know that our extract function will always return the smallest element
-> Every time we extract, we need to heapify again
-> To turn this heap into a sorted heap, we'll extract every element from the heap and insert it into a new array
->Heapsort can be done in place to reduce space complexity


## Heapsort with constant space
1. Heapify left to right
2. Extract right to left
We'll make use of the fact that under the hood, the heap is just an array.
-> Useful to think of there being an artificial line that delineates the array in half
-> Whatever is to the left of the line is part of the heap
-> Move the boundary one step
-> Works more elegantly if we use a max heap instead of a min heap
1. The parents need to be larger than its children
-> Each time we're adding one more element to the heap and checking to see if we need to heapify that element

Once the artificial line reaches the end of the array and all of the appropriate heapifies take place. we'll have a valid heap.  At this point, we'll start from the right and go to the left.
1. We'll do a standard extract
-> We swap the first and last element and move the barrier over one
1. We move the barrier over by one because the child checker needs to stop when it reaches this line so it doesn't start swapping with elements that are already sorted

Mergesort is also O(nlogn), but it is not an in place sort
