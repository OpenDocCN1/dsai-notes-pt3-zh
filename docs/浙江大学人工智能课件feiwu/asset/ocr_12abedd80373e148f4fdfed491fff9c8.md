# # Infrastructure for search algorithms

Now that we have nodes, we need somewhere to put them. The frontier needs to be
stored in such a way that the search algorithm can easily choose the next node to expand
according to its preferred strategy. The appropriate data structure for this is a **queue**. The
operations on a queue are as follows:

+   - EMPTY?(queue) returns true only if there are no more elements in the queue.
+   - Pop(queue) removes the first element of the queue and returns it.
+   - INSERT(element, queue) inserts an element and returns the resulting queue.

Queues are characterized by the **order** in which they store the inserted nodes. Three common
variants are the first-in, first-out or **FIFO queue**, which pops the _oldest_ element of the queue;
the last-in, first-out or **LIFO queue** (also known as a **stack**), which pops the _newest_ element
of the queue; and the **priority queue**, which pops the element of the queue with the highest
priority according to some ordering function.

The explored set can be implemented with a hash table to allow efficient checking for
repeated states. With a good implementation, insertion and lookup can be done in roughly
constant time no matter how many states are stored. One must take care to implement the
hash table with the right notion of equality between states. For example, in the traveling
salesperson problem (page 74), the hash table needs to know that the set of visited cities
{Bucharest,Urziceni,Vaslui} is the same as {Urziceni,Vaslui,Bucharest}. Sometimes this can
be achieved most easily by insisting that the data structures for states be in some **canonical
form**; that is, logically equivalent states should map to the same data structure. In the case
of states described by sets, for example, a bit-vector representation or a sorted list without
repetition would be canonical, whereas an unsorted list would not.