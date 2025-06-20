---
title: "🏀 Group Balls by Sequence | GFG Solution 🔍"
keywords🏷️: ["🏀 group balls", "🔍 frequency map", "🔢 consecutive sequence", "🗂️ hash map", "📊 counting sort", "🚀 coding interview", "🧩 greedy", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Group Balls by Sequence problem: determine if balls can be grouped into consecutive sequences of length k using frequency mapping. 🚀"
date: 📅 2025-06-20
---

# *171. Group Balls by Sequence*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/group-balls-by-sequence/1)

## **🧩 Problem Description**

You are given an array `arr[]` of positive integers, where each element `arr[i]` represents the number written on the i-th ball, and a positive integer `k`. Your task is to determine whether it is possible to rearrange all the balls into groups such that:

- Each group contains exactly **k balls**.
- The numbers in each group are **consecutive integers**.


## Code(C++)
```cpp
class Solution {
public:
    bool validgroup(vector<int> &arr, int k) {
        map<int, int> m;
        for (int x : arr) m[x]++;
        for (auto& p : m) {
            int v = p.first, f = p.second;
            if (f == 0) continue;
            for (int i = 1; i < k; i++) {
                if (m[v + i] < f) return false;
                m[v + i] -= f;
            }
        }
        return true;
    }
};
```

## Code (Java)

```java
class Solution {
    public boolean validgroup(int[] arr, int k) {
        Map<Integer, Integer> m = new TreeMap<>();
        for (int x : arr) m.put(x, m.getOrDefault(x, 0) + 1);
        for (Map.Entry<Integer, Integer> e : m.entrySet()) {
            int v = e.getKey(), f = e.getValue();
            if (f == 0) continue;
            for (int i = 1; i < k; i++) {
                if (m.getOrDefault(v + i, 0) < f) return false;
                m.put(v + i, m.get(v + i) - f);
            }
        }
        return true;
    }
}
```

## Code (Python)

```python
from collections import Counter
class Solution:
    def validgroup(self, arr, k):
        m = Counter(arr)
        for v in sorted(m.keys()):
            f = m[v]
            if f == 0: continue
            for i in range(1, k):
                if m[v + i] < f: return False
                m[v + i] -= f
        return True
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
