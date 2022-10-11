## Easy([541. Reverse String II](https://leetcode.com/problems/reverse-string-ii//))

**Solution:**

Explanation:

- Split the string to an array: `'abcdefgh' -> [a, b, c, d, e, f, g, h]`
- Continue split array to multiple sub arrays with length is `k`: `[[a, b], [c, d], [e, f], [g, h]]`
- Use the map loop through the array if the index is odd reversed it: `[[a, b], [d, c], [e, f], [h, g]]`
- Convert to string `[[a, b], [d, c], [e, f], [h, g]] -> 'abdcefhg'`

**Analysis:**

- Time complexity: <Still don't know about this, I'll research later>
- Space complexity: <Still don't know about this, I'll research later>

Submission Detail

```
Status: Accepted
60 / 60 test cases passed.
Runtime: 74 ms
Memory Usage: 47.3 MB
```

Code:

```TypeScript
function reverseStr(s: string, k: number): string {
    const splittedStr = s.split("");

    // this part I copy from somewhere in stackoverflow :v
    const splittedArr = splittedStr.reduce((resultArray, item, index) => {
      const chunkIndex = Math.floor(index/k)

      if(!resultArray[chunkIndex]) {
        resultArray[chunkIndex] = [] // start a new chunk
      }

      resultArray[chunkIndex].push(item)

      return resultArray
    }, [])


    const reversedArr = splittedArr.map((arr, index) => index % 2 === 0 ? arr.reverse().join("") : arr.join(""));


    return reversedArr.join("")
};
```
