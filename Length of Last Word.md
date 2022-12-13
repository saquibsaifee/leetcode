Type:[[Array & Hashing Questions (C)]]

Easy(12/12/2022)

LeetCode Link: https://leetcode.com/problems/length-of-last-word/description/

Notes: Reverse reversal

# 58. Length of Last Word

Given a string `s` consisting of words and spaces, return _the length of the **last** word in the string._

A **word** is a maximal 

substring

 consisting of non-space characters only.

**Example 1:**

**Input:** s = "Hello World"
**Output:** 5
**Explanation:** The last word is "World" with length 5.

**Example 2:**

**Input:** s = "   fly me   to   the moon  "
**Output:** 4
**Explanation:** The last word is "moon" with length 4.

**Example 3:**

**Input:** s = "luffy is still joyboy"
**Output:** 6
**Explanation:** The last word is "joyboy" with length 6.


# Solution 1:

	def lengthOfLastWord(self, s: str) -> int:
	
		s = s.split()
	
		return(len(s[-1]))


# Solution 2:

	def lengthOfLastWord(self, s: str) -> int:
		counter = 0
	
		for i in range(len(s)-1, -1, -1):
			if s[i] != ' ':
				counter += 1
			elif counter:
				return counter
		return counter