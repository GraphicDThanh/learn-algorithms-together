## Medium([88. Merge Sorted Array](https://leetcode.com/problems/merge-sorted-array/))

**Solution:**
- Use two pointers, go right -> left
    - One pointer is start from m - last element of nums1's values
    - One pointer is start from n - last element of nums2's values
- Because two lists is sorted by de-inscreasing order then:
    - if value at n bigger than value at m 
        -> the last item value = value at n
        -> reduce n
    - if value at n smaller than value at m 
        -> the last item value = value at m
        -> reduce m
    - reduce last index to continue the check
    
**Analysis:**
- Time complexity: `O(m+n)`
- Space complexity: `O(1)`

**Submission Detail**
```
Status: Accepted
59 / 59 test cases passed.
Runtime: 49 ms
Memory Usage: 13.5 MB
```

Code: 
```python
class Solution(object):
    def merge(self, nums1, m, nums2, n):
        # last element is total length (m + n) - 1
        last = m + n - 1
        
        # two pointers will be on m and n
        # until one of them out of elements
        while m > 0 and n > 0:
            if nums1[m - 1] > nums2[n - 1]:
                # if value at m smaller than value at n
                # set last value on nums1 to become value at m
                nums1[last] = nums1[m - 1]
                
                # reduce m to check next item (from right to left)
                m -= 1
            else:
                # if value at m larger than value at n
                # set last value on nums1 to become value at n
                nums1[last] = nums2[n - 1]
                
                # reduce n to check next item (from right to left)
                n -= 1
            
            # reduce the last element
            last -= 1

        # the rest of nums2 if still exists
        while n > 0:
            nums1[last] = nums2[n - 1]
            n, last = n - 1, last - 1
```
