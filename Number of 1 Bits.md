Type: [[Bit Manipulation Questions (C)]]

Easy (11/30/2022)

Leet code link: https://leetcode.com/problems/number-of-1-bits/description/

Notes: mod % 2 of 1 and 0 will give the same number.
`>>` shifts the bit to the left and so does `//` by 2.
(n-1) remove 1 and & compliment will make it zero.

# 191. Number of 1 Bits
Write a function that takes an unsigned integer and returns the number of '1' bits it has (also known as the Hamming weight).
 
Example 1:
Input: n = 00000000000000000000000000001011
Output: 3
Explanation: The input binary string 00000000000000000000000000001011 has a total of three '1' bits.

Example 2:
Input: n = 00000000000000000000000010000000
Output: 1
Explanation: The input binary string 00000000000000000000000010000000 has a total of one '1' bit.

Example 3:
Input: n = 11111111111111111111111111111101
Output: 31
Explanation: The input binary string 11111111111111111111111111111101 has a total of thirty one '1' bits.

# Solution 1 (mod 2):
 ```python
	def hammingWeight(self, n: int) -> int:
        count = 0
        while n:
            count += n % 2
            n = n >> 1
        return count
```

# Solution 2 (&   by n-1):

```python
	def hammingWeight(self, n: int) -> int:
        res = 0
        while n:
            n &= n - 1
            res += 1
	        return res
``` 
