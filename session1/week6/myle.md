# Easy([1859. Sorting the Sentence](https://leetcode.com/problems/sorting-the-sentence/)) #
Solution:
- Split letters in the given sentence into items in an array
- Sort items in letters array
- Use join method to concate sorted letters into a sentence

Analysis:
- Time complexity: O(n)
- Space complexity:

Submission Detail
- Status: Accepted
- 3 / 3 test cases passed.
- Runtime: 94 ms
- Memory Usage: 42.9 MB

Code:
```ts
function sortSentence(s: string): string {
    const letters = s.split(' ')
    let sortedLetters: string[] = []
    let count = 1
    for (let i = 0; i <= letters.length; i++) {
        letters.forEach((letter) => {
            if (parseInt(letter.charAt(letter.length - 1)) === count) {
                sortedLetters.push(letter.slice(0, letter.length - 1))
                count++
            }
        })
    }
    const sortedSentence = sortedLetters.join(' ')
    return sortedSentence
};
```
