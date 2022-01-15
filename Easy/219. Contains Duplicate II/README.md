# 268. Missing Number [Link](https://leetcode.com/problems/missing-number/)

## Analysis of Algorithms
 - Time complexity: O(n) **due to the sum operation**
 - Space complexity: O(1)

## The Code

```Python
class Solution:
    def missingNumber(self, nums: List[int]) -> int:
        n = len(nums)
        return (n**2 + n) //2 - sum(nums)
```

## Examples

### Example 1:
> - nums = [3,0,1]
> 
> - n = 3 <br/>
> result = 2

### Example 2:
> - nums = [0,1]
> 
> - n = 2 <br/>
> result = 2

### Example 3:
> - nums = [9,6,4,2,3,5,7,0,1]
> 
> - n = 9 <br/>
> result = 8
