## Easy([21. Merge Two Sorted Lists](https://leetcode.com/problems/merge-two-sorted-lists/))

**Solution:**
- Use a dummy node start with 0 value
- Check list1 and list2, which smaller will add to the dummy node. Go through until one of list is empty.
- The rest of list remain will add all to the dummy node

**Analysis:**
- Time complexity: `O(n + m)`
- Space complexity: `O(1)`

**Submission Detail**
```
Status: Accepted
208 / 208 test cases passed.
Runtime: 79 ms ms
Memory Usage: 13.9  MB
```

Code: 
```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def mergeTwoLists(self, list1: Optional[ListNode], list2: Optional[ListNode]) -> Optional[ListNode]:
        dummyNode = ListNode()
        
        tail = dummyNode
        while list1 and list2:
            
            if list1.val < list2.val:
                # if list1 current node value 
                # smaller than list2 current node value
                # then choice list1 to be the next of tail
                # and move list1 to next node
                tail.next = list1
                list1 = list1.next
            else:
                # otherwise to list2
                tail.next = list2
                list2 = list2.next
            
            # move tail to the next one
            tail = tail.next
        
        # check remaining and merge to dummy node
        if list1:
            tail.next = list1
        elif list2:
            tail.next = list2

        return dummyNode.next

```