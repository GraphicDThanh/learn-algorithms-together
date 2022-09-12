# Easy([21. Merge Two Sorted Lists](https://leetcode.com/problems/merge-two-sorted-lists/))

**Solution:**

Explanation:

- If both the heads are NULL return null.
- If one head is null return the other.
- Compare the head of both linked lists, find the smaller node among the two head nodes. The current element will be the smaller node among two head nodes.
- The recursive function will return the next smaller element linked with rest of the sorted element.

**Analysis:**

- Time complexity:
- Space complexity:

Submission Detail

```
- Status: Accepted
- 208 / 208 test cases passed.
- Runtime: 111 ms
- Memory Usage: 45.1 MB
```

Code:

```TypeScript
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

const mergeTwoLists = (list1: ListNode | null, list2: ListNode | null): ListNode | null => {
    if(list1 === null && list2 === null){
        return list1;
    }
    if(list1 === null){
        return list2;
    }
    if(list2 === null){
        return list1;
    }

    if (list1.val < list2.val) {
        list1.next = mergeTwoLists(list1.next, list2);
        return list1;
    } else {
        list2.next = mergeTwoLists(list1, list2.next);
        return list2;
    }
};
```

# Easy([182. Duplicate Emails](https://leetcode.com/problems/duplicate-emails/))

**Solution:**

Explanation:

- Use SELECT DISTINCT to get non-duplicate value in SQL. The DISTINCT clause will retrieve unique, distinct values, eliminating duplicate values ​​in the returned result.
- Then use group by to sort the query item by group
- The HAVING count clause will count the number of emails, if it is greater than 1, it will return the email

**Analysis:**

- Time complexity: O(n)
- Space complexity:

Submission Detail

```
- Status: Accepted
- 208 / 208 test cases passed.
- Runtime: 111 ms
- Memory Usage: 45.1 MB
```

Code:

```SQL
SELECT distinct email
FROM Person
GROUP BY email
HAVING count(email) > 1;
```
