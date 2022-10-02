## Easy([119. Pascal's Triangle II](https://leetcode.com/problems/pascals-triangle-ii/))

**Solution:**

Explanation:

- Generating every single row from 0 to rowIndex.
- Beginning with the initial Row is [1], then calc the next row using the previous row as ref.
- To create the next row, the first and the last member always is 1, and the other member is equal to <code>prevArray[i] + prevArray[i-1]</code>

**Analysis:**

- Time complexity: <Still don't know about this, I'll research later>
- Space complexity: <Still don't know about this, I'll research later>

Submission Detail

```
Status: Accepted
34 / 34 test cases passed.
Runtime: 123 ms
Memory Usage: 44.6 MB
```

Code:

```TypeScript
function getRow(rowIndex:number): number[] {
    let result = [1];
    let newArray = [];

    for(let j = 0; j < rowIndex; j++) {
        for(let i = 0; i < result.length; i++) {
            if (i === 0) {
                newArray.push(1);
            } else {
                newArray.push(result[i] + result[i-1])
            }
        }

        newArray.push(1);
        result = newArray;
        newArray = [];
    }

    return array;
};
```

## Hard ([1424. Diagonal Traverse II](https://leetcode.com/problems/diagonal-traverse-ii/))

**Solution:**

- Find x, y is following the columns and rows of the matrix
- The total number of diagonals will be `x + y - 1`
- Loop from `1` to `x + y - 1` to generate every diagonal of the matrix
- Use 2 loop to generate diagonal

**Analysis:**

Submission Detail

```
Status: Time Limit Exceeded
53 / 56 test cases passed
Runtime: N/A
Memory Usage: N/A
```

Code:

```TypeScript
  function findDiagonalOrder(nums: number[][]) {
    const result = [];
    const lengths = nums.map((a) => a.length);
    const y = nums.length;
    const x = nums[lengths.indexOf(Math.max(...lengths))].length;

    for (let k = 0; k < (x + y -1); k += 1) {
        for (let i = k; i >= 0; i -= 1) {
            if(nums[i] && nums[i][k-i]) {
                result.push(nums[i][k-i])
            }
        }
    }

    return result
  }
```
