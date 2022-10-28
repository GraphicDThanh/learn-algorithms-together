## Easy([66. Plus One](https://leetcode.com/problems/plus-one/))

**Solution:**
- Special case happen when the list have format is 999
- With 9, we need to carry 1 to the next item (from right to left)
- Solve by assume have carry, loop while still exist carry
    - if value is not 9 the reset carry to 0 and exist loop
    - if value is 9, set the value to 0 and continue the loop
    
**Analysis:**
- Time complexity: `O(n)`
- Space complexity: `O(1)`

**Submission Detail**
```
Status: Accepted
111 / 111 test cases passed.
Runtime: 29 ms
Memory Usage: 13.4 MB
```

Code: 

```python
class Solution(object):
    def plusOne(self, digits):
        """
        :type digits: List[int]
        :rtype: List[int]
        """
        length = len(digits)
        # carry wil have when the last item is 9
        carry, i = 1, length - 1
        
        # assume always have carry
        while carry:
            # still in the list
            if i > -1:
                value = digits[i]
            
                if value == 9:
                    # only kep the loop if have carry
                    digits[i] = 0
                else:
                    # value is not 9 then 
                    # - increase value to 1
                    # - update carry to 0
                    # quit the loop since no carry
                    digits[i] += 1
                    carry = 0
                    
            else:
                # out of element
                # add 1 to top of list
                # reset carry to 0 to quit the loop
                digits = [1] + digits
                carry = 0
                
            i -= 1
            
        return digits
            
```