# Easy([441. Arranging Coins](https://leetcode.com/problems/arranging-coins/)) #
Solution:
- The row starts with 0
- Full coin per row starts with 0
- Plus row number to coin per row util the coin per row larger or equal the number of given coin
- Return value is number of row minus 1

Analysis:
- Time complexity: O(n)
- Space complexity:

Submission Detail
- Status: Accepted
- 10 / 10 test cases passed.
- Runtime: 153 ms
- Memory Usage: 45.3 MB

Code:
```ts
function arrangeCoins(n: number): number {
    let row: number = 0
    let coin: number = 0
    while (n >= coin) {
        coin += row
        if (n >= coin) {
            row++
        } else {
            break
        }
    }
    return row-1
};
 ```
