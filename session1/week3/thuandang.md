## Easy([4121. Best Time to Buy and Sell Stock](https://leetcode.com/problems/best-time-to-buy-and-sell-stock/))

**Solution:**

Explanation:

- Use for ... of to iterate over the values ​​in the provided array
- Use 2 variables minPrice and currentPrice for comparison condition
- The Match.max function will find the maximum value and will return the profit value

**Analysis:**

- Time complexity:
- Space complexity:

Submission Detail

```
Status: Accepted
211 / 211 test cases passed.
Runtime: 99 ms
Memory Usage: 51.7 MB
```

Code:

```TypeScript
/**
 *
 * @param prices is arrays of prices
 * @returns maximum value of profit
 */
const maxProfit = (prices: number[]): number => {
  let minPrice = prices[0];
  let profit = 0;

  for (let currentPrice of prices) {
    if (currentPrice > minPrice) {
      profit = Math.max(profit, currentPrice - minPrice);
    } else {
      minPrice = currentPrice;
    }
  }
  return profit;
};

```

