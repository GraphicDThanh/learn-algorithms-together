## Easy([1859. Sorting the Sentence](https://leetcode.com/problems/sorting-the-sentence/))

**Solution:**
- Use a dict extract key is index, value is string
- Sort all keys increments then loop the dict values and connect string to sentence

**Analysis:**
- Time complexity: `O(n + m)`
- Space complexity: `O(1)`

**Submission Detail**
```
Status: Accepted
45 / 45 test cases passed.
Runtime: 34 ms ms
Memory Usage: 14 MB  MB
```

Code: 
```python
import re

class Solution:
    def sortSentence(self, s: str) -> str:
        word_list = s.split(" ")
        word_dict = {}
        
        for string in word_list:
            index = re.findall(r'\d+', string)[0]
            word_dict[index] = string.replace(index, '')
            
        indexes_sorted = list(word_dict.keys())
        indexes_sorted.sort()
        sentence = ''
        length_indexes_sorted = len(indexes_sorted)
        
        for i, index in enumerate(indexes_sorted):
            if i == length_indexes_sorted - 1:
                sentence += word_dict[index]
            else:
                sentence += word_dict[index] + " "
            
        return sentence
```