hashmap = dict()
for i in range(len(nums)):
	if nums[i] in hashmap:
		return [hashmap[nums[i]], i]
	else:
		hashmap[target - nums[i]] = i
return False