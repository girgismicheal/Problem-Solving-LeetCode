# 53. Maximum Subarray (Using Kadane's Algorithm) [Explanation Video](https://www.youtube.com/watch?v=86CQq3pKSUw)

#### Space complexity: O(1)
#### Time Complexity: O(n)
```Python
def maxSubArray(self, nums: List[int]) -> int:
    curr_max = total_max = nums[0]
    for i in range(1,len(nums)):
        curr_max = max(nums[i],curr_max+nums[i])    
        total_max = max(total_max,curr_max)
    return total_max
```
