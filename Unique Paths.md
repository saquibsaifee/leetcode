Type: [[Dynamic Programming Questions (C)]]

Medium (01/14/2023)

LeetCode Link: https://leetcode.com/problems/unique-paths/description/

Notes: matrix traversing and using DP

# 62. Unique Paths

There is a robot on an `m x n` grid. The robot is initially located at the **top-left corner** (i.e., `grid[0][0]`). The robot tries to move to the **bottom-right corner** (i.e., `grid[m - 1][n - 1]`). The robot can only move either down or right at any point in time.

Given the two integers `m` and `n`, return _the number of possible unique paths that the robot can take to reach the bottom-right corner_.

The test cases are generated so that the answer will be less than or equal to `2 * 109`.

**Example 1:**

![](https://assets.leetcode.com/uploads/2018/10/22/robot_maze.png)

**Input:** m = 3, n = 7
**Output:** 28

**Example 2:**

**Input:** m = 3, n = 2
**Output:** 3
**Explanation:** From the top-left corner, there are a total of 3 ways to reach the bottom-right corner:
1. Right -> Down -> Down
2. Down -> Down -> Right
3. Down -> Right -> Down


# Solution 1 [O(mn) space]:

```python
    def uniquePaths(self, m: int, n: int) -> int:
        if m == n == 1: return 1
        
        matrix = [[1 for _ in range(n)] for _ in range(m)]

        for row in range(1, m):
            for col in range(1, n):
                matrix[row][col] = matrix[row-1][col] + matrix[row][col-1]

        return (matrix[m-1][n-1])
```



# Solution 2 [O(n) space]:

Approach: 
1. create a row with 1 (this will be the last row initially) 
2. create new row with 1 (this will be the 2nd last row initially)
3. traverse the matrix in reverse starting from 2nd last row and 2nd last col.
4. value of curr will be right + down.

```python
    def uniquePaths(self, m: int, n: int) -> int:
        if m == n == 1: return 1

        row = [1] * n 

        for i in range(m - 1):
            newRow = [1] * n
            for col in range(n -2, -1, -1):
                newRow[col] = newRow[col + 1] + row[col] 
            row = newRow
        return row[0]
```
