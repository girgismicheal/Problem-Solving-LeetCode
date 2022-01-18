# 454. 4Sum II [Link](https://leetcode.com/problems/4sum-ii/)
## Analysis of Algorithms
 - Time complexity: O(N^2^)
 - Space complexity: O(N)

## The Code

```Python 
class Solution:
    def fourSumCount(self, nums1: List[int], nums2: List[int], nums3: List[int], nums4: List[int]) -> int:
        dic = {}
        count = 0;
        for i in nums1:
            for j in nums2:
                if (i+j) not in dic:
                    dic[i+j] =1
                else:
                    dic[i+j] += 1
                    
        for i in nums3:
            for j in nums4:
                if (-(i+j)) in dic:
                    count+= dic[-(i+j)]
        return count
```
