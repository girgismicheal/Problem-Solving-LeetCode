# 500. Keyboard Row [Link](https://leetcode.com/problems/keyboard-row/)
## Analysis of Algorithms
 - Time complexity: O(words*letters)
 - Space complexity: O(1)

## The Code
### Solution 1
```Python 
class Solution:
    def findWords(self, words: List[str]) -> List[str]:
        key = {1: "QWERTYUIOP",
               2: "ASDFGHJKL",
               3: "ZXCVBNM"}
        
        valid_words = list()
        for word in words:
            row_num = [i for i in range(1,4) if word[0].upper() in key[i]][0]
        
            valid_words.append(word)
            
            for char in word.upper():
                if char not in key[row_num]:
                    valid_words.pop()
                    break   
            
        return valid_words
```

### Solution 2
```Python 

```
