class Solution: 
def isAnagram(self, s: str, t: str) -> bool: 

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