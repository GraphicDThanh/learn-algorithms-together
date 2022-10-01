# Easy([1716. Calculate Money in Leetcode Bank](https://leetcode.com/problems/calculate-money-in-leetcode-bank/))

Solution:

- Total money in Leetcode Bank equal (1) total money of weeks add (2) total money of odd days
- (1) Get total money of week depend on total money of first week and difference money per weeks
- (2) Get total money of odd days by [Partial Sums ](https://en.wikipedia.org/wiki/1_%2B_2_%2B_3_%2B_4_%2B_%E2%8B%AF)algorithms

Analysis:

- Time complexity:
- Space complexity:

Submission Detail

- Status: Accepted
- 106 / 106 test cases passed.
- Runtime: 61 ms
- Memory Usage: 42.1 MB

Code:

```javascript
/**
 * @param {number} n
 * @return {number}
 */
var totalMoney = function (n) {
  const oddDays = n % 7; // 7 is number of days in one week
  const weeks = (n - oddDays) / 7; // 7 is number of days in one week
  const TOTAL_MONEY_FIRST_WEEK = 1 + 2 + 3 + 4 + 5 + 6 + 7;
  const DIFFERENCE_MONEY_PER_WEEK = 7;

  // Sum of consecutive ordinal numbers
  const sumsPartial = (endPartial) => ((1 + endPartial) * endPartial) / 2;

  const totalMoneyOfWeeks =
    TOTAL_MONEY_FIRST_WEEK * weeks +
    DIFFERENCE_MONEY_PER_WEEK * sumsPartial(weeks - 1);

  const totalMoneyOfOddDays = sumsPartial(oddDays + weeks) - sumsPartial(weeks);

  return totalMoneyOfWeeks + totalMoneyOfOddDays;
};
```
