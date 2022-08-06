## Easy([35. Search Insert Position](https://leetcode.com/problems/search-insert-position/))

**Solution:**

Explanation:
- Use the `while` loop. The expected index starts with 0, plus 1 while the item value in the array is less than the target value. The expected index will stop increasing when the item value is equal to or greater than the target value.

Analysis:
- Time complexity: O(n)
- Space complexity: O(n)

Submission Detail
```
Status: Accepted
1 / 1 test cases passed.
Runtime: 65 ms
Memory Usage: 41.9 MB
```

Code: 
```javascript
/**
 * @param {number[]} nums
 * @param {number} target
 * @return {number}
 */
var searchInsert = function(nums, target) {
    let count = 0
    while (nums[count] < target) {
        count++
    }
    return count
};
```
