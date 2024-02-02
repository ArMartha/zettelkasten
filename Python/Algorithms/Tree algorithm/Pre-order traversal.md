
Visit the current node, then we recurse on the left child (if one exists), and the we recurse on the right child (if one exists). Put simply VLR (visit-left-right)

Python code:

```python
class Solution:
    def preorderTraversal(self, root: Optional[TreeNode]) -> List[int]:
        val = []
        def inorder_traversal(root, val):
            if root:
                val.append(root.val)
                inorder_traversal(root.left, val)
                inorder_traversal(root.right, val)
        inorder_traversal(root, val)
        return val
```