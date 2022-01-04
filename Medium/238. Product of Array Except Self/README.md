# 
## Algorithm Explanation
> 1. assign the fir
> 2. 
> 3. 
> 4. 
> 5. 
> 
 
> Exapmle
  [1, 2, 3, 4]

  -> [1, 1, 1, 1] product = 1, idx = 1
  -> [1, 1, 1, 1] product = 2, idx = 2
  -> [1, 1, 2, 6] product = 6, idx = 3


  -> [1, 1, 4, 1] product = 4, idx = 2
  -> [1, 12, 4, 1] product = 12, idx = 1
  -> [24, 12, 4, 1] product = 24, idx = 0


  [1, 1, 2, 6]
  [24, 12, 4, 1]
  [24, 12, 8, 6]

```Python
def productExceptSelf(self, nums: List[int]) -> List[int]:
        result = [1] * len(nums)
        product = nums[0]
        
        for i in range(1,len(nums)):
            result[i] *= product
            product *= nums[i]
            
        product = nums[len(nums)-1]
        for i in range(len(nums)-2,-1,-1):
            result[i] *= product
            product *= nums[i]
            
        return result
```
