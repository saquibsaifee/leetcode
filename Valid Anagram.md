[[Array & Hashing Questions (C)]]

# **Intuition**
Both string will have same number of alphabets, right?

# **Approach**
1: Use the counter and compare both strings?

2: Sort both strings and compare them?

3: Build a HashMap and count the occurrence of the strings and lastly compare them?

use hashmap.get(s[i], 0) to avoid any error.
HashMap will give error if the value we are asking for doesn't exist, but using it will make that key with 0 value.

# **Complexity**

Time: O(n) as we are only traversing through the string once.
Space: O(n) as we are taking additional space by adding all the elements in the HashMap.

## Solution 1 # 
	return sorted(s) == sorted(t) 

## Solution 2 # 
	return (Counter(s) == Counter(t)) 

# Solution 3 
	if len(s) != len(t): 
		return False 
		
	HashMapS = {} 
	HashMapT = {} 
	
	for i in range(len(s)): 
		HashMapS[s[i]] = 1 + HashMapS.get(s[i], 0) 
		HashMapT[t[i]] = 1 + HashMapT.get(t[i], 0) 
		
	return HashMapS == HashMapT