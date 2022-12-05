[[Bit Manipulation Questions (C)]]
Easy (12/02/2022)
Leet code link: https://leetcode.com/problems/counting-bits/
Notes: use dp 

# 338. Counting Bits
Given an integer n, return an array ans of length n + 1 such that for each i (0 <= i <= n), ans[i] is the number of 1's in the binary representation of i.

Example 1:
Input: n = 2
Output: [0,1,1]
Explanation:
0 --> 0
1 --> 1
2 --> 10
Example 2:

Input: n = 5
Output: [0,1,1,2,1,2]
Explanation:
0 --> 0
1 --> 1
2 --> 10
3 --> 11
4 --> 100


# Solution 1 ()
    def countBits(self, n: int) -> List[int]:
        dp: list = [0] * (n + 1)
        offset: int = 1

        for n in range(1, n+1):
            if (offset * 2) == n:
                offset = n  
            dp[n] = 1 + dp[n - offset]
        return dp

