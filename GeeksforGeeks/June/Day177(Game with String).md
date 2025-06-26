---
title: "🎮 Game with String | GFG Solution 🧠"
keywords🏷️: ["🧮 frequency reduction", "🧵 string manipulation", "🧊 bucket sort", "📦 max heap", "📘 GFG", "💻 DSA", "🏁 competitive programming"]
description: "✅ GFG solution to the Game with String problem: minimize string value after removing k characters using greedy strategies. 🚀"
date: 📅 2025-06-26
---
# *177. Game with String*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/game-with-string4100/1)

## **🧩 Problem Description**

You are given a string `s` consisting of lowercase alphabets and an integer `k`. You must remove exactly **k characters** from the string such that the **value of the string** is minimized.

The **value** of the string is defined as the **sum of squares of the frequencies** of all distinct characters.

Return the **minimum value** achievable after removing exactly `k` characters.


## Code(C++)
```cpp
class Solution {
public:
    int minValue(string &s, int k) {
        int f[26] = {}, m = 0;
        for (char c : s) m = max(m, ++f[c - 'a']);
        vector<int> b(m + 1);
        for (int x : f) if (x) b[x]++;
        while (k && m) {
            if (b[m] <= k) k -= b[m], b[m - 1] += b[m], b[m--] = 0;
            else b[m] -= k, b[m - 1] += k, k = 0;
        }
        int r = 0;
        for (int i = 1; i <= m; i++) r += i * i * b[i];
        return r;
    }
};
```

## Code (Java)

```java
class Solution {
    public int minValue(String s, int k) {
        int[] f = new int[26]; int m = 0;
        for (char c : s.toCharArray()) m = Math.max(m, ++f[c - 'a']);
        int[] b = new int[m + 1];
        for (int x : f) if (x > 0) b[x]++;
        while (k > 0 && m > 0) {
            if (b[m] <= k) {
                k -= b[m]; 
                b[m - 1] += b[m]; 
                b[m--] = 0;
            } else {
                b[m] -= k; 
                b[m - 1] += k; 
                k = 0;
            }
        }
        int r = 0;
        for (int i = 1; i <= m; i++) r += i * i * b[i];
        return r;
    }
}
```

## Code (Python)

```python
class Solution:
    def minValue(self, s, k):
        f = [0] * 26
        for c in s: f[ord(c) - 97] += 1
        m = max(f)
        b = [0] * (m + 1)
        for x in f: b[x] += x > 0
        while k and m:
            if b[m] <= k: k -= b[m]; b[m - 1] += b[m]; b[m] = 0; m -= 1
            else: b[m] -= k; b[m - 1] += k; k = 0
        return sum(i * i * b[i] for i in range(1, m + 1))
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
