## Easy([1716. Calculate Money in Leetcode Bank](https://leetcode.com/problems/calculate-money-in-leetcode-bank/))

**Solution:**

Explanation:

- Use the split method to create an array containing the separate words of the previous jumbled sentence
- Use the sort function to compare words with the available index in the word
- Use map function in combination with splice(first index position + length - 1)th position to remove redundant indexes in words and use join function to split words in array

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

