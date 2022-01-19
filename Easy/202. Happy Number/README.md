# 202. Happy Number [Link](https://leetcode.com/problems/happy-number/)

## Analysis of Algorithms
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
> **Input:** n = 19 <br/>
> 1<sup>2</sup> + 9<sup>2</sup> = 82 <br/>
> 8<sup>2</sup> + 2<sup>2</sup> = 68 <br/>
> 6<sup>2</sup> + 8<sup>2</sup> = 100 <br/>
> 1<sup>2</sup> + 0<sup>2</sup> + 0<sup>2</sup> = 1 <br/>
> **Output: ** True <br/>

### Example 2:
> **Input:** n = 2<br/>
> 



