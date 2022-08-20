## Easy([441. Arranging Coins](https://leetcode.com/problems/arranging-coins/))

**Solution 1: Brute Force**
- The row will start with 1 and end with h, where h <=n
- Just fill each row until the rest is smaller than the row
 
Analysis:
- Time complexity: O(n)
- Space complexity: O(1)

Submission Detail
```
Status: Accepted
1335 / 1335 test cases passed.
Runtime: 767 ms
Memory Usage: 13.9 MB
```

Code: 
```python
class Solution:
    def arrangeCoins(self, n: int) -> int:
        rows = 1
        while n > 0:
            rows = rows + 1
            n = n - rows
        
        return rows - 1
```

**Solution 2: Binary Search**
- The coins for k rows will be sum up from 1 to k, mean = 1 + 2 + 3 + ... + k = (k * (k + 1)) / 2
- With binary search, the range will from 1 to n
  - the left will start with 1, the right will start with n
  - the middle will start with left + (right - left) / 2
  - the coins need to fill from left to right = left * (right + 1) / 2
  

Analysis:
- Time complexity: O(logn)
- Space complexity: O(1)

Submission Detail
```
Status: Accepted
x / x test cases passed.
Runtime: x ms
Memory Usage: x MB
```

**Issue: TIL**

Code: 
```python
class Solution:
    def arrangeCoins(self, n: int) -> int:
        left, right, complete_rows = 1, n, 0
        
        while left <= right:
            # middle value
            middle = left + (right - left) // 2
            
            # sum from left to right
            coins_needed_from_l_to_r = left * (right + 1) / 2
            
            if coins_needed_from_l_to_r > n:
                # move right to before the middle
                right = middle - 1
            else:
                # move the left to middle
                left = middle
                # set the rows complete to middle
                complete_rows = middle
        
        return int(complete_rows) - 1
```