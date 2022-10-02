# Easy([119. Pascal's Triangle II](https://leetcode.com/problems/pascals-triangle-ii/))

**Solution:**

Explanation:

- If rowIndex is 0 or 1 then the default value of array will be [1] and [1, 1]
- If rowIndex is greater than or equal to 2, then specify Next Row with first default value of 1 and next value will be equal to position curRow [current index - 1] + curRow [current index]
- The loop will end if the value of the loop is greater than the value of rowIndex then will stop the loop and add the default value of 1 to the end of the array

**Analysis:**

- Time complexity: O(N2)
- Space complexity: O(N2)

Submission Detail

```
Status: Accepted
34 / 34 test cases passed.
Runtime: 114 ms
Memory Usage: 44.9 MB
```

Code:

```TypeScript
const getRow = (rowIndex: number): number[] => {
  if (rowIndex === 0) {
    return [1]
  }

  if (rowIndex === 1) {
    return [1,1]
  }

  let curRow: Array<number> = [1,1]
  for (let i = 2; i <= rowIndex; i++) {
    let nextRow: Array<number> = [1]

    for (let j = 1; j < i; j++) {
      nextRow = [...nextRow, curRow[j - 1] + curRow[j]]
    }

    curRow = [...nextRow, 1]
  }

  return curRow
};

```

