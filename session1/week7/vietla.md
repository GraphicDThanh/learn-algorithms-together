# Easy([1716. Calculate Money in Leetcode Bank](https://leetcode.com/problems/calculate-money-in-leetcode-bank/))

Solution:

- Loop to n value
- Count number of days within week. If it's next week, we need set putting money, days
- Sum money to save money

Analysis:

- Time complexity:
- Space complexity:

Submission Detail

- Status: Accepted
- 3 / 3 test cases passed.
- Runtime: 80 ms
- Memory Usage: 43.1 MB

Code:

```javascript
/**
 * @param {number} n
 * @return {number}
 */
var totalMoney = function (n) {
  let weekCount = 0;
  let result = 0;
  let value = 1;
  let count = 0;
  let i = 1;

  // ------- FOR
  //     for (let i = 1; i <= n; i++) {
  //       if (count > 6) {
  //         weekCount++
  //         value = 1 + weekCount
  //         count = 0
  //       }

  //       result+=value
  //       value++
  //       count++
  //     }

  // ------- WHILE
  while (i <= n) {
    if (count > 6) {
      weekCount++;
      value = 1 + weekCount;
      count = 0;
    }

    result += value;
    value++;
    count++;
    i++;
  }

  console.log(result);
  return result;
};
```
