# Easy ([541. Reverse String II](https://leetcode.com/problems/reverse-string-ii))

- Solution
  - Each number in the array will be compared with the next ones to it
  - If the sum of them is equal to target return them in an array
- Analysis
  - Time complexity:
  - Space complexity:
- Submission detail:
  - 57/57 test cases passed
  - Run time: 149ms
  - Memory usage: 42.6 MB
- Code

```js
var twoSum = function (nums, target) {
  for (let i = 0; i < nums.length; i++)
    for (let j = i + 1; j < nums.length; j++)
      if (nums[i] + nums[j] === target) return [i, j];
};
```
