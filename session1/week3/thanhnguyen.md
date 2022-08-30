## Easy([121. Best Time to Buy and Sell Stock](https://leetcode.com/problems/best-time-to-buy-and-sell-stock/submissions/))

**Solution 1: Brute Force**
- maxProfit start with 0
- Each value could be a buy, and the rest of list could be sell time. If buy - sell higher than maxProfit then set new maxProfit
- Check all possible cases then return maxProfit
 
Analysis:
- Time complexity: O(n^2)
- Space complexity: O(n)

Submission Detail
```
Status: FAIl(Time Limit Access)
```

Code: 
```python
class Solution:
    def maxProfit(self, prices: List[int]) -> int:
        max_profit = 0
        
        for i, x in enumerate(prices):
            sell_prices = prices[i+1:]
            for y in sell_prices:
                if y - x > max_profit:
                    max_profit = y - x
        
        return max_profit
```

**Solution 2: 2 pointer**
- Use 2 pointers: left, right. maxProfile start with 0
- Start with left is the first day, right is the second day
- If left price smaller than right price:
  - check if profile is larger than maxProfit to set
  - keep left to keep low price
  - move on the right to the next of the right
- If left price bigger than right price:
  - move the left to the right
  - move on the right to the next of the right


Example: [7, 1, 5, 3, 6, 4]
- max_profit = 0, len = 6
- Note: 0-7 mean index 0, price 7)

|   Left  |   Right   |   Profit
|   0-7   |    1-1    |    -6
|   1-1   |    2-5    |    4     --> max_profit = 4
|   1-1   |    3-3    |    2     --> max_profit = 4
|   1-1   |    4-6    |    5     --> max_profit = 5
|   1-1   |    5-4    |    3     --> max_profit = 5

Analysis:
- Time complexity: O(n^2)
- Space complexity: O(n)

Submission Detail
```
Status: Accepted
211 / 211 test cases passed.
Runtime: 1751 ms
Memory Usage: 25.2 MB
```

Code: 
```python
class Solution:
    def maxProfit(self, prices: List[int]) -> int:
        l = 0
        r = 1
        max_profit = 0
        
        while r < len(prices):
            # only check if left price small than right price to set max profile
            if prices[l] < prices[r]:
                profit = prices[r] - prices[l]
                if profit > max_profit:
                    max_profit = profit
            else:
                # if left price bigger then right price then move left to smaller price
                l = r
            
            # always move right to the next price of right
            r += 1
        return max_profit
```