---
Difficulty: Easy  
Source: 160 Days of Problem Solving  
Tags:
  - two-pointer-algorithm
  - Strings
---

# 🚀 _Day 11. Longest substring with distinct characters_ 🧠


The problem can be found at the following link: [Problem Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/two-pointer-technique-gfg-160/problem/longest-distinct-characters-in-string5848)


## 💡 **Problem Description:**

Given a string `s`, your task is to find the length of the longest substring with all distinct characters.

## 🔍 **Example Walkthrough:**

**Input:**  
`s = "geeksforgeeks"`  
**Output:**  
`7`  
**Explanation:**  
"eksforg" is the longest substring with all distinct characters.


**Input:**  
`s = "aaa"`  
**Output:**  
`1`  
**Explanation:**  
The longest substring with all distinct characters is "a".


**Input:**  
`s = "abcdefabcbb"`  
**Output:**  
`6`  
**Explanation:**  
The longest substring with all distinct characters is "abcdef", which has a length of 6.


### Constraints:
- $`1 <= s.size() <= 3 * 10^4`$
- All characters are lowercase English alphabets.


## 🎯 **My Approach:**

1. **Sliding Window Technique**:  
   To find the longest substring with distinct characters, we maintain a sliding window that contains only unique characters. If a duplicate character is found, we slide the window forward to remove it.

2. **Steps**:
   - Use an array `lastSeen` to store the last seen index of each character.  
   - Traverse the string using a pointer (`end`) to extend the window.  
   - Use a second pointer (`start`) to mark the beginning of the valid window. If a duplicate is found, move `start` to ensure all characters in the window are unique.  
   - Keep track of the maximum length of the substring during the traversal.  

3. **Edge Cases**:
   - Empty or very small strings.  
   - Strings with all identical characters.  
   - Strings with all unique characters.


## 🕒 **Time and Auxiliary Space Complexity** 

- **Expected Time Complexity:** O(n), where `n` is the length of the string. Each character is processed at most twice (once when extending the window and once when shrinking it).  
- **Expected Auxiliary Space Complexity:** O(1), as the space used for the `lastSeen` array is constant (128 elements for ASCII).

## 📝 **Solution Code**

## Code (C++)

```cpp
#include <unordered_map>
#include <string>
using namespace std;

class Solution {
public:
    int longestUniqueSubstr(string s) {
        unordered_map<char, int> mp;
        int left = 0, ans = 0;

        for (int right = 0; right < s.length(); right++) {
            mp[s[right]]++;

            while (mp[s[right]] > 1) {
                mp[s[left]]--;
                left++;
            }

            ans = max(ans, right - left + 1);
        }

        return ans;
    }
};
```


## Code (Java)

```java
import java.util.HashMap;

class Solution {
    public int longestUniqueSubstr(String s) {
        HashMap<Character, Integer> map = new HashMap<>();
        int left = 0, ans = 0;
        
        for (int right = 0; right < s.length(); right++) {
            char c = s.charAt(right);
            map.put(c, map.getOrDefault(c, 0) + 1);

            while (map.get(c) > 1) {
                char leftChar = s.charAt(left);
                map.put(leftChar, map.get(leftChar) - 1);
                left++;
            }

            ans = Math.max(ans, right - left + 1);
        }

        return ans;
    }
}

```


## Code (Python)

```python
class Solution:
    def longestUniqueSubstr(self, s):
        # code here
        mp = {}
        l, ans = 0, 0
        for r in range(len(s)):
            mp[s[r]] = mp.get(s[r], 0) + 1
            
            while mp[s[r]] > 1:
                mp[s[l]] = mp.get(s[l], 0) - 1
                l += 1
                
            ans = max(ans, r - l + 1)
        
        return ans
```


## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---

<div align="center">
 <h3><b>❤️Visitor Count❤️</b></h3>
   <textalign="center">
   <h4>864</h4>
