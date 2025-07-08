---
title: "🧺 Next Element with Greater Frequency | GFG Solution 🔍"
keywords🏷️: ["🧺 next greater element", "🔍 monotonic stack", "📍 frequency analysis", "📈 hash map", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Next Element with Greater Frequency problem: find the closest element to the right with higher frequency using monotonic stack technique. 🚀"
date: 📅 2025-07-08
---

# *189. Next Element with Greater Frequency*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/next-element-with-greater-frequency--170637/1)

## **🧩 Problem Description**

Given an array `arr[]` of integers, for each element, find the **closest** (distance wise) to its right that has a **higher frequency** than the current element. If no such element exists, return **-1** for that position.

The goal is to efficiently find the next element with greater frequency for each position in the array while maintaining optimal time and space complexity.


## Code(C++)
```cpp
class Solution {
public:
    vector<int> findGreater(vector<int>& a) {
        unordered_map<int, int> f;
        for (int x : a) f[x]++;
        vector<int> r(a.size(), -1);
        stack<int> s;
        for (int i = 0; i < a.size(); i++) {
            while (!s.empty() && f[a[i]] > f[a[s.top()]]) {
                r[s.top()] = a[i];
                s.pop();
            }
            s.push(i);
        }
        return r;
    }
};
```

## Code (Java)

```java
class Solution {
    public ArrayList<Integer> findGreater(int[] a) {
        HashMap<Integer, Integer> f = new HashMap<>();
        for (int x : a) f.put(x, f.getOrDefault(x, 0) + 1);
        ArrayList<Integer> r = new ArrayList<>(Collections.nCopies(a.length, -1));
        Deque<Integer> s = new ArrayDeque<>();
        for (int i = 0; i < a.length; i++) {
            while (!s.isEmpty() && f.get(a[i]) > f.get(a[s.peekLast()]))
                r.set(s.pollLast(), a[i]);
            s.add(i);
        }
        return r;
    }
}
```

## Code (Python)

```python
from collections import Counter
class Solution:
    def findGreater(self, a):
        f = Counter(a)
        r, s = [-1]*len(a), []
        for i, v in enumerate(a):
            while s and f[v] > f[a[s[-1]]]:
                r[s.pop()] = v
            s.append(i)
        return r
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
