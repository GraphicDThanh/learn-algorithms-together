## Easy([1716. Calculate Money in Leetcode Bank](https://leetcode.com/problems/calculate-money-in-leetcode-bank/))

**Solution:**

Explanation:

- If number of days <= 7 then first day will be 1 and sum will be result of remainder division by 7 + current
- If the next number of days is > 7 then the last day of the week will be divisible by 7 and increment the current + 1

**Analysis:**

- Time complexity: O(n)
- Space complexity: O(n)

Submission Detail

```
Status: Accepted
106 / 106 test cases passed.
Runtime: 82 ms
Memory Usage: 43.6 MB
```

Code:

```TypeScript
const totalMoney = (n: number): number => {
    let current = 1;
    let total = 0;

    for (let i = 0; i < n; i++) {
        total += current+(i%7);

        if((i+1)%7 === 0)
            current++;
    }

    return total;
};

```

