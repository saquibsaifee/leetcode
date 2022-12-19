Type: [[Array & Hashing Questions (C)]]

Easy(12/17/2022)

LeetCode Link: https://leetcode.com/problems/add-strings/description/

Notes: Make Dictionary and helper function to convert str into int.

# 415. Add Strings

Given two non-negative integers, `num1` and `num2` represented as string, return _the sum of_ `num1` _and_ `num2` _as a string_.

You must solve the problem without using any built-in library for handling large integers (such as `BigInteger`). You must also not convert the inputs to integers directly.

**Example 1:**

**Input:** num1 = "11", num2 = "123"
**Output:** "134"

**Example 2:**

**Input:** num1 = "456", num2 = "77"
**Output:** "533"

**Example 3:**

**Input:** num1 = "0", num2 = "0"
**Output:** "0"


# Solution 1:

    def addStrings(self, num1: str, num2: str) -> str:
        hashmap = {'0' : 0, '1' : 1, '2' : 2, '3' : 3, '4' : 4, '5' : 5, '6' : 6, '7' : 7, '8' : 8, '9' : 9}

  
        def addNumbers(strings: str, dictionary=hashmap) -> int:
            output = int()
            for i in strings:
                output = output * 10 + hashmap[i]
            return output

        return str((addNumbers(num1))+(addNumbers(num2)))


# Solution 2: using ord()

    def addStrings(self, num1: str, num2: str) -> str:

        def addNumbers(strings: str) -> int:
            output = 0
            for i in strings:
                output = output * 10 + ord(i) - ord('0')
            return output


        return str((addNumbers(num1))+(addNumbers(num2)))