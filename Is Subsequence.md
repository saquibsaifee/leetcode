Type: [[Two Pointers Questions (C)]]
Easy(12/11/2022)
Leetcode link: https://leetcode.com/problems/is-subsequence/description/
Notes: 2 pointers

# 392. Is Subsequence

Given two strings `s` and `t`, return `true` _if_ `s` _is a **subsequence** of_ `t`_, or_ `false` _otherwise_.

A **subsequence** of a string is a new string that is formed from the original string by deleting some (can be none) of the characters without disturbing the relative positions of the remaining characters. (i.e., `"ace"` is a subsequence of `"abcde"` while `"aec"` is not).

**Example 1:**

**Input:** s = "abc", t = "ahbgdc"
**Output:** true

**Example 2:**

**Input:** s = "axc", t = "ahbgdc"
**Output:** false


# Solution:
	def isSubsequence(self, s: str, t: str) -> bool:
	        pointer1, pointer2 = 0, 0
	        
	        while pointer1 < len(s) and pointer2 < len(t):
	            if s[pointer1] == t[pointer2]:
	                pointer1 += 1
	            pointer2 += 1
	            
	        return pointer1 == len(s)