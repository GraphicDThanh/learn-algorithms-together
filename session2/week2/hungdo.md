## Easy([1. Two sum](https://leetcode.com/problems/two-sum/))

**Solution:**

Explanation:

- Loop for each number, find the 2nd number which if added with the first number will equal the target
- Return 2 index of number

**Analysis:**

- Time complexity: O(n)
- Space complexity: O(n)

Submission Detail

```
Status: Accepted
57 / 57 test cases passed.
Runtime: 1132 ms
Memory Usage: 50 MB

```

Code:

```TypeScript
function twoSum(nums: number[], target: number): number[] {
    for (const i in nums) {
        const firstIndex = parseInt(i);
        const newNums = nums.slice(0, firstIndex);
        const secondIndex = newNums.findIndex((num) => num === (target - nums[i]));

        if (secondIndex !== -1) {
            return [firstIndex, secondIndex]
        }
    }

    return []
};};
```
