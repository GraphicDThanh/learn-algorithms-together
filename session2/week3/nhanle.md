## Easy([88. Merge Sorted Array](https://leetcode.com/problems/merge-sorted-array/))

**Solution:**

Explanation:

- Use splice to join 2 arrays
- After concatenating array nums2 to nums1 use sort to sort the array

**Analysis:**

- Time complexity:
- Space complexity:

Submission Detail

```
Status: Accepted
Runtime: 65 ms
Memory Usage: 44.4 MB
```

Code:

```TypeScript
function sortNumber(a: number, b: number) {
  return a - b
}

/**
 Do not return anything, modify nums1 in-place instead.
 */
function merge(nums1: number[], m: number, nums2: number[], n: number): void {
  let i: number
  let j = m

  for (i = 0; i < n; i++) {
    nums1.splice(j, 1, nums2[i])

    j++
  }

  nums1.sort(sortNumber)
}
```
