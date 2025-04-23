---
Difficulty: Easy
Source: 160 Days of Problem Solving
Tags:
  - Bit Manipulation
  - Bit Magic
---

# 🚀 _Day 113. Unique Number II_ 🧠

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/bit-manipulation-gfg-160/problem/finding-the-numbers0215)  

## 💡 **Problem Description:**

Given an array `arr[]` of size **2*N + 2**, where **2*N** elements appear in pairs and **two elements appear only once**, your task is to find those two **distinct unique numbers** and return them in **increasing order**.  


## Code(C++)
```cpp
class Solution {
  public:
    vector<int> singleNum(vector<int>& A) {
        int x = 0, a = 0, b = 0;
        for (int n : A) x ^= n;
        for (int n : A) (n & (x & -x) ? a : b) ^= n;
        return a < b ? vector<int>{a, b} : vector<int>{b, a};
    }
};
```

## Code (Java)

```java
class Solution {
    public int[] singleNum(int[] arr) {
        int x = 0, a = 0, b = 0;
        for (int n : arr) x ^= n;
        for (int n : arr) if ((n & (x & -x)) != 0) a ^= n; else b ^= n;
        return a < b ? new int[]{a, b} : new int[]{b, a};
    }
}
```

## Code (Python)

```python
class Solution:
    def singleNum(self, arr):
        x = 0
        for n in arr: x ^= n
        a = b = 0
        for n in arr:
            (a, b) = (a ^ n, b) if n & (x & -x) else (a, b ^ n)
        return [a, b] if a < b else [b, a]
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
