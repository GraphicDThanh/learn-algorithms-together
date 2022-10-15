## Medium([238. Product of Array Except Self](https://leetcode.com/problems/product-of-array-except-self/))

**Solution:**

Analysis: `nums: [1, 2, 3, 4]`
- the results at `1` is: `2 * 3 * 4 = 24`
- the results at `2` is: `1 * 3 * 4 = 12`

that mean will be multiple the before and after of num
- before at `2`: `[1]`, after at `2`: `[3, 4]`
- result = `1 * 12 = 12`

#### Example: `nums = [1,2,3,4]`
#### Solution: 
use an array to store the results
multiple then default value will be 1, `results = [1,1,1,1]`

**There are 2 loops:**
- prefix loop (left to right) 
- postfix loop (right to left)

**Prefix loop:**
- the prefix of the first number always empty, we store the 1 as default multiple (`x * 1 = x`), the prefix start with 1
- the next prefix will be current prefix * number at the position
- the next result prefix will be the prefix value after update        

`results = [1,1,2,6]`

**Postfix loop:**
- the results will use from the prefix loop to multiple the rest on postfix
- we need a reverse index because postfix loop from right to left
- the postfix and the last number always empty, , we store the 1 as default multiple (x * 1 = x), the postfix also start with 1
- the next result postfix will be the postfix * results at that position
- the next postfix will be current postfix * number at the position

`results = [24,12,8,6]`

**Analysis:**
- Time complexity: `O(n)`
- Space complexity: `O(n)`

**Submission Detail**
```
Status: Accepted
22 / 22 test cases passed.
Runtime: 295 ms
Memory Usage: 21.1 MB
```

Code: 
```python
class Solution:
    def productExceptSelf(self, nums: List[int]) -> List[int]:
        results = [1 for i in nums]
        len_nums = len(nums)
        prefix = postfix = 1 
        
        # prefix: left to right
        for i, n in enumerate(nums):
            if i != len_nums - 1:
                prefix = prefix * n
                results[i+1] = prefix
        
        # postfix: right to left
        index_reversed = reversed(range(0, len_nums))
        for i in index_reversed:
            if i != len_nums - 1:
                results[i] = results[i] * postfix
            
            postfix = postfix * nums[i]
          
        return results
```
