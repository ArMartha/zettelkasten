Skip List is effectively the same as a Linked List, except every node in the Skip List has multiple layers, where each layer of a node is a forward pointers.
Height - number of layers a node reaches.
Elements in Skip List must be sorted, because it's property will let us perform a find algorithm that is functionally similar to binary search.
SkipList mimicked some properties from ArrayList
Optimally-distributed Skip List - each "jump" allows to traverse half of the remainder of the list.
Distribution of heights has a significant impact on the performance of a Skip List.

Like [[Linked List]] this structure has a head which has multiple layers.

Finding an element - O(N) - the worst-case time, O(logN) - for optimally-distributed Skip List - average-case
Remove an element - O(N) - the worst-case time, O(logN) - for optimally-distributed Skip List
Inserting an element  - O(N) - the worst-case time, 
O(logN) - for optimally-distributed Skip List
