---
Difficulty: Easy
Source: 160 Days of Problem Solving
Tags:
  - Bit Manipulation
  - two-pointer-algorithm
  - Arrays
---

# 🚀 _Day 110. Find Only Repetitive Element from 1 to n-1_ 🧠


The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/bit-manipulation-gfg-160/problem/find-repetitive-element-from-1-to-n-1)  

## 💡 **Problem Description:**

Given an array `arr[]` of size `n`, filled with numbers from `1` to `n-1` in random order. The array has **only one repetitive element**. Your task is to find this **repeating element**.


## Code(C++)
```cpp
class Solution {
  public:
    int findDuplicate(vector<int>& a) {
        int s = a[0], f = a[0];
        do { 
            s = a[s];
            f = a[a[f]];
        } while (s != f);
        f = a[0];
        while (s != f) { 
            s = a[s];
            f = a[f];
        }
        return s;
    }
};
```

## Code (Java)

```java
class Solution {
    public int findDuplicate(int[] a) {
        int s = a[0], f = a[0];
        do { 
            s = a[s]; 
            f = a[a[f]];
        } while (s != f);
        f = a[0];
        while (s != f) { 
            s = a[s];
            f = a[f];
        }
        return s;
    }
}
```

## Code (Python)

```python
class Solution:
    def findDuplicate(self, a):
        s = f = a[0]
        while True:
            s = a[s]
            f = a[a[f]]
            if s == f: break
        f = a[0]
        while s != f:
            s = a[s]
            f = a[f]
        return s
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
