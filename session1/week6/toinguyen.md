# Easy([1859. Sorting the Sentence ](https://leetcode.com/problems/sorting-the-sentence/))

Solution:

- Get list of words by split each word in sentence
- Loop through list words, and sort them by the last character of each word
- Group sorted list words

Analysis:

- Time complexity:
- Space complexity:

Submission Detail

- Status: Accepted
- 45 / 45 test cases passed.
- Runtime: 90 ms
- Memory Usage: 41.9 MB

Code:

```javascript
/**
 * @param {string} s
 * @return {string}
 */
const sortSentence = (s) => {
  const splitWords = s.split(' ');
  const sortedSentence = [];

  splitWords.forEach((item) => {
    const word = item.slice(0, -1);
    const index = item.slice(-1);

    sortedSentence[index - 1] = word;
  });

  return sortedSentence.join(' ');
};
```
