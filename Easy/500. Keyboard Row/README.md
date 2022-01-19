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
class Solution:
    def findWords(self, words: List[str]) -> List[str]:
        key ={'Q':1,'W':1,'E':1,'R':1,'T':1,'Y':1,'U':1,'I':1,'O':1,'P':1,
              'A':2,'S':2,'D':2,'F':2,'G':2,'H':2,'J':2,'K':2,'L':2,
              'Z':3,'X':3,'C':3,'V':3,'B':3,'N':3,'M':3}


        valid_words = list()
        for word in words:
            row_num = key[word[0].upper()]
        
            valid_words.append(word)
            
            for char in word.upper():
                if key[char] != row_num:
                    valid_words.pop()
                    break   
            
        return valid_words
```

## Examples
### Example 1:

> Input: words = ["Hello","Alaska","Dad","Peace"]<br/>
> Output: ["Alaska","Dad"]

### Example 2:

> **Input:** words = ["omk"]<br/>
> Output: []

### Example 3:

> Input: words = ["adsdf","sfd"]<br/>
> Output: ["adsdf","sfd"]
