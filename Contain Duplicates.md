# **Intuition**
Intuition 1:
What if we remove duplicates and then compare the later one with original?
If the length is same it means there is no repetition, Right?
If not then it contains the repetition.

Intuition 2:
What if we iterate over the list and store them 1 by 1 and checking if they are already in the new storage. If they are there that means a duplicate.

# **Approach**
1:
Remove the duplicates from the list and than compare it with the original list.
Easy way to remove duplicates is converting it into the sets.

2:
Make a hash set
Iterate over the list and see if the value is already in the hash set, if it is there than return True implying there is duplicate.
If not, add the element in hash set and iterate to next element.

# **Code**

**1st approach
One liner:**

return(len(nums)!=len(set(nums)))

**2nd approach:**

	hashset = set()
        for i in nums:
            if i in hashset:
                return True
            else:
                hashset.add(i)
        return False

# **Complexity**

2nd Approach:

Time: O(n) for iterating over the list once in worst case.
Space: O(n) for adding all the values in the hash set.