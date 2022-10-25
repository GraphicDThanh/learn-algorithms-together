## Easy([88. Merge Sorted Array](https://leetcode.com/problems/merge-sorted-array/))

**Solution:**

Explanation:

- Remove elements that not in the `m` length from `nums1`
- Replace removed elements with `n` length sliced `nums2` array
- Sort `nums1` in non-decreasing order

**Analysis:**

- Time complexity:
- Space complexity:

Submission Detail

```
Status: Accepted
Runtime: 71 ms
Memory Usage: 42.4 MB
59 / 59 test cases passed.
```

Code:

```JavaScript
/**
 Do not return anything, modify nums1 in-place instead.
 */
var merge = function (nums1, m, nums2, n) {
  nums1.splice(m, nums1.length, ...nums2.slice(0, nums2.length));
  nums1.sort((a, b) => a - b);
};
```
