Type: [[Tree Questions (C)]]

Easy(01/07/2023)

LeetCode Link:  https://leetcode.com/problems/balanced-binary-tree/

Notes: bit complex. dfs with height. similar to diameter of binary tree.

# 110. Balanced Binary Tree

Given a binary tree, determine if it is 
**height-balanced**

**Example 1:**

![](https://assets.leetcode.com/uploads/2020/10/06/balance_1.jpg)

**Input:** root = [3,9,20,null,null,15,7]
**Output:** true

**Example 2:**

![](https://assets.leetcode.com/uploads/2020/10/06/balance_2.jpg)

**Input:** root = [1,2,2,3,3,null,null,4,4]
**Output:** false

**Example 3:**

**Input:** root = []
**Output:** true


# Solution :

```python
    def isBalanced(self, root: Optional[TreeNode]) -> bool:

        def dfs(root):
            if not root: return[True, 0]

            left = dfs(root.left)
            right = dfs(root.right)
            balanced = left[0] and right[0] and abs(left[1] - right[1]) <= 1

            return [balanced, 1 + max(left[1], right[1])]
        
        return dfs(root)[0]
```