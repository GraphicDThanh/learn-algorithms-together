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

## Medium([7. Reverse Integer](https://leetcode.com/problems/reverse-integer/))

**Solution:**

Explanation:

- Just reverse it xD

**Analysis:**

- Time complexity: O(n)
- Space complexity: O(n)

Submission Detail

```
Status: Accepted
1032 / 1032 test cases passed.
Runtime: 147 ms
Memory Usage: 44.8 MB
```

Code:

```TypeScript
function reverse(x: number): number {
    let revNum = 0;
    let lastDigit = 0;

    while (x !== 0) {
        lastDigit = x % 10;
        x = (x - lastDigit) / 10;
        revNum = revNum * 10 + lastDigit;

        if (revNum < Math.pow(-2, 31) || revNum > Math.pow(2, 31) - 1) return 0
    }

    return revNum
};
```
