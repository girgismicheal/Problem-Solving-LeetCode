# 125. Valid Palindrome [Link](https://leetcode.com/problems/valid-palindrome/)

## Analysis of Algorithms
 - Time complexity: O(n)
 - Space complexity: O(1)

## The Code
```Python
class Solution:
    def isPalindrome(self, s: str) -> bool:
        s = ''.join((filter(lambda x: x.isalnum(), s.lower())))
        size = len(s)
        for i in range(size-1):
            if s[i] != s[size-i-1]:
                return False
        return True
```

## Examples
### Example 1:

### Example 2:



