# Easy ([Two Sum](https://leetcode.com/problems/two-sum/)) #
- Solution
  - Loop through given array
  - With each item, find the second value such that they add up to target
  - Check if that value exist in the given array
    - If yes, then return the index of the current item and the index of second value
    - If no, continue to check another items
- Analysis
  - Time complexity: O(n)
  - Space complexity: O(n)
- Submission detail
  - 57/57 test cases passed
  - Run time: 160ms
  - Memory usage: 44.7 MB 
- Code
```ts
function twoSum(nums: number[], target: number): number[] {
    let twoIndex: number[] = []
    for (let i = 0; i < nums.length; i++) {
        const secondNum = target - nums[i]
        if (nums.includes(secondNum, i + 1)) {
            const index = nums.indexOf(secondNum, i + 1)
            twoIndex.push(i, index)
            break
        } else {
            continue
        }
    }
    return twoIndex
};
```
