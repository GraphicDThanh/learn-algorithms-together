## Easy([119. Pascal's Triangle II](https://leetcode.com/problems/pascals-triangle-ii/))

**Solution:**
- Use a map to mapping each line result
- The next line will result base on the previous line
- The next line will have index change from 1 to i - 2

**Analysis:**
- Time complexity: `O(n^2)`
- Space complexity: `O(n)`

**Submission Detail**
```
Status: Accepted
38 / 38 test cases passed.
Runtime: 38 ms
Memory Usage: 13.9 MB
```

Code: 
```python
class Solution:
    def getRow(self, rowIndex: int) -> List[int]:
        map_index = {
            1: [1],
            2: [1, 1]
        }
        if rowIndex == 0:
            return map_index[1]
        if rowIndex == 1:
            return map_index[2]
        
        for i in range(3, rowIndex + 2):
            result_i = [1 for x in range(i)]
            result_prev = map_index[i-1]
            
            for c in range(1, i - 1):
                result_i[c] = result_prev[c - 1] + result_prev[c]
            
            map_index[i] = result_i
        
        return map_index[rowIndex + 1]
```
