# 766. Toeplitz Matrix [Explanation Video](https://www.youtube.com/watch?v=86CQq3pKSUw)

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
> - power = log(27) / log(3) = 3 is integer
> True
### Example 2:
> - n = 0 <= 0
> False

### Example 3:
> - n = -3 <= 0
> False

### Example 3:
> - n = 45
> 
> - power = log(27) / log(3) = 3.4649 not integer
> False
