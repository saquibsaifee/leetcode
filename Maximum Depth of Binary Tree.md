[[Tree Questions (C)]] 
Easy (11/23/2022)
Leet code link: https://leetcode.com/problems/maximum-depth-of-binary-tree/

# 104. Maximum Depth of Binary Tree

Given the `root` of a binary tree, return _its maximum depth_.

A binary tree's **maximum depth** is the number of nodes along the longest path from the root node down to the farthest leaf node.

**Example 1:**

![](https://assets.leetcode.com/uploads/2020/11/26/tmp-tree.jpg)

**Input:** root = [3,9,20,null,null,15,7]
**Output:** 3

**Example 2:**

**Input:** root = [1,null,2]
**Output:** 2

# Solution 1 (recursive DFS)
    def maxDepth(self, root: Optional[TreeNode]) -> int:
        if not root:
            return 0
        return (1 + max(self.maxDepth(root.left), self.maxDepth(root.right)))

# Solution 2 (iterative DFS)
    def maxDepth(self, root: Optional[TreeNode]) -> int:
        stack = [[root, 1]]
        res = 0
        while stack:
            node, depth = stack.pop()
            if node:
                res = max(res, depth)
                stack.append([node.left, depth + 1])
                stack.append([node.right, depth + 1])
        return res

# Solution 3 (iterative BFS)
    def maxDepth(self, root: Optional[TreeNode]) -> int:
        if not root:
            return 0
        queue = collections.deque([root])
        counter = 0
        while queue:
            for i in range(len(queue)):
                curr = queue.popleft()
                if curr.left:
                    queue.append(curr.left)
                if curr.right:
                    queue.append(curr.right)
            counter += 1
        return counter


