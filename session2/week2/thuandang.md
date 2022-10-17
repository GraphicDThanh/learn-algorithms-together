# Medium ([238. Product of Array Except Self](https://leetcode.com/problems/product-of-array-except-self/))

**Solution:**

Explanation:

- create an array to store the `forward values ​​* nums[i]` but `(i <nums.length)`
- Loop Backwards starting from the last index in the array:
  - the value of `results[i] (ie i = nums.length-1)` will be equal to `value * backward`
  - backward will be equal to the current `backward * nums[i] (ie i = nums.length-1)`

**Analysis:**

- Time complexity: O(N)
- Space complexity: O(N)

Submission Detail

```
Status: Accepted
22 / 22 test cases passed.
Runtime: 104 ms
Memory Usage: 56.3 MB
```

Code:

```TypeScript
const productExceptSelf = (nums: number[]): number[] => {
    const results: number[] = [];
    let forward: number = 1;

    //loop Forward
    for(let i = 0; i < nums.length; i++){
        results.push(forward)
        forward *= nums[i]
    }

    let backward: number = 1

    //loop Backward
    for(let i = nums.length - 1; i >= 0; i--){
        results[i] *= backward
        backward *= nums[i]
    }

    return results
};

// Results loop 1
// [1,1,2,6]
// Results loop 2
// loop: 1
// results = [1,1,2,6]
// backward = 4 (1x4 = 4), nums[i] = 4
// loop: 2
// results = [1,1,8,6]
// backward = 12 (4x3 = 12), nums[i] = 3
// loop: 3
// results = [1,12,8,6]
// backward = 24 (12x2 = 24), nums[i] = 2
// loop: 4
// results = [24,12,8,6]
// backward = 24 (24x1 = 24), nums[i] = 1
```

