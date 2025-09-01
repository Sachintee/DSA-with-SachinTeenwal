---
title: "🔢 Sum of Mode | GFG Solution 🔍"
keywords🏷️: ["🔢 sum of mode", "🔍 sliding window", "📍 frequency tracking", "📈 hash map", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Sum of Mode problem: find sum of modes of all subarrays of size k using efficient sliding window with frequency buckets technique. 🚀"
date: 📅 2025-09-01
---

# *244. Sum of Mode*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/sum-of-mode/1)

## **🧩 Problem Description**

You are given an array `arr[]` of positive integers and an integer `k`. Your task is to find the **sum of the modes** of all the subarrays of size `k`.

**Note:** The mode of a subarray is the element that occurs with the highest frequency. If multiple elements have the same highest frequency, the smallest such element is considered the mode.


## Code(C++)
```cpp
class Solution {
public:
    int sumOfModes(vector<int>& arr, int k) {
        int n = arr.size(), sum = 0;
        unordered_map<int, int> freq;
        map<int, set<int>> buckets;
        
        for (int i = 0; i < k; i++) freq[arr[i]]++;
        for (auto& p : freq) buckets[p.second].insert(p.first);
        sum += *buckets.rbegin()->second.begin();
        for (int i = k; i < n; i++) {
            int out = arr[i - k], in = arr[i];
            
            buckets[freq[out]].erase(out);
            if (buckets[freq[out]].empty()) buckets.erase(freq[out]);
            if (--freq[out] > 0) buckets[freq[out]].insert(out);
            else freq.erase(out);
            if (freq[in] > 0) {
                buckets[freq[in]].erase(in);
                if (buckets[freq[in]].empty()) buckets.erase(freq[in]);
            }
            buckets[++freq[in]].insert(in);
            sum += *buckets.rbegin()->second.begin();
        }
        return sum;
    }
};
```

## Code (Java)

```java
class Solution {
    public int sumOfModes(int[] arr, int k) {
        int n = arr.length, sum = 0;
        Map<Integer, Integer> freq = new HashMap<>();
        TreeMap<Integer, TreeSet<Integer>> buckets = new TreeMap<>();
        for (int i = 0; i < k; i++) freq.merge(arr[i], 1, Integer::sum);
        freq.forEach((val, f) -> buckets.computeIfAbsent(f, x -> new TreeSet<>()).add(val));
        sum += buckets.lastEntry().getValue().first();
        for (int i = k; i < n; i++) {
            int out = arr[i - k], in = arr[i];
            TreeSet<Integer> outSet = buckets.get(freq.get(out));
            outSet.remove(out);
            if (outSet.isEmpty()) buckets.remove(freq.get(out));
            freq.merge(out, -1, Integer::sum);
            if (freq.get(out) > 0) 
                buckets.computeIfAbsent(freq.get(out), x -> new TreeSet<>()).add(out);
            else freq.remove(out);
            if (freq.containsKey(in)) {
                TreeSet<Integer> inSet = buckets.get(freq.get(in));
                inSet.remove(in);
                if (inSet.isEmpty()) buckets.remove(freq.get(in));
            }
            freq.merge(in, 1, Integer::sum);
            buckets.computeIfAbsent(freq.get(in), x -> new TreeSet<>()).add(in);
            sum += buckets.lastEntry().getValue().first();
        }
        return sum;
    }
}
```

## Code (Python3)

```python
class Solution:
    def sumOfModes(self, arr, k):
        n, sum_val = len(arr), 0
        freq = defaultdict(int)
        buckets = defaultdict(set)
        for i in range(k):
            freq[arr[i]] += 1
        for val, f in freq.items():
            buckets[f].add(val)
        max_freq = max(buckets.keys())
        sum_val += min(buckets[max_freq])
        for i in range(k, n):
            out, in_val = arr[i - k], arr[i]
            buckets[freq[out]].remove(out)

            if not buckets[freq[out]]:
                del buckets[freq[out]]
            freq[out] -= 1
            if freq[out] > 0:
                buckets[freq[out]].add(out)
            else:
                del freq[out]
            if freq[in_val] > 0:
                buckets[freq[in_val]].remove(in_val)
                if not buckets[freq[in_val]]:
                    del buckets[freq[in_val]]

            freq[in_val] += 1
            buckets[freq[in_val]].add(in_val)
            max_freq = max(buckets.keys())
            sum_val += min(buckets[max_freq])
        
        return sum_val
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
