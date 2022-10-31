## Easy([66. Plus One](https://leetcode.com/problems/plus-one/))

**Solution:**

Explanation:

- Convert array of numbers to a string
- Convert string to number and +1 (note: use BigInt to [convert a string to a large integer](https://stackoverflow.com/questions/53971935/convert-a-string-to-a-big-integer-in-javascript))
- Take the calculated value and convert it back to an array

- **Analysis:**

- Time complexity:
- Space complexity:

Submission Detail

```
Status: Accepted
Runtime: 113 ms
Memory Usage: 44.8 MB
```

Code:

```TypeScript
function plusOne(digits: number[]): number[] {
    const digitString = digits.join("");
    const resultCaculator = BigInt(digitString) + BigInt(1);
    const arrNumber = String(resultCaculator)
      .split("")
      .map((num) => {
        return Number(num);
      });

    return arrNumber;
  }
```
