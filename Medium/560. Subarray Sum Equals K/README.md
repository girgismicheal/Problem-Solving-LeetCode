# 560. Subarray Sum Equals K [Link](https://leetcode.com/problems/subarray-sum-equals-k/)
## Analysis of Algorithms
Solution 1:
 - Time complexity: O(n**2)
 - Space complexity: O(1)

Solution 2:
 - Time complexity: O(n)
 - Space complexity: O(n)

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

Solution 2:
```Python
class Solution:
    def subarraySum(self, nums: List[int], k: int) -> int:
        curr_sum = 0
        counter = 0
        hash_map = {0:1}
        
        for i in nums:
            curr_sum += i
            if curr_sum-k in hash_map:
                counter += hash_map[curr_sum-k]
            if curr_sum not in hash_map:
                hash_map[curr_sum] = 1
            else:
                hash_map[curr_sum] += 1
        return counter
```
