# Easy([1859. Sorting the Sentence](https://leetcode.com/problems/sorting-the-sentence/)) #
## Solution 1: Use math format ##
- Solution
  - $total = total On Full Week + total On Surplus Days$
  - $totalOnFullWeeks = 28 * fullWeeks + 7 * {(fullWeeks - 1) * fullWeeks \over 2}$
  - $totalOnSurplusDays = surplusDays * fullWeeks + {surplusDays * (surplusDays + 1) \over 2}$
  - fullWeeks = floor(n / 7)
  - surplusDays = n % 7
- Analysis:
  - Time complexity: O(1)
  - Space complexity:
- Submission Detail
  - 106 / 106 test cases passed.
  - Runtime: 112 ms
  - Memory Usage: 43.3 MB
- Code
```ts
function totalMoney(n: number): number {
    const fullWeeks = Math.floor(n / 7)
    const surplusDays = n % 7
    const totalOnFullWeeks = 28 * fullWeeks + 7 * (((fullWeeks - 1) * fullWeeks) / 2)
    const totalOnSurplusDays = surplusDays * fullWeeks + surplusDays * (surplusDays + 1) / 2
    return totalOnFullWeeks + totalOnSurplusDays
};
```
## Solution 2: Use loop to plus money day by day ##
- Solution
  - Loop through all days
  - Add an amount equal to the number of the day and the number of the week to the total
- Analysis:
  - Time complexity: O(n)
  - Space complexity:
- Submission Detail:
  - 106 / 106 test cases passed.
  - Runtime: 99 ms
  - Memory Usage: 43 MB
- Code
```ts
function totalMoney(n: number): number {
    let total = 0
    let day = 1
    let week = 0
    for (let i = 1; i <= n; i++) {
        total = total + day + week
        if (day < 7) {
            day++
        } else {
            day = 1
            week++
        }
    }
    return total
};
```
