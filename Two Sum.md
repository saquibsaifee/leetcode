[[Array & Hashing Questions (C)]]
# **Intuition**
1. we can translate our problem into this equation, right? 
	a + b = c 
	FirstElement + SecondElement = target.
	Lets change it to:
	c - a = b
	target - FirstElement = SecondElement
	Initialize the HashMap and store the SecondElement by using above formula and check if the current value in the loop is in the HashMap already. 
	If exist than we got our a and b = target. If not the add the b in the HashMap linked to the a.

2. Sort the list and have two pointers
	one on the first going toward the end, pointer i
	second on the last element coming towards the first, pointer j
	Compare if first and last element is equal to the target, if greater than the decrease the pointer by 1
	if smaller then increase the pointer i by 1

# Solution:
	hashmap = dict()
	for i in range(len(nums)):
		if nums[i] in hashmap:
			return [hashmap[nums[i]], i]
		else:
			hashmap[target - nums[i]] = i
	return False

	```python
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        C = target
        hashmap = dict()
        for index, A in enumerate(nums):
            B = C - A
            if B in hashmap:
                return [index, hashmap[B]]
            hashmap[A] = index
```
