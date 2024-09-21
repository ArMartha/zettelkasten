A **2-3-4 tree**  (or 2-4 tree) is a self-balancing tree. The number represents the number of children each node can have. Any internal node can have either **two, three, or four** child nodes. 
 It is a [[B-Tree]] of degree four and all leaf nodes at the same level
 ## **Properties of a 2-4 Tree:**

- A **2-node** has one data element and if it is an internal node, then it has two child nodes.
- A **3-node** has two data elements and if this is an internal node, it has three child nodes.
- A **4-node** has three data elements and if it is an internal node, it has four child nodes.
- The elements in each node **should be sorted from smallest to greatest**.
- 2-3-4 tree is a perfectly balanced tree i.e., in this all leaf nodes are at the same level.
- The type of any node is decided based on the structure of the tree (the structure gets decided such that the tree is always a perfectly balanced tree).
- 
There are three basic operations that are performed in a 2-4 tree. The operations are:

- Insertion of a node
- Searching a value
- Deletion of a node