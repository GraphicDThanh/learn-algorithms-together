## Easy([1716. Calculate Money in Leetcode Bank](https://leetcode.com/problems/calculate-money-in-leetcode-bank/))

**Solution:**

Explanation:

- We will have 2 cases:
- 1. n <= 7 => we will return the total amount of money in bank after n days
- 2. n > 7
  - We will calculate 2 values: the number of weeks and the number of days left
  - Loop through the weeks and calculate the total amount of money based on weeks
  - Loop through the days left and calculate the total amount of money by continuing plus the total amount of money above with the number of weeks and the number of days left

**Analysis:**

- Time complexity: <Not clear yet about the way to calculate, I will update later>
- Space complexity: <Not clear yet about the way to calculate, I will update later>

Submission Detail

```
Status: Accepted
Runtime: 62 ms
Memory Usage: 43.4 MB
```

Code:

```TypeScript
function totalMoney(n: number): number {
  let sum = 0;
  let weeks = 0;
  let days = 0;
  
  if (n <= 7) {
    for (let i = 1; i <= n; i++) {
      sum += i;
    }
  } else {
    weeks = Math.floor(n/7);
    days = n - weeks*7;
    
    for (let i = 0; i < weeks; i++) {
      sum += 28 + (7*i);
    }
    
    for (let i = 1; i <= days; i++) {
      sum += weeks + i;
    }
  }

  return sum;
}
```