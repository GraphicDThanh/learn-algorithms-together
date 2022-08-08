## Easy([35. Search Insert Position](https://leetcode.com/problems/search-insert-position/))

**Solution:**

Explanation: Use binary search algorithm
- Init values:
  - left start with 0, right start with length of nums
  - middle will be average of left and right
- Continue do while left <= right
  - if mid == target -> found index, return mid
  - if mid < target -> move left to the mid + 1
  - if mid > target -> move right to the mid - 1
- The result will be the left if still not found the value

> The algorithm cost `O(logn)` since the list will half break with the middle

Analysis:
- Time complexity: `O(logn)`
- Space complexity: 

Submission Detail
```
Status: Accepted
64 / 64 test cases passed.
Runtime: 89 ms
Memory Usage: 44.3 MB
```

Code: 
```ts
function searchInsert(nums: number[], target: number): number {
    // range search will be from 0 to len of the nums
    let l = 0, r = nums.length - 1;

    while(l <= r) {
        // middle will = (left + right) % 2
        // use left + (right - left) % 2 to avoid overflow
        let m = l + (r - l) % 2;

        // if equal target, return index
        if (nums[m] == target) {
            return m;
        }
        
        if (nums[m] < target) {
            // if middle value smaller then target
            // move the left to middle + 1 index
            l = m + 1;
        } else {
            // if middle value bigger then target
            // move the right to before the middle
            // (exclude the middle because already check)
            r = m - 1;
        }
    }
    
    return l  
};
```