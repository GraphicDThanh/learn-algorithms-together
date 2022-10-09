# Easy ([541. Reverse String II](https://leetcode.com/problems/reverse-string-ii))

- Solution
  - Split the provided string into chunks with `k * 2` length then reverse `k` characters in each of chunks
- Analysis
  - Time complexity:
  - Space complexity:
- Submission detail:
  - 60/60 test cases passed
  - Run time: 108
  - Memory usage: 47.3 MB
- Code

```ts
function reverseStr(s: string, k: number): string {
  let currentChunkIndex = 0;
  const temp = [];
  for (let i = 0; i < s.length; i++) {
    if (i % (k * 2) === 0) {
      i % (k * 2) === 0 && temp.push([]);
      i !== 0 && currentChunkIndex++;
    }
    temp[currentChunkIndex].push(s[i]);
  }

  for (let i = 0; i < temp.length; i++) {
    const str = temp[i].slice(0, k).reverse();
    for (let j = 0; j < str.length; j++) temp[i][j] = str[j];
    temp[i] = temp[i].join("");
  }

  return temp.join("");
}
```
