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

