# 53. Maximum Subarray (Using Kadane's Algorithm) [Explanation Video](https://www.youtube.com/watch?v=86CQq3pKSUw)

## Analysis of Algorithms
 - Time complexity: O(1)
 - Space complexity: O(1)

## The Code

```Python
import math
class Solution:
    def isPowerOfThree(self, n: int) -> bool:
        if n <= 0:
            return False
        
        power = math.log10(n) / 0.47712125471966244 #= Log10(3)
        if power.is_integer():
            return True
        return False
```

## Examples

### Example 1:
> - nums = [-2,1,-3,4,-1,2,1,-5,4]
> - curr_max =-2, total_max= -2
> 
> - curr_max = 1, total_max= 1
> - curr_max =-2, total_max= 1
> - curr_max = 4, total_max= 4
> - curr_max = 3, total_max= 4
> - curr_max = 5, total_max= 5
> - curr_max = 6, total_max= 6
> - curr_max = 1, total_max= 6
> - curr_max = 5, total_max= 6

### Example 2:
> nums = [1]
> - curr_max = 1, total_max= 1
> 
> - curr_max = 1, total_max= 1

### Example 3:
> nums = [5,4,-1,7,8]
> - curr_max = 5, total_max= 5
> 
> - curr_max = 9, total_max= 9
> - curr_max = 8, total_max= 9
> - curr_max = 15, total_max= 15
> - curr_max = 23, total_max= 23
