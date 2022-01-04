# 121. Best Time to Buy and Sell Stock

## Analysis of Algorithms
 - Time complexity: O(n)
 - Space complexity: O(1)

## The Code

```Python
class Solution:
    def maxProfit(self, prices: List[int]) -> int:
        
        to_buy = prices[0]
        max_profit = 0 # accumulator initialized with 0
        for i in prices:
            # if we have new minimum we should use it as a reference value
            to_buy = min(to_buy,i)
            # get the max profit
            max_profit  = max(i-to_buy,max_profit)
        return  max_profit
```


## Examples

### Example 1:

> - prices = [7,1,5,3,6,4]
> 
> - to_buy = 7, max_profit = 0
> 
> - to_buy = 1, max_profit = 0
> - to_buy = 1, max_profit = 4
> - to_buy = 1, max_profit = 4
> - to_buy = 1, max_profit = 5
> - to_buy = 1, max_profit = 5
> Result: max_profit = 5

### Example 2:

> prices = [7,6,4,3,1]
> - to_buy = 7, max_profit = 0
> 
> - to_buy = 6, max_profit = 0
> - to_buy = 4, max_profit = 0
> - to_buy = 3, max_profit = 0
> - to_buy = 1, max_profit = 0
> Result: max_profit = 0


