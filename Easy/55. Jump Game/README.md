# 55. Jump Game

### Time complexity: O(n)
### Space complexity: O(n)
```Python
def canJump(self, nums: List[int]) -> bool:
    can_reach = [False]*(len(nums)-1) + [True]
    for i in range(len(nums)-2,-1,-1):
        can_reach[i] = any(can_reach[i:i+nums[i]+1])
    return can_reach[0]
```
