# Easy([1. Two Sum](https://leetcode.com/problems/two-sum))

Solution:

- Loop for each element, get sum of current element and next element
- Return index if sum is equal with target

Analysis:

- Time complexity:
- Space complexity:

Submission Detail

- Status: Accepted
- Runtime: 165 ms
- Memory Usage: 42.4 MB

Code:

```javascript
/**
 * @param {number[]} nums
 * @param {number} target
 * @return {number[]}
 */
var twoSum = function (nums, target) {
  for (let index = 0; index < nums.length - 1; index++) {
    for (let j = index + 1; j < nums.length; j++) {
      if (nums[index] + nums[j] === target) return [index, j];
    }
  }

  return [];
};
```
