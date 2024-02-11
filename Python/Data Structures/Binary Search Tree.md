(или корневое бинарное дерево)

Это корневые деревья со следующими двумя ограничениями:
- Все узлы, кроме корня, имеют родителя.
- Все узлы имеют 0, 1 или 2 дочерних элемента.
  
Eng:
In this data structure any given node is larger than all nodes in its left subtree and smaller than all nodes in its right subtree. BST can only store elements if there exists some way of comparing them: there must be some inherent order between elements.

A tree's hight is the longest distance from the root of the tree to a leaf, where we define "instance" in this case as  the number of edges (not nodes) in a path.
Worst-case time complexity of inserting, finding, and removing elements of a BST is proportional to the its height: in the tree-traversal step of any of the three aforementioned operations (i.e., traversing left or right to either find an element or to find the insertion site for a new element), we perform a constant-time comparison operation once for each level of the BST, so as the number of levels in a BST grows, the number of comparison operations we must perform grows proportionally.

BST are relatively efficient when they are balanced (logarithmic time), they become unbalanced fairly easily depending on the order in which the elements are inserted.

