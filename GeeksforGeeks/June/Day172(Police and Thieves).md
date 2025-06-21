---
title: "🚔 Police and Thieves | GFG Solution 👮‍♂️"
keywords🏷️: ["🚔 police thieves", "🎯 two pointers", "🔍 greedy algorithm", "📍 array traversal", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Police and Thieves problem: find maximum number of thieves that can be caught using optimal two-pointer greedy approach. 🚀"
date: 📅 2025-06-21
---

# *172. Police and Thieves*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/police-and-thieves--141631/1)

## **🧩 Problem Description**

Given an array `arr[]`, where each element contains either a **'P'** for policeman or a **'T'** for thief. Find the **maximum number of thieves** that can be caught by the police.

Keep in mind the following conditions:
- Each policeman can catch only **one thief**
- A policeman cannot catch a thief who is more than **k units away** from him


## Code(C++)
```cpp
class Solution {
public:
    int catchThieves(vector<char> &arr, int k) {
        int n = arr.size(), i = 0, j = 0, c = 0;
        while (i < n && j < n) {
            while (i < n && arr[i] != 'P') i++;
            while (j < n && arr[j] != 'T') j++;
            if (i < n && j < n && abs(i - j) <= k) i++, j++, c++;
            else if (j < i) j++;
            else i++;
        }
        return c;
    }
};
```

## Code (Java)

```java
class Solution {
    public int catchThieves(char[] arr, int k) {
        int i = 0, j = 0, n = arr.length, c = 0;
        while (i < n && j < n) {
            while (i < n && arr[i] != 'P') i++;
            while (j < n && arr[j] != 'T') j++;
            if (i < n && j < n && Math.abs(i - j) <= k) {
                i++; j++; c++;
            } else if (j < i) j++;
            else i++;
        }
        return c;
    }
}
```

## Code (Python)

```python
class Solution:
    def catchThieves(self, arr, k):
        i = j = c = 0
        n = len(arr)
        while i < n and j < n:
            while i < n and arr[i] != 'P':
                i += 1
            while j < n and arr[j] != 'T':
                j += 1
            if i < n and j < n and abs(i - j) <= k:
                i += 1
                j += 1
                c += 1
            elif j < i:
                j += 1
            else:
                i += 1
        return c
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
