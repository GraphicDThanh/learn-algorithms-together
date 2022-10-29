## Easy([66. Plus One](https://leetcode.com/problems/plus-one/))

**Solution:**
- Convert the digits number to a string
- Using BigInt to represent a too large number then plus one
- Convert the string into an array of digits
- Convert each string in the array to a number

**Analysis:**
- Time complexity:
- Space complexity:

**Submission Detail**
```
111 / 111 test cases passed.
Status: Accepted
Runtime: 82 ms
Memory Usage: 42.9 MB
```

Code: 
```TypeScript
function plusOne(digits: number[]): number[] {
  // Convert the number to a string
  let str:string = digits.join('');
  // Using BigInt to represent a too large number
  let arrToNum:bigint = BigInt(str);

  let numOfStr:bigint = BigInt(arrToNum + BigInt(1));
  // Convert the string into an array of digits
  const arrOfStr:string[] = Array.from(numOfStr.toString());
  // Convert each string in the array to a number
  const arrOfNum:number[] = arrOfStr.map(str => Number(str));
  
  return arrOfNum;
};
```