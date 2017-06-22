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
