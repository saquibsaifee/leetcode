
Solution 1:
    def isPalindrome(self, s: str) -> bool:
        s = s.strip()
        s = s.split()
        s = "".join(s).lower()
        t = ""
        for i in s:
            if i.isalnum():
                t += "".join(i)
        
        j = len(t)-1
        for i in range(len(t)):
            if t[i] != t[j]:
                return False
            j -= 1
        return True

Solution 2:
	def isPalindrome(self, s: str) -> bool:
	        left, right = 0, len(s) - 1
	
	        while left < right:
	            while left < right and not self.alnum(s[left]):
	                left += 1
	            while right > left and not self.alnum(s[right]):
	                right -= 1
	            if s[left].lower() != s[right].lower():
	                return False
	            left += 1
	            right -= 1
	        return True
	
	    def alnum(self, char):
	        return (ord('A') <= ord(char) <= ord('Z') or
	                ord('a') <= ord(char) <= ord('z') or
	                ord('0') <= ord(char) <= ord('9'))