# Easy([119. Pascal's Triangle II](https://leetcode.com/problems/pascals-triangle-ii/))

Solution:

- Depend on Binomial Theorem formula to get value at a-th row and b-th column

Analysis:

- Time complexity:
- Space complexity:

Submission Detail

- Status: Accepted
- None / None test cases passed.
- Runtime: 75 ms
- Memory Usage: 42.3 MB

Code:

```javascript
/**
 * @param {number} rowIndex
 * @return {number[]}
 */
var getRow = function (rowIndex) {
  const rowAtIndex = new Array(rowIndex + 1);

  const factorial = (x) => {
    if (x == 0) return 1;
    return x * factorial(x - 1);
  };

  const binomial = (a, b) => {
    numerator = factorial(a);
    denominator = factorial(a - b) * factorial(b);

    return numerator / denominator;
  };

  for (let i = 0; i <= rowIndex; i++) {
    rowAtIndex[i] = binomial(rowIndex, i);
  }

  return rowAtIndex;
};
```
