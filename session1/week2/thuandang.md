## Easy([441. Arranging Coins](https://leetcode.com/problems/arranging-coins/))

**Solution:**

Explanation:

- Create a temporary variable to store the number of coins
- If the temporary variable is smaller than the initial coin number, stairs will be + 1
- If the temporary variable is larger than the original number of coins, the value of the stairs will be returned

**Analysis:**

- Time complexity:
- Space complexity:

Submission Detail

```
Status: Accepted
1335 / 1335 test cases passed.
Runtime: 161 ms
Memory Usage: 44.9 MB
```

Code:

```TypeScript
/**
 *
 * @param n is total number of coins
 * @returns total of stairs
 */
const arrangeCoins = (n: number): number => {
  let stairs = 0;
  let result = 0;
  for (let i = 1; i <= n; i++) {
    result += i;
    if (result <= n) {
      stairs++;
    } else {
      return stairs;
    }
  }
  return stairs;
};

```

