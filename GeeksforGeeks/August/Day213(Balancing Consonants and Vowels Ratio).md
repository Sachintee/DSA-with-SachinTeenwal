---
title: "🔠 Balancing Consonants and Vowels Ratio | GFG Solution 🔍"
keywords🏷️: ["🔠 balanced strings", "🔍 prefix sum", "📍 hash map", "📈 subarray counting", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Balancing Consonants and Vowels Ratio problem: count balanced substrings with equal vowels and consonants using prefix sum technique. 🚀"
date: 📅 2025-08-01
---

# *213. Balancing Consonants and Vowels Ratio*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/balancing-consonants-and-vowels-ratio/1)

## **🧩 Problem Description**

You are given an array of strings `arr[]`, where each `arr[i]` consists of lowercase English alphabets. Your task is to find the number of **balanced strings** in `arr[]` which can be formed by concatenating one or more contiguous strings of `arr[]`.

A **balanced string** contains an equal number of vowels and consonants.


## Code(C++)
```cpp
class Solution {
public:
    int countBalanced(vector<string>& arr) {
        int res = 0, sum = 0;
        unordered_map<int, int> mp{{0, 1}};
        for (string& s : arr) {
            int score = 0;
            for (char c : s) score += (c == 'a' || c == 'e' || c == 'i' || c == 'o' || c == 'u') ? 1 : -1;
            res += mp[sum += score]++;
        }
        return res;
    }
};
```

## Code (Java)

```java
class Solution {
    public int countBalanced(String[] arr) {
        Map<Integer, Integer> mp = new HashMap<>();
        mp.put(0, 1);
        int sum = 0, res = 0;
        for (String s : arr) {
            for (char c : s.toCharArray()) 
                sum += "aeiou".indexOf(c) >= 0 ? 1 : -1;
            res += mp.getOrDefault(sum, 0);
            mp.put(sum, mp.getOrDefault(sum, 0) + 1);
        }
        return res;
    }
}
```

## Code (Python)

```python
class Solution:
    def countBalanced(self, arr):
        mp, s, res = {0: 1}, 0, 0
        for string in arr:
            s += sum(1 if c in 'aeiou' else -1 for c in string)
            res += mp.get(s, 0)
            mp[s] = mp.get(s, 0) + 1
        return res
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
