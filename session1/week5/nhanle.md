# Easy([21. Merge Two Sorted Lists](https://leetcode.com/problems/merge-two-sorted-lists/))

Solution:

- Traverse the list. If the head node of list2 lies in between two nodes of the first list1, insert it there and make the next node of list2 the head. Continue this until there is no node left in both lists.
- Compare both the lists where the list with a smaller head value is the first list.

Analysis:

- Time complexity:
- Space complexity:

Submission Detail

- Status: Accepted
- Runtime: 73 ms
- Memory Usage: 44.2 MB

Code:

```js
function mergeUtil(list1, list2) {
  let curr1 = list1
  let next1 = list1.next
  let curr2 = list2
  let next2 = list2.next

  if (list1.next == null) {
    list1.next = list2
    return list1
  }

  while (next1 != null && curr2 != null) {
    if (curr2.val >= curr1.val && curr2.val <= next1.val) {
      next2 = curr2.next
      curr1.next = curr2
      curr2.next = next1

      curr1 = curr2
      curr2 = next2
    } else {
      if (next1.next != null) {
        next1 = next1.next
        curr1 = curr1.next
      } else {
        next1.next = curr2
        return list1
      }
    }
  }
  return list1
}

/**
 * Definition for singly-linked list.
 * function ListNode(val, next) {
 *     this.val = (val===undefined ? 0 : val)
 *     this.next = (next===undefined ? null : next)
 * }
 */

/**
 * @param {ListNode} list1
 * @param {ListNode} list2
 * @return {ListNode}
 */
var mergeTwoLists = function (list1, list2) {
  if (list1 === null) return list2
  if (list2 === null) return list1

  if (list1.val < list2.val) return mergeUtil(list1, list2)
  else return mergeUtil(list2, list1)
}
```
