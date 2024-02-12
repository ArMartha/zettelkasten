We visit nodes level-by-level (where root is the "first level", its children are the "second level", etc.) and on a given level, we visit nodes left-to-right.

Python code:

```python
def level_order(root):
    ans = []
    if not root:
        return ans
    level = [root]
    while level:
        current = []
        new_level = []
        for node in level:
            current.append(node.val)
            if node.left:
                new_level.append(node.left)
            if node.right:
                new_level.append(node.right)
        level = new_level
        ans.append(current)
    return ans
    ```
