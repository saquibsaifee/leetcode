[[Tree Questions (C)]] 
Easy (12/03/2022)
Leet code link: https://leetcode.com/problems/missing-number/
Notes:  

# 268. Missing Number
Given an array `nums` containing `n` distinct numbers in the range `[0, n]`, return _the only number in the range that is missing from the array._

**Example 1:**
**Input:** nums = [3,0,1]
**Output:** 2
**Explanation:** n = 3 since there are 3 numbers, so all numbers are in the range [0,3]. 2 is the missing number in the range since it does not appear in nums.

**Example 2:**
**Input:** nums = [0,1]
**Output:** 2
**Explanation:** n = 2 since there are 2 numbers, so all numbers are in the range [0,2]. 2 is the missing number in the range since it does not appear in nums.

**Example 3:**
**Input:** nums = [9,6,4,2,3,5,7,0,1]
**Output:** 8
**Explanation:** n = 9 since there are 9 numbers, so all numbers are in the range [0,9]. 8 is the missing number in the range since it does not appear in nums.

# Solution 1:
    def missingNumber(self, nums: List[int]) -> int:
        temp = [x for x in range(len(nums)+1)]
        return sum(temp) - sum(nums)

# Solution 2:
    def missingNumber(self, nums: List[int]) -> int:
        total = sum(range(1, len(nums)+1))
        curr_sum = sum(nums) 
        return(total-curr_sum)

# Solution 3:
    def missingNumber(self, nums: List[int]) -> int:
        res = len(nums)
        
        for i in range(len(nums)):
            res += i - nums[i]
        return res



