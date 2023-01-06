[[Tree Questions (C)]] 

Easy (11/21/2022)

Leet code link: https://leetcode.com/problems/invert-binary-tree/submissions/

Notes: Recursion, Swap left to right

# 226. Invert Binary Tree
Given the `root` of a binary tree, invert the tree, and return _its root_.

**Example 1:**

![](https://assets.leetcode.com/uploads/2021/03/14/invert1-tree.jpg)

**Input:** root = [4,2,7,1,3,6,9]
**Output:** [4,7,2,9,6,3,1]

**Example 2:**

![](https://assets.leetcode.com/uploads/2021/03/14/invert2-tree.jpg)

**Input:** root = [2,1,3]
**Output:** [2,3,1]

**Example 3:**
**Input:** root = []
**Output:** []

# Solution 1 (BFS, iteration)

```python
    def invertTree(self, root: Optional[TreeNode]) -> Optional[TreeNode]:   
        if not root: return None

        queue = collections.deque([root])

        while queue:
            curr = queue.popleft()
            curr.left, curr.right = curr.right, curr.left

            if curr.left: queue.append(curr.left)
            if curr.right: queue.append(curr.right)

        return root
```


# Solution 2 (recursive)

```python
	def invertTree(self, root: Optional[TreeNode]) -> Optional[TreeNode]:
        #base case
        if not root:
            return None
        
        #swapping left to right and right to left
        left = root.left
        root.left = root.right
        root.right = left

        #recrusivly calling the swapping function
        self.invertTree(root.left)
        self.invertTree(root.right)

        #returning the new root after swapping
        return root
