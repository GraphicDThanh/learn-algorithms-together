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
 * @param sentence is arrays of a list of words
 * @returns maximum value of profit
 */
 const sortSentence = (sentence: string): string =>
sentence
   .split(" ")
   .sort((a, b) => Number(a[a.length - 1]) - Number(b[b.length - 1]))
   .map((element) => element.slice(0, element.length - 1))
   .join(" ");

```

