---
title: "🔗 Longest Span in two Binary Arrays | GFG Solution 🧮"
keywords🏷️: ["🔢 longest span", "⚖️ equal sum subarray", "🧮 binary arrays", "📊 prefix sums", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to find the longest span where two binary arrays have equal sum in the span. 🚀"
date: 📅 2025-06-07
---

# *158. Longest Span in two Binary Arrays*

The problem can be found here: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/longest-span-with-same-sum-in-two-binary-arrays5142/1)

## **🧩 Problem Description**

Given two binary arrays `a1[]` and `a2[]` of the same size, find the length of the longest span `(i, j)` such that the sum of elements from `a1[i]` to `a1[j]` is equal to the sum of elements from `a2[i]` to `a2[j]`.


## Code(C++)
```cpp
class Solution {
  public:
    int longestCommonSum(vector<int> &arr1, vector<int> &arr2) {
        int n = arr1.size(), res = 0;
        unordered_map<int, int> diffMap;
        int sum1 = 0, sum2 = 0;
        for (int i = 0; i < n; i++) {
            sum1 += arr1[i];
            sum2 += arr2[i];
            int diff = sum1 - sum2;
            if (diff == 0) res = i + 1;
            else if (diffMap.count(diff)) res = max(res, i - diffMap[diff]);
            else diffMap[diff] = i;
        }
        return res;
    }
};
```

## Code (Java)

```java
class Solution {
    public int longestCommonSum(int[] arr1, int[] arr2) {
        int n = arr1.length, sum1 = 0, sum2 = 0, res = 0;
        Map<Integer, Integer> map = new HashMap<>();
        for (int i = 0; i < n; i++) {
            sum1 += arr1[i];
            sum2 += arr2[i];
            int diff = sum1 - sum2;
            if (diff == 0)
                res = i + 1;
            else if (map.containsKey(diff))
                res = Math.max(res, i - map.get(diff));
            else
                map.put(diff, i);
        }
        return res;
    }
}
```

## Code (Python)

```python
class Solution:
    def longestCommonSum(self, arr1, arr2):
        n = len(arr1)
        sum1 = sum2 = res = 0
        diff_map = {}
        for i in range(n):
            sum1 += arr1[i]
            sum2 += arr2[i]
            diff = sum1 - sum2
            if diff == 0:
                res = i + 1
            elif diff in diff_map:
                res = max(res, i - diff_map[diff])
            else:
                diff_map[diff] = i
        return res
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
