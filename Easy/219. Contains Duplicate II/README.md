# 219. Contains Duplicate II [Link](https://leetcode.com/problems/contains-duplicate-ii/)

## Analysis of Algorithms
### Solution 1:
 - Time complexity: O(n) 
 - Space complexity: O(n)
### Solution:2
 - Time complexity: O(n**2) 
 - Space complexity: O(1)

## The Code
### Solution 1:
```Python
class Solution:
    def containsNearbyDuplicate(self, nums: List[int], k: int) -> bool:
        dic =  {}
        for i in range(len(nums)):
            if nums[i] not in dic:
                dic[nums[i]] = i
            else:
                if i - dic[nums[i]]<=k:
                    return True
                else:
                    dic[nums[i]] = i
        return False
```

### Solution 2:
```Python
class Solution:
    def containsNearbyDuplicate(self, nums: List[int], k: int) -> bool:
        
        for i in range(len(nums)):
            if nums[i] in nums[i+1:i+k+1]:
                    return True
        return False
```

## Examples

### Example 1:
> - nums = [1,2,3,1], k = 3
> 
> - True

### Example 2:
> nums = [1,0,1,1], k = 1
> 
> - True

### Example 3:
> - nums = [1,2,3,1,2,3], k = 2
>
> - False

### Example 4:
> - nums = [2,2], k = 2
>
> - True

### Example 5:
> - nums = [99,99], k = 3
>
> - True
