# 217. Contains Duplicate [Link](https://leetcode.com/problems/contains-duplicate/)

## Analysis of Algorithms
 - Time complexity: O(n)
 - Space complexity: O(n)
 
 
## The Code
### The first implementation
```Python
class Solution:
    def containsDuplicate(self, nums: List[int]) -> bool:
        d = {}
        for i in nums:
            if i in d:
                return True
            else:
                d[i] = 1
        return False
```

### The second implementation
```Python
class Solution:
    def containsDuplicate(self, nums: List[int]) -> bool:
        return len(set(nums)) != len(nums)
```


## Examples

### Example 1:
> - **Input:** nums = [1,2,3,1]
> - **Output:** true

### Example 2:


### Example 3:
