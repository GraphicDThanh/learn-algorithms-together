## Easy([121. Best Time to Buy and Sell Stock](https://leetcode.com/problems/best-time-to-buy-and-sell-stock/))

**Solution:**

Explanation:

- Create a temporary variable with the first value in the array Prices
- Create an array to store all possible returns, initial default is 0
- Use a loop, iterate through all the positions of the array, if price < min price then assign min price = price. Push profits into the array
- Use Math.max to find the max profit

**Analysis:**

- Time complexity:
- Space complexity:

Submission Detail

```
Status: Accepted,
Runtime: 154 ms,
Memory Usage: 60 MB,
```

Code:

```TypeScript
/**
 * Calculate the maximum profit
 * @param prices prices array
 * @returns max profit
 */
const maxProfit = (prices: number[]): number => {
    const profitArr: number[] = [0];
    let minPrice: number = prices[0];

    for (let i = 1; i < prices.length; i++) {
        let price = prices[i];

        if (price < minPrice) {
            minPrice = price
        }

        profitArr.push(price - minPrice);
    }

    return Math.max(...profitArr)
};
```
