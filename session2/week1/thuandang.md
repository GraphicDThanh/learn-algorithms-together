# Easy ([541. Reverse String II](https://leetcode.com/problems/reverse-string-ii))

**Solution:**

Explanation:

- If `(index/k)%2==0` it will take the character at index to k and reverse 2 characters otherwise, return that character.

**Analysis:**

- Time complexity: O(1)
- Space complexity: O(1)

Submission Detail

```
Status: Accepted
60 / 60 test cases passed.
Runtime: 113 ms
Memory Usage: 44.8 MB
```

Code:

```TypeScript
const reverseStr = (s: string, k: number): string => {
  let result = "";
  for (let i = 0; i < s.length; i += k) {
    if ((i / k) % 2 == 0){
        result += [...s.substr(i, k)].reverse().join("");
    }else {
        result += s.substr(i, k);
    }
  }
  return result;
};

```

