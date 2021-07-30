# First Unique Character in a String

Given a string `s`, find the first non-repeating character in it and return its index. If it does not exist, return -1.

### Example:

**_Input:_** `s = "leetcode"`

**_Output:_** `0`

### Constraints:

`1 <= s.length <= 10^5`

`s consists of only lowercase English letters.`

## Solution in JavaScript:

```
var firstUniqChar = function(s) {
    let set = {}
    let uniqCharIndex = -1
    for (let i = 0; i < s.length; i++) {
        if (set[s[i]]) {
            set[s[i]].count++
        } else {
            set[s[i]] = {}
            set[s[i]].count = 1
            set[s[i]].index = i
        }
    }
    
    for (let j in set) {
        if (set[j].count === 1) {
            uniqCharIndex = set[j].index
            break
        }
    }
    
    return uniqCharIndex
};
```
