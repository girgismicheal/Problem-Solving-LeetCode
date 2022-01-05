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
> - n = 27
> 
> - power = log(27) / log(3) = 3 !=0 
> - True
