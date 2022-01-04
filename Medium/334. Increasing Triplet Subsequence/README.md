# 334. Increasing Triplet Subsequence [Link](https://leetcode.com/problems/increasing-triplet-subsequence/)
## Analysis of Algorithms
 - Time complexity: O(n)
 - Space complexity: O(1)
## The Algorithm Explanation

## The Code

```Python 

def increasingTriplet(nums: List[int]) -> bool:
    min3list = [float('inf')]*2
    for num in nums:
        if min3list[0] >= num:
            min3list[0] = num
        elif min3list[1] >= num:
            min3list[1] = num
        else:
            return True
    return False
```

## An Example
>




