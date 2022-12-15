Type: [[Array & Hashing Questions (C)]]

Easy(12/14/2022)

LeetCode Link: https://leetcode.com/problems/longest-common-prefix/description/

Notes: put in rows and check from right to left in all.

# 14. Longest Common Prefix

Write a function to find the longest common prefix string amongst an array of strings.

If there is no common prefix, return an empty string `""`.

**Example 1:**

**Input:** strs = ["flower","flow","flight"]
**Output:** "fl"

**Example 2:**

**Input:** strs = ["dog","racecar","car"]
**Output:** ""
**Explanation:** There is no common prefix among the input strings.


# Solution 1:

	    def longestCommonPrefix(self, strs: List[str]) -> str:
	        result = ''
	
	        for i in range(len(strs[0])):
	            for s in strs:
	                if i == len(s) or s[i] != strs[0][i]:
	                    return result
	            result += s[i]
	        
	        return result



