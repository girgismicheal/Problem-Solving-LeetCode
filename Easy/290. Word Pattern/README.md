# 290. Word Pattern [Link](https://leetcode.com/problems/word-pattern/)

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
> **Input:** pattern = "abba", s = "dog cat cat dog"<br/>
> **Output:** true
### Example 2:
> **Input:** pattern = "abba", s = "dog cat cat fish"<br/>
> **Output:** false

### Example 3:
> **Input:** pattern = "aaaa", s = "dog cat cat dog"<br/>
> **Output:** false


