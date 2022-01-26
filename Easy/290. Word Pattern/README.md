# 290. Word Pattern [Problem](https://leetcode.com/problems/word-pattern/)

## Analysis of Algorithms
 - Time complexity: O(n)
 - Space complexity: O(n)

## The Code

```Python
class Solution:
    def wordPattern(self, pattern: str, s: str) -> bool:
        words = s.split(' ')
        if len(pattern) != len(words):
            return False
        
        maper = {}
        for letter, word in zip(pattern, words):
            if (letter not in maper) and (word not in maper.values()):
                maper[letter] = word
            elif (letter in maper) and (word in maper.values()):
                if maper[letter] != word:
                    return False
            else:
                return False
        return True
```

## Examples

### Example 1:

### Example 2:

### Example 3:

### Example 4:

