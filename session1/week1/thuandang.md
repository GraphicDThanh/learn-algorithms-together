## Easy([35. Search Insert Position](https://leetcode.com/problems/search-insert-position/))

**Solution:**

Explanation:

- Initialize 2 variables `start` and `end` as the first and last index of array
- At while create a variable mid with the lowest average value to check the value at index and target position
- If the target is less than the value at the index of `mid`, the index of the `end` will be reassigned to `mid - 1` otherwise `mid + 1`
- The loop will continue until the value at index mid is equal to target
- If there is no value at the last index position equal to the target, the condition at this time start is greater than the end and the loop ends. Then return the position of start which is also the position of the target after being added to the arrays

**Analysis:**

- Time complexity: O(log n)
- Space complexity: O(log n)

Submission Detail

```
Status: Accepted
64 / 64 test cases passed.
Runtime: 77 ms
Memory Usage: 44.7 MB
```

Code:

```TypeScript
/**
 *
 * @param ArrayNumbers - Arrays of numbers to find
 * @param target - target value
 * @returns index of target value
 */
const searchInsert = (ArrayNumbers: number[], target: number): number => {
    let start = 0;
    let end = ArrayNumbers.length - 1;

    while (start <= end) {
        let mid = start + Math.floor((end - start) / 2);

        if(target < ArrayNumbers[mid]){
            end = mid - 1;
        } else if (target > ArrayNumbers[mid]) {
            start = mid + 1;
        } else {
            return mid
        }
    }

    return start;
};
```

