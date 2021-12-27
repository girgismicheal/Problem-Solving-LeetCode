# 121. Best Time to Buy and Sell Stock

## Space complexity: O(1)
## Time Complexity: O(n)
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
