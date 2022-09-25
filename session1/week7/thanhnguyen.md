## Easy([1716. Calculate Money in Leetcode Bank](https://leetcode.com/problems/calculate-money-in-leetcode-bank/))

**Solution:**
- Total money wil equal to total of all rounded weeks and the rest of last week

**Analysis:**
- Time complexity: `O(n)`
- Space complexity: `O(n)`

**Submission Detail**
```
Status: Accepted
106 / 106 test cases passed.
Runtime: 41 ms
Memory Usage: 13.9 MB
```

Code: 
```python
class Solution:
    def totalMoney(self, n: int) -> int:
        """
        Total money wil equal to total of all rounded weeks 
        and the rest of last week
        """
        total = 0
        round_weeks = n // 7
        rest_last_week = n % 7
        
        if round_weeks:
            # sum of 1 + 2 + 3 + 4 + 5 + 6 + 7 = 7 * (7 + 1) / 2
            # at week i, total in the week is
            # 7 * i + (7 * 8) / 2 = 7 * i + 28
            for i in range(round_weeks):
                total += 7 * i + 28
        
        if rest_last_week:
            # if have round weeks:
            # - last week will start with round week + 1
            # if not have round weeks:
            # - last week will start with 1
            start_last_week = round_weeks + 1 if round_weeks else 1
            for i in range(rest_last_week):
                total += start_last_week + i
        
        return total

```
