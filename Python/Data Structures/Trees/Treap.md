Type of [[Data Structures/Trees/Binary Search Tree]]
Binary tree in which nodes contain two items, *a key* and *a priority*, and which must obey the following restrictions:
1. The tree must follow the [[Data Structures/Trees/Binary Search Tree]] properties with respect to its key
2. The tree must follow the *Heap Property* with respect to its priorities
Given a set of (key, priority) you can construct valid Treap containing the given pairs:
- Start with an empty BST
- Insert the (key, priority) pairs in decreasing order of priority, using the regular BST insertion algorithm with respect to the keys
- The resulting BST is a Treap: the BST ordering of he keys is enforced by the BST insertion algorithm, and the Heap Property of the priorities is enforced by inserting pairs in descending order of priorities
Algorithm to find a key in a Treap is completely indentical to the "find" algorithm of a typical BST: start at the root node, and then traverse left or right down the tree until you either find the desired element.