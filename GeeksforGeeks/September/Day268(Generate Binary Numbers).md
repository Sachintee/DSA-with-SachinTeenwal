---
title: "🔢 Generate Binary Numbers | GFG Solution 🔍"
keywords🏷️: ["🔢 binary generation", "🔍 number conversion", "📍 bit manipulation", "📈 queue", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Generate Binary Numbers problem: generate binary representation of numbers from 1 to n using efficient conversion techniques. 🚀"
date: 📅 2025-09-25
---

# *268. Generate Binary Numbers*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/generate-binary-numbers-1587115620/1)

## **🧩 Problem Description**

Given a number `n`, the task is to generate all binary numbers with decimal values from `1` to `n`.

A binary number is the base-2 representation of a decimal number, using only digits 0 and 1. The goal is to convert each decimal number from 1 to n into its corresponding binary string representation.


## Code(C++)
```cpp
class Solution {
public:
    vector<string> generateBinary(int n) {
        vector<string> res(n);
        for (int i = 0; i < n; i++) {
            string s = "";
            for (int x = i + 1; x; x /= 2) s = char('0' + x % 2) + s;
            res[i] = s;
        }
        return res;
    }
};
```

## Code (Java)

```java
class Solution {
    public ArrayList<String> generateBinary(int n) {
        ArrayList<String> res = new ArrayList<>(n);
        for (int i = 1; i <= n; i++) {
            StringBuilder sb = new StringBuilder();
            for (int x = i; x > 0; x /= 2) sb.append(x % 2);
            res.add(sb.reverse().toString());
        }
        return res;
    }
}
```

## Code (Python)

```python
class Solution:
    def generateBinary(self, n):
        return [bin(i)[2:] for i in range(1, n + 1)]
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
