# 334. Increasing Triplet Subsequence

## Time complexity: O(n)
## Space complexity: O(1)
```Python 
class Solution:
    def increasingTriplet(self, nums: List[int]) -> bool:
        min3list = [float('inf')]*3
        for num in nums:
            if min3list[0] >= num:
                min3list[0] = num
            elif min3list[1] >= num:
                min3list[1] = num
            else:
                min3list[2] = num
        if min3list[2] != float('inf'): return True
        return False
```
