## Easy([1716. Calculate Money in Leetcode Bank](https://leetcode.com/problems/calculate-money-in-leetcode-bank/))

**Solution:**
- 0 to 6 correspond to the days of the week (E.g. 0 = Monday, 1 = Tuesday...)
- And the index of the week starts with 1 and increase by 1 every week that passes as Hercy will put in $1 more than the previous Monday
- The amount of money that Hercy put into Leetcode Bank a day will be the sum of day index and week index

**Analysis:**
- Time complexity: 
- Space complexity: 

**Submission Detail**
```
Status: Accepted
106 / 106 test cases passed.
Runtime: 63 ms
Memory Usage: 41.8 MB
```

Code: 
```javascript
var totalMoney = function(n) {
  let total = 0
  let week = 1
  let day = 0
  let loop = 0
  
  while (loop < n) {
    if (day === 7) {
      day = 0
      week += 1
      continue
    }
    total += week + day
    day++
    loop++
  }

  return total
};
```