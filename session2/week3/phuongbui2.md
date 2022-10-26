## Easy([88. Merge Sorted Array](https://leetcode.com/problems/merge-sorted-array/))

**Solution:**
- Use two pointers, start from right to left
  - One pointer is start from the last element of nums1
  - One pointer is start from the last element of nums2
  - Then merge two pointers into 1
- Sort the result after merging

**Analysis:**
- Time complexity:
- Space complexity:

**Submission Detail**
```
Status: Accepted
59 / 59 test cases passed
Runtime: 136 ms
Memory Usage: 43.2 MB
```

Code: 
```TypeScript
/**
 Do not return anything, modify nums1 in-place instead.
 */
function merge(nums1: number[], m: number, nums2: number[], n: number): void {
  let idx1 = m-1;
  let idx2 = n-1;
  let lastIdx = m+n-1;
    
  for (lastIdx; lastIdx >= 0 && idx2 >= 0; lastIdx--) {
    nums1[lastIdx] = nums2[idx2];
    idx2--;
  }
    
  for (let i = 0; i < nums1.length; i++) {
    for (let j = i + 1; j < nums1.length; j++) {
      if (nums1[i] > nums1[j]) {
        let temp = nums1[i];
        nums1[i] = nums1[j];
        nums1[j] = temp;
      }
    }
  }
};
```