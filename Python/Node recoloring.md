The most trivial case: if the tree is empty, insert the new node as the root and color it **black**

If the tree is not empty, insert the new node via the [[Binary Search Tree]] insertion algorithm, and color the new node **red**. While you're performing the **[[Binary Search Tree]]** insertion algorithm, if you run into a **black** node with two **red** children, recolor all three, and if the parent was the root, recolor it back to **black** (note that we may need to perform an [[AVL rotation]] to fix the tree if this recoloring results in a **red** node with a **red** child)

If the newly-inserted node is the child of a **black** node, we are done

If the new node is the child of a **red** node, if the nodes are in a **straight line**, perform a **single rotation** and a **recoloring**

If the new node is the child of a **red** node, if the nodes are in a **kink**, perform a **single rotation** to transform them into a **straight line**, and then perform the **straight line** method above