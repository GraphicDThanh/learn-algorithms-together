# Easy ([Merge Sorted Array](https://leetcode.com/problems/merge-sorted-array)) #
- Solution
  - Replace last n `0` elements in nums1 array with elements of nums2 array
  - Use sort method to sort new nums1 array
- Analysis
  - Time complexity: O(n+m)
  - Space complexity: O(n)
- Submission detail
  - 59/59 test cases passed
  - Run time: 99ms
  - Memory usage: 44.6 MB 
- Code
```ts
/**
 Do not return anything, modify nums1 in-place instead.
 */
function merge(nums1: number[], m: number, nums2: number[], n: number): void {
    for (let i = 0; i < n + m; i++) {
        if (i >= m) {
            nums1[i] = nums2[i-m]
        }
    }
    nums1.sort((a,b) => a - b)
};
```
