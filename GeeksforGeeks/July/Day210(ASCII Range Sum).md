---
title: "📝 ASCII Range Sum | GFG Solution 🔍"
keywords🏷️: ["📝 ascii sum", "🔍 string processing", "📍 character tracking", "📈 array iteration", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the ASCII Range Sum problem: find ASCII sum of characters between first and last occurrence of each character using efficient character tracking. 🚀"
date: 📅 2025-07-29
---

# *210. ASCII Range Sum*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/ascii-range-sum/1)

## **🧩 Problem Description**

Given a string `s` consisting of lowercase English letters, for every character whose first and last occurrences are at different positions, calculate the sum of ASCII values of characters strictly between its first and last occurrence.

Return all such **non-zero sums** (order does not matter).


## Code(C++)
```cpp
class Solution {
public:
    vector<int> asciirange(string& s) {
        vector<int> result;
        int n = s.size();
        for (int i = 0; i < 26; i++) {
            int first = -1, last = -1;
            for (int j = 0; j < n; j++) {
                if (s[j] - 'a' == i) {
                    if (first == -1) first = j;
                    last = j;
                }
            }
            if (first != -1 && last > first) {
                int sum = 0;
                for (int k = first + 1; k < last; k++) sum += s[k];
                if (sum) result.push_back(sum);
            }
        }
        return result;
    }
};
```

## Code (Java)

```java
class Solution {
    public ArrayList<Integer> asciirange(String s) {
        ArrayList<Integer> result = new ArrayList<>();
        int n = s.length();
        for (int i = 0; i < 26; i++) {
            int first = -1, last = -1;
            for (int j = 0; j < n; j++) {
                if (s.charAt(j) - 'a' == i) {
                    if (first == -1) first = j;
                    last = j;
                }
            }
            if (first != -1 && last > first) {
                int sum = 0;
                for (int k = first + 1; k < last; k++)
                    sum += s.charAt(k);
                if (sum != 0) result.add(sum);
            }
        }
        return result;
    }
}
```

## Code (Python)

```python
class Solution:
    def asciirange(self, s):
        result = []
        positions = {}
        
        for i, char in enumerate(s):
            if char not in positions:
                positions[char] = [i, i]
            else:
                positions[char][1] = i
        
        for char in sorted(positions.keys()):
            first, last = positions[char]
            if last > first:
                total = sum(ord(s[j]) for j in range(first + 1, last))
                if total:
                    result.append(total)
        
        return result
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
