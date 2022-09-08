# Easy([21. Merge Two Sorted Lists](https://leetcode.com/problems/merge-two-sorted-lists/)) #
Solution:
- Create a head node.
- Create a previous node, it point to headNode at first
- Check the first value of 2 given lists
  - If there are no first value in 1 of 2 list, then assign head node to the other list
  - If there are no first value in both lists, then assign null to the head node
- Compare each value in 2 given lists, Which node value is smaller, append it to the previous list and move the pointer of the other node to the next node.
- If the next node of current node is null, then stop.

Analysis:
- Time complexity: O(n)
- Space complexity:

Submission Detail
- Status: Accepted
- 6 / 6 test cases passed.
- Runtime: 113 ms
- Memory Usage: 45.1 MB

Code:
```ts
/**
 * Definition for singly-linked list.
 * class ListNode {
 *     val: number
 *     next: ListNode | null
 *     constructor(val?: number, next?: ListNode | null) {
 *         this.val = (val===undefined ? 0 : val)
 *         this.next = (next===undefined ? null : next)
 *     }
 * }
 */

function mergeTwoLists(list1: ListNode | null, list2: ListNode | null): ListNode | null {
    var list3 = new ListNode(null, null);
    var prevNode = list3;
  
    while (list1 !== null && list2 !== null) {
        if (list1.val <= list2.val) { 
            prevNode.next = list1;
            list1 = list1.next;
        } else {
            prevNode.next = list2;
            list2 = list2.next;
        }
        prevNode = prevNode.next;
    }

    if (list1 === null) { 
      prevNode.next = list2; 
    }
    if (list2 === null) { 
      prevNode.next = list1; 
    }

    return list3.next;
};
```
