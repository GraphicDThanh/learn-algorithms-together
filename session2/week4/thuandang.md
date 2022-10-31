# Easy ([66. Plus One](https://leetcode.com/problems/plus-one/))

**Solution:**

Explanation:

- The loop will always run at the last index position
- The value at index position [i] will be + 1 and there are 2 cases:
  - If the value is divisible by 10 (minus 0 and 10), the old array will be returned with the last index value incremented by 1.
  - If the value is divisible by 10 (10 and 0) then the last 0 will be added and the next index[i-1] will be incremented by 1.
- In case if the array has only 9, then 1 will be added to the array

**Analysis:**

- Time complexity: O(1)
- Space complexity: O(1)

Submission Detail

```
Status: Accepted
111 / 111 test cases passed.
Runtime: 94 ms
Memory Usage: 42.8 MB
```

Code:

```TypeScript
const plusOne = (digits: number[]): number[] => {
     for(let i = digits.length - 1; i >= 0 ; i--) {
        digits[i] += 1;

        if(digits[i] % 10) {
            return digits;
        }

        digits[i] %= 10;

        if(i === 0) {
            return [1, ...digits];
        }
    }
};

```
