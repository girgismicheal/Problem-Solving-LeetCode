# 202. Happy Number [Link](https://leetcode.com/problems/happy-number/)

## Analysis of Algorithms
Given an (n*m) matrix 
 - Time complexity: O(1)
 - Space complexity: O(1)

## The Code

```Python
class Solution:
    def isHappy(self, n: int) -> bool:
        my_set = list()
        x = n
        while x not in my_set:   
            my_set.append(x)
            x = sum([int(a)**2 for a in str(x)])
            
        if x ==1:
            return True
        else:
            return False
```

## Examples
### Example 1:


### Example 2:




