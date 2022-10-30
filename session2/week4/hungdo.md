## Easy([66. Plus One)](https://leetcode.com/problems/plus-one)

**Solution:**

Explanation:

- Mutate the original array
- Loop through array from end to beginning
- If the value is less than 9, plus one then break the loop
- If the value is 9 replace with 0 and continue the loop
- If the index is 0 and value is 9, replace with 0 and unshift 1 to array

**Analysis:**

- Time complexity: O(n)
- Space complexity: O(n)

Submission Detail

```
Status: Accepted
111 / 111 test cases passed.
Runtime: 106 ms
Memory Usage: 43.2 MB
```

Code:

```TypeScript
function plusOne(digits: number[]): number[] {
    for (let i = digits.length - 1; i >= 0; i--) {
        if (digits[i] === 9) {
            digits[i] = 0;

            if(i === 0) {
                digits.unshift(1);

                break;
            }
        } else {
            digits[i] = digits[i] + 1;

            break;
        }
    }

    return digits
};
```
