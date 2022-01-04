#  238. Product of Array Except Self
## The Algorithm Explanation
> 1. Result list fill it with ones
> 2. Assign the first element of nums to product
> 3. Iterate over the nums list
>       > - Begining from index 1
>       > - Assign the previse product to the current result
>       > - Update it by multiplying with the current element
> 4. Assign the last element of nums to product
> 5. Iterate over the nums list
>       > - Begining from index (last-1)
>       > - Assign the previse product to the current result
>       > - Update it by multiplying with the current element


## The Code

```Python
def productExceptSelf(nums: List[int]) -> List[int]:
        result = [1] * len(nums)  # Result list fill it with ones
        product = nums[0]         # assign the first element of nums to product
        
        for i in range(1,len(nums)):
            result[i] *= product
            product *= nums[i]
            
        product = nums[len(nums)-1]
        for i in range(len(nums)-2,-1,-1):
            result[i] *= product
            product *= nums[i]
            
        return result
```
## An Exapmle

