# 
## Algorithm Explanation
> 1. 
> 2. 
> 3.  iterate over the nums list
>  >  - begining from index 1
>  > - assign the previse product to the current result
>  > - then update it by multiplying with the current element
> 4. 
> 5. 
> 
```Python
def productExceptSelf(self, nums: List[int]) -> List[int]:
        result = [1] * len(nums)  # Result list fill it with ones
        product = nums[0]         # assign the first element of nums to product
        # , .  then update it by multiplinig with the current element
        for i in range(1,len(nums)):
            result[i] *= product
            product *= nums[i]
            
        product = nums[len(nums)-1]
        for i in range(len(nums)-2,-1,-1):
            result[i] *= product
            product *= nums[i]
            
        return result
```
 
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

