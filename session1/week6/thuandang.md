## Easy([1859. Sorting the Sentence](https://leetcode.com/problems/sorting-the-sentence/))

**Solution:**

Explanation:

- Use the split method to create an array containing the separate words of the previous jumbled sentence
- Use the sort function to compare words with the available index in the word
- Use map function in combination with splice(first index position + length - 1)th position to remove redundant indexes in words and use join function to split words in array

**Analysis:**

- Time complexity:
- Space complexity:

Submission Detail

```
Status: Accepted
45 / 45 test cases passed.
Runtime: 110 ms
Memory Usage: 43.2 MB
```

Code:

```TypeScript
/**
 *
 * @param sentence is arrays of a list of words
 * @returns a original sentence
 */
 const sortSentence = (sentence: string): string =>
sentence
   .split(" ")
   .sort((a, b) => Number(a[a.length - 1]) - Number(b[b.length - 1]))
   .map((element) => element.slice(0, element.length - 1))
   .join(" ");

```

