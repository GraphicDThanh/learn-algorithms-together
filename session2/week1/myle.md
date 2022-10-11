# Easy ([541. Reverse String II](https://leetcode.com/problems/reverse-string-ii)) #
- Solution
  - Split the string to an array of characters
  - Create an empty array, which represents a new string
  - Loop through the charaters array, group them into a subarray
  - Everytime we have a subarray with `k` character:
    - If it's even subarray, just concat it to the new array
    - If it's odd subarray, reverse then concat it to the new array
  - Join items in the array into a new string
- Analysis
  - Time complexity: O(n)
  - Space complexity:
- Submission detail:
  - 2/2 test cases passed
  - Run time: 146ms
  - Memory usage: 48.6MB 
- Code
```ts
function reverseStr(s: string, k: number): string {
  let reversedSrt: string[] = [];
  const charArr: string[] = s.split("");
  let subArr: string[] = [];
  let doReverse = true;
  for (let i = 0; i < charArr.length; i++) {
    subArr.push(charArr[i])
    if ((i + 1) % k === 0 || i === charArr.length - 1) {
      if (doReverse) {
        subArr.reverse();
      }
      reversedSrt = reversedSrt.concat(subArr);
      subArr = [];
      if (((i + 1) / k) % 2 !== 0) {
        doReverse = false
      } else {
        doReverse = true
      }
    }
  }
  return reversedSrt.join("");
}
```
