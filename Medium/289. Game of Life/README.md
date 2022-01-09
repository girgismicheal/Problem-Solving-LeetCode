# 334. Increasing Triplet Subsequence [Link](https://leetcode.com/problems/increasing-triplet-subsequence/)
## Analysis of Algorithms
 - Time complexity: O(n)
 - Space complexity: O(1)


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

## Examples
### Example 1:
> - nums = [1,2,3,4,5]
> - min3list= [inf, inf], num = 1
> - min3list= [1, inf], num = 2
> - min3list= [1, 2], num = 3
> - valid

### Example 2:
> - nums = [5,4,3,2,1]
> - min3list= [inf, inf], num = 5
> - min3list= [5, inf], num = 4
> - min3list= [4, inf], num = 3
> - min3list= [3, inf], num = 2
> - min3list= [2, inf], num = 1
> - min3list= [1, inf]
> - Invalid

### Example 3:
> - nums = [2,1,5,0,4,6]
> - min3list= [inf, inf], num = 2
> - min3list= [2, inf], num = 1
> - min3list= [1, inf], num = 5
> - min3list= [1, 5], num = 0
> - min3list= [0, 5], num = 4
> - min3list= [0, 4], num = 6
> - valid


