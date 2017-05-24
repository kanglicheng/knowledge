In a typical breadth first search (BFS) algorithm, a simple queue works great for keeping track of what states have been visited. Since each new state is one more operational step than the current state, adding new locations to the end of the queue is sufficient to insure that the quickest path is found first. However, the assumption here is that each operation from one state to the next is a single step.

Let us consider another example where you are driving a car, and wish to get to your destination as quickly as possible. A typical problem statement might say that you can move one block up/down/left/right in one minute. In such a case, a simple queue-based BFS works perfectly, and is guaranteed to provide a correct result.

But what happens if we say that the car can move forward one block in two minute, but requires three minutes to make a turn and then move one block (in a direction different from how the car was originally facing)? Depending on what type of move operation we attempt, a new state is not simply one "step" from the current state, and the "in order" nature of a simple queue is lost.

This is where priority queues come in. Simply put, a priority queue accepts states, and internally stores them in a method such that it can quickly pull out the state that has the least cost. (Since, by the nature of a "shortest time/path" type of problem, we always want to explore the states of least cost first.) 

A real world example of a priority queue might be waiting to board an airplane. Individuals arriving at their gate earlier will tend to sit closest to the door, so that they can get in line as soon as they are called. However, those individuals with a "gold card", or who travel first class, will always be called first, regardless of when they actually arrived. 

One very simple implementation of a priority queue is just an array that searches (one by one) for the lowest cost state contained within, and appends new elements to the end. Such an implementation has a trivial time-complexity for insertions, but is painfully slow to pull objects out again. 

A special type of binary tree called a heap is typically used for priority queues. In a heap, the root node is always less than (or greater than, depending on how your value of "priority" is implemented) either of its children. Furthermore, this tree is a "complete tree" from the left. A very simple definition of a complete tree is one where no branch is n + 1 levels deep until all other branches are n levels deep. Furthermore, it is always the leftmost node(s) that are filled first. 

To extract a value from a heap, the root node (with the lowest cost or highest priority) is pulled. The deepest, rightmost leaf then becomes the new root node. If the new root node is larger than at at least one of its children, then the root is swapped with its smallest child, in order to maintain the property that the root is always less than its children. This continues downward as far as necessary. Adding a value to the heap is the reverse. The new value is added as the next leaf, and swapped upward as many times as necessary to maintain the heap property. 

A convenient property of trees that are complete from the left is that they can be stored very efficiently in a flat array. In general, element 0 of the array is the root, and elements 2k + 1 and 2k + 2 are the children of element k. The effect here is that adding the next leaf simply means appending to the array. 