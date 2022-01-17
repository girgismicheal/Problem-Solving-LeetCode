# 560. Subarray Sum Equals K [Link](https://leetcode.com/problems/subarray-sum-equals-k/)
## Analysis of Algorithms
Solution 1:
 - Time complexity: O(n**2)
 - Space complexity: O(1)

Solution 2:


## The Code
Solution 1:
```Python 
class Solution:
    def subarraySum(self, nums: List[int], k: int) -> int:
        count = 0
        for i in range(len(nums)):
            sum_nums = 0
            for j in range(i,len(nums)):
                sum_nums+= nums[j]
                if sum_nums == k:
                    count +=1
        return count
```
