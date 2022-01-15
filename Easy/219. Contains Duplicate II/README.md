# 219. Contains Duplicate II

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

