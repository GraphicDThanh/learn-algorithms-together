## Easy([1716. Calculate Money in Leetcode Bank](https://leetcode.com/problems/calculate-money-in-leetcode-bank/))

**Solution:**

Explanation:

- Set initial state for total is 0, money in Monday is 0, and current money in that specific day is 0
- Use a loop from day 1 to day n from input
- If that day is monday increase money in Monday to 1, then add to the total and set current is equal to money in Monday
- Else if that day is not monday, increase current to 1, then add to the total

**Analysis:**

- Time complexity:
- Space complexity:

Submission Detail

```
Status: Accepted
106 / 106 test cases passed.
Runtime: 136 ms
Memory Usage: 42.9 MB
```

Code:

```TypeScript
function totalMoney(n: number): number {
    let total = 0;
    let monday = 0;
    let current = 0;

    for(let i = 1; i <= n; i++) {
        // if is monday
        if(i % 7 == 1) {
            monday++;
            current = monday;
        } else {
            current++;
        }

        total += current;
    }

    return total;
};

```

