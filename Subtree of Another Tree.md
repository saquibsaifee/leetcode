Type: [[Tree Questions (C)]] 

Easy (11/28/2022)

Leet code link: https://leetcode.com/problems/subtree-of-another-tree/description/

Notes: Base cases are imp in DFS recursion. use isSimilar helper function.

# 572. Subtree of Another Tree

Given the roots of two binary trees `root` and `subRoot`, return `true` if there is a subtree of `root` with the same structure and node values of `subRoot` and `false` otherwise.

A subtree of a binary tree `tree` is a tree that consists of a node in `tree` and all of this node's descendants. The tree `tree` could also be considered as a subtree of itself.

**Example 1:**

![](https://assets.leetcode.com/uploads/2021/04/28/subtree1-tree.jpg)

**Input:** root = [3,4,5,1,2], subRoot = [4,1,2]
**Output:** true

**Example 2:**

![](https://assets.leetcode.com/uploads/2021/04/28/subtree2-tree.jpg)

**Input:** root = [3,4,5,1,2,null,null,null,null,0], subRoot = [4,1,2]
**Output:** false


# Solution 1 (DFS Recursion)

```python
    def isSubtree(self, root: Optional[TreeNode], subRoot: Optional[TreeNode]) -> bool:
        if not subRoot: return True
        if not root: return False

        if self.isSimilar(root, subRoot): return True

        return (self.isSubtree(root.left, subRoot) or
               self.isSubtree(root.right, subRoot))
                
    def isSimilar(self, root, subRoot):
        if not root and not subRoot: return True
        if root and subRoot and root.val == subRoot.val:
            return (self.isSimilar(root.left, subRoot.left) and 
                    self.isSimilar(root.right, subRoot.right))
        return False
```



