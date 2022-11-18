[[Stack (C)]]
# 20. Valid Parentheses
Given a string `s` containing just the characters `'('`, `')'`, `'{'`, `'}'`, `'['` and `']'`, determine if the input string is valid.

An input string is valid if:
1.  Open brackets must be closed by the same type of brackets.
2.  Open brackets must be closed in the correct order.
3.  Every close bracket has a corresponding open bracket of the same type.

**Example 1:**
**Input:** s = "()"
**Output:** true

**Example 2:**
**Input:** s = "()[]{}"
**Output:** true

**Example 3:**
**Input:** s = "(]"
**Output:** false

# Solution:
	def isValid(self, s: str) -> bool:
        Hashmap = {")": "(", "]": "[", "}": "{"}
        stack = []

        for c in s:
            if c not in Hashmap:
                stack.append(c)
                continue
            if not stack or stack[-1] != Hashmap[c]:
                return False
            stack.pop()

        return not stack