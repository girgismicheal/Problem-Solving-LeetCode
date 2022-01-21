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
> **Input:** s = "A man, a plan, a canal: Panama" <br/>
> **Output:** true <br/>
> **Explanation:** "amanaplanacanalpanama" is a palindrome.

### Example 2:
> **Input:** s = "race a car" <br/>
> **Output:** false <br/>
> **Explanation:** "raceacar" is not a palindrome.

### Example 3:
> **Input:** s = " " <br/>
> **Output:** true <br/>
> **Explanation:** "" s is an empty string "" after removing non-alphanumeric characters.
Since an empty string reads the same forward and backward, it is a palindrome.

