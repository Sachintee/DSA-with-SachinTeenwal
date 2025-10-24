---
title: "🔢 Split Array Subsequences | GFG Solution 🔍"
keywords🏷️: ["🔢 consecutive subsequences", "🔍 greedy algorithm", "📍 hash map", "📈 frequency tracking", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to Split Array into Consecutive Subsequences: determine if array can be split into consecutive subsequences of length at least k using greedy approach with hash maps. 🚀"
date: 📅 2025-10-24
---

# *297. Split Array Subsequences*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/split-array-subsequences/1)

## **🧩 Problem Description**

You are given a sorted integer array `arr[]` and an integer `k`. Your task is to determine if it is possible to split the array into one or more **consecutive subsequences** such that:

* Each subsequence consists of consecutive integers (each number is exactly one greater than the previous).
* Every subsequence has a length of **at least k**.

Return `true` if such a split is possible, otherwise return `false`.


## Code(C++)
```cpp
class Solution {
public:
    bool isPossible(vector<int>& a, int k) {
        unordered_map<int,int> freq, need;
        for (int x : a) freq[x]++;
        for (int x : a) {
            if (!freq[x]) continue;
            freq[x]--;
            if (need[x] > 0) need[x]--, need[x + 1]++;
            else {
                for (int i = 1; i < k; i++) {
                    if (--freq[x + i] < 0) return false;
                }
                need[x + k]++;
            }
        }
        return true;
    }
};
```

## Code (Java)

```java
class Solution {
    public boolean isPossible(int[] a, int k) {
        Map<Integer,Integer> freq = new HashMap<>(), need = new HashMap<>();
        for (int x : a) freq.put(x, freq.getOrDefault(x, 0) + 1);
        for (int x : a) {
            if (freq.get(x) == 0) continue;
            freq.put(x, freq.get(x) - 1);
            if (need.getOrDefault(x, 0) > 0) {
                need.put(x, need.get(x) - 1);
                need.put(x + 1, need.getOrDefault(x + 1, 0) + 1);
            } else {
                for (int i = 1; i < k; i++) {
                    if (freq.getOrDefault(x + i, 0) <= 0) return false;
                    freq.put(x + i, freq.get(x + i) - 1);
                }
                need.put(x + k, need.getOrDefault(x + k, 0) + 1);
            }
        }
        return true;
    }
}
```

## Code (Python)

```python
class Solution:
    def isPossible(self, a, k):
        freq, need = {}, {}
        for x in a:
            freq[x] = freq.get(x, 0) + 1
        for x in a:
            if not freq[x]:
                continue
            freq[x] -= 1
            if need.get(x, 0):
                need[x] -= 1
                need[x + 1] = need.get(x + 1, 0) + 1
            else:
                for i in range(1, k):
                    if freq.get(x + i, 0) <= 0:
                        return False
                    freq[x + i] -= 1
                need[x + k] = need.get(x + k, 0) + 1
        return True
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
