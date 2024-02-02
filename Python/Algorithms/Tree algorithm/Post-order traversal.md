We first recurse on the left child (if one exists), then we recurse on the right child (if one exists), and then we visit the current node. Put simply LRV (left-right-visit)

Python code:
```python
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def postorderTraversal(self, root: Optional[TreeNode]) -> List[int]:
        val = []
        def inorder_traversal(root, val):
            if root:
                inorder_traversal(root.left, val)
                inorder_traversal(root.right, val)
                val.append(root.val)
        inorder_traversal(root, val)
        return val
```