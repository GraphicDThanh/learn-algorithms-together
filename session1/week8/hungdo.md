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
