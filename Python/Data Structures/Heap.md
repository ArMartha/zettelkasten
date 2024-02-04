Куча - это дерево, удовлетворяющее _свойству кучи_ -  для любых двух узлов **A** и **B**, если узел **A** является узлом-предком для узла **B**, то узел **A** имеет более высокий (или равный) приоритет, чем узел **B**.

Есть макси-куча и мини-куча.

A **min-heap** is a heap where every node is _**smaller**_ than (or equal to) all of its children (or has no children). In other words, a node _A_ is said to have _higher priority_ than a node _B_ if _A_ < _B_ (i.e., when comparing two nodes, the _smaller_ of the two has higher priority).

A **max-heap** is a heap where every node is **_larger_** than (or equal to) all of its children (or has no children). In other words, a node _A_ is said to have _higher priority_ than a node _B_ if _A_ > _B_ (i.e., when comparing two nodes, the _larger_ of the two has higher priority).

Heap is guaranteed that any given element has higher (or equal) priority than all of its children. Any given element must also have a higher priority than all of its descendants, not just its direct children. And the root, which is the ancestor of all other elements in the tree, must be the highest-priority element in the heap.

Heap can be represented as array. In this case, we can access the parent, left child or right child of any given element in constant time using simple arithmetic. For an element at index _i_ of the array:
parent is at index  *i-1/2*
left child - 2*i +1*
right child - 2*i +2*
