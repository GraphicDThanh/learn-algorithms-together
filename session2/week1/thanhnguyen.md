## Easy([541. Reverse String II](https://leetcode.com/problems/reverse-string-ii/))

**Solution:**
- Use a list to save index list of 2k from 0 to length of string
- Loop to the index list and pick the 2k string, reverse the first k letter and keep the rest then append to the results

**Analysis:**
- Time complexity: `O(n)`
- Space complexity: `O(n)`

**Submission Detail**
```
Status: Accepted
60 / 60 test cases passed.
Runtime: 65 ms
Memory Usage: 14.2 MB
```

Code: 
```python
class Solution:
    def reverseStr(self, s: str, k: int) -> str:
        result_s = ""
        
        # indexed of 2k is the range from 0 to len s with step is 2k
        indexes_2k = list(range(0, len(s) + 1, 2 * k))
        len_indexes_2k = len(indexes_2k) 
        
        # Break s down to 2k, revert the first k and add to results
        for key, value in enumerate(indexes_2k):
            
            if key + 1 >= len_indexes_2k:
                # the rest is smaller than len_indexes_2k
                chunk_2k = s[value:]
            else:
                # a chunk 2k start by value and the next index of it
                chunk_2k = s[value:indexes_2k[key + 1]]

            reverse_chunk_k = chunk_2k[0:k][::-1]
            transfer_chunk_2k = reverse_chunk_k + chunk_2k[k:]
            result_s += transfer_chunk_2k
            
        return result_s


```
