## Easy([1859. Sorting the Sentence](https://leetcode.com/problems/sorting-the-sentence/))

**Solution:**

Explanation:

- Get the words in the sentence to form an array
- Use sort() to sort words by position from the character at the end of each word
- Create an empty array, use map to remove the character at the end of each word and push in
- Use join and return the correct string

**Analysis:**

- Time complexity:
- Space complexity:

Submission Detail

```
Status: Accepted
Runtime: 114 ms
Memory Usage: 43.1 MB
```

Code:

```TypeScript
function sortSentence(s: string): string {
  const stringArr = s.split(' ')
  const sortString = stringArr.sort(
    (a, b) => Number(a.charAt(a.length - 1)) - Number(b.charAt(b.length - 1)),
  )
  let resultArr: string[] = []

  sortString.map((item) => {
    resultArr.push(item.slice(0, item.length - 1))
  })

  return resultArr.join(' ')
}
```
