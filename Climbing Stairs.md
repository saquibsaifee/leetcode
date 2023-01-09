Type: [[Dynamic Programming Questions (C)]]

Easy (11/30/2022)

Leet code link: https://leetcode.com/problems/climbing-stairs/description/

Notes: 1-D Dynamic programming. (Fibonacci series)

# 70. Climbing Stairs

You are climbing a staircase. It takes `n` steps to reach the top.
Each time you can either climb `1` or `2` steps. In how many distinct ways can you climb to the top?

**Example 1:**
**Input:** n = 2
**Output:** 2
**Explanation:** There are two ways to climb to the top.
1. 1 step + 1 step
2. 2 steps

**Example 2:**
**Input:** n = 3
**Output:** 3
**Explanation:** There are three ways to climb to the top.
1. 1 step + 1 step + 1 step
2. 1 step + 2 steps
3. 2 steps + 1 step

# Solution 1:

```python
  def climbStairs(self, n: int) -> int:
	x, y = 1, 1
	for i in range(n-1):
		temp = x
		x += y
		y = temp
	return x
```


# Solution 2:

```python
  def climbStairs(self, n: int) -> int:
	if n <= 3: return n
	n1, n2 = 2, 3
	for i in range(4, n + 1):
		temp = n1 + n2
		n1 = n2
		n2 = temp
	return n2
``` 
 



