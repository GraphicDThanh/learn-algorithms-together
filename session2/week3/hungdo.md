## Easy([88. Merge Sorted Array](https://leetcode.com/problems/merge-sorted-array/))

**Solution:**

Explanation:

- Remove elements that not in first `m` length of `nums1`
- Push all elements in `nums2` into `nums1`
- Sort `nums1` by ascending

**Analysis:**

- Time complexity:
- Space complexity:

Submission Detail

```
Status: Accepted
59 / 59 test cases passed.
Runtime: 95 ms
Memory Usage: 44.1 MB

```

Code:

```TypeScript
function merge(nums1: number[], m: number, nums2: number[], n: number): void {
    nums1.splice(m, nums1.length);
    nums1.push(...nums2);
    nums1.sort((a,b) => a - b);
};
```
