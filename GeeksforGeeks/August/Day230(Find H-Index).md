---
title: "🔢 Find H-Index | GFG Solution 🔍"
keywords🏷️: ["🔢 h-index", "🏷️ bucket counting", "📊 sorting", "🔍 binary search", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Find H-Index problem: calculate researcher's h-index using optimal bucket counting technique with linear time complexity. 🚀"
date: 📅 2025-08-18
---

# *230. Find H-Index*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/find-h-index--165609/1)

## **🧩 Problem Description**

You are given an array `citations[]`, where each element `citations[i]` represents the number of citations received by the ith paper of a researcher. Your task is to calculate the researcher's **H-index**.

The **H-index** is defined as the maximum value H, such that the researcher has published **at least H papers**, and all those papers have citation value **greater than or equal to H**.


## Code(C++)
```cpp
class Solution {
public:
    int hIndex(vector<int>& citations) {
        int n = citations.size();
        vector<int> bucket(n + 1, 0);
        
        for (int c : citations) bucket[min(c, n)]++;
        
        int count = 0;
        for (int i = n; i >= 0; i--) {
            count += bucket[i];
            if (count >= i) return i;
        }
        return 0;
    }
};
```

## Code (Java)

```java
class Solution {
    public int hIndex(int[] citations) {
        int n = citations.length;
        int[] bucket = new int[n + 1];
        
        for (int c : citations) bucket[Math.min(c, n)]++;
        
        int count = 0;
        for (int i = n; i >= 0; i--) {
            count += bucket[i];
            if (count >= i) return i;
        }
        return 0;
    }
}
```

## Code (Python)

```python
class Solution:
    def hIndex(self, citations):
        n = len(citations)
        bucket = [0] * (n + 1)
        
        for c in citations:
            bucket[min(c, n)] += 1
        
        count = 0
        for i in range(n, -1, -1):
            count += bucket[i]
            if count >= i:
                return i
        return 0
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
