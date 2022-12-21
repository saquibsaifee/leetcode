Type: [[Array & Hashing Questions (C)]]

Medium(12/20/2022)

LeetCode Link: https://leetcode.com/problems/maximum-subarray/description/

Notes: use -1e8 in maxsum. keep adding num in currsum, if neg then max currsum 0. compare curr and max sum.

# 53. Maximum Subarray

Given an integer array `nums`, find the 

subarray

 which has the largest sum and return _its sum_.

**Example 1:**

**Input:** nums = [-2,1,-3,4,-1,2,1,-5,4]
**Output:** 6
**Explanation:** [4,-1,2,1] has the largest sum = 6.

**Example 2:**

**Input:** nums = [1]
**Output:** 1

**Example 3:**

**Input:** nums = [5,4,-1,7,8]
**Output:** 23


# Solution 1:
```python
    def maxSubArray(self, nums: List[int]) -> int:
        if len(nums) == 1: return nums[0]
        
        currsum, maxsum = 0, -1e8
        
        for i in range(len(nums)):
            currsum += nums[i]
            if currsum > maxsum: maxsum = currsum
            if currsum < 0: currsum = 0
        return maxsum
```
