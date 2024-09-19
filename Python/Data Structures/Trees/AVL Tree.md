Adelson-Velsky-Landis tree/
Revolutionary self-balancing tree that achieves a worst-case time complexity of **O(log _n_)**.

An **AVL Tree** is a **[[Data Structures/Trees/Binary Search Tree|Binary Search Tree]]** in which, for all nodes in the tree, the _heights_ of the two child subtrees of the node differ by at most one. If, at any time, the two subtree heights differ by more than one, rebalancing is done to restore this property.
- The **balance factor** of a node _u_ is equal to the height of _u_'s right subtree minus the height of _u_'s left subtree
- A **[[Data Structures/Trees/Binary Search Tree|Binary Search Tree]]** is an **AVL Tree** if, for all nodes _u_ in the tree, the balance factor of _u_ is either -1, 0, or 1
The worst-case time complexity for finding, inserting, or removing an element is O(log _n_) because the height of the tree is at worst O(log _n_).
**AVL Tree** required to make two passes through the tree for inserting or removing elements: one pass down the tree to actually perform the insertion or removal, and then another pass up the tree to maintain the tree's balance