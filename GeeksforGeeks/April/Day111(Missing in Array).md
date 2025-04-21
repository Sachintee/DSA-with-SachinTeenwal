---
Difficulty: Easy
Source: 160 Days of Problem Solving
Tags:
  - Bit Manipulation
  - Arrays
  - Searching
  - Bit Magic
---

# 🚀 _Day 111. Missing in Array_ 🧠

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/bit-manipulation-gfg-160/problem/missing-number-in-array1416)  

## 💡 **Problem Description:**

You are given an array `arr[]` of size **n - 1** that contains distinct integers in the range from **1 to n** (inclusive).  
The array represents a permutation of numbers from `1` to `n` with **one number missing**. Your task is to **find the missing number**.  


## Code(C++)
```cpp
class Solution{
public:
    int missingNum(vector<int>&a){
        int x=0,n=a.size()+1;
        for(int i=0;i<a.size();++i) x^=a[i]^(i+1);
        return x^n;
    }
};
```

## Code (Java)

```java
class Solution {
    int missingNum(int[] a) {
        int x = 0;
        for (int i = 0; i < a.length; ++i) x ^= a[i] ^ (i + 1);
        return x ^ (a.length + 1);
    }
}
```

## Code (Python)

```python
class Solution:
    def missingNum(self, a):
        x = 0
        for i, v in enumerate(a): x ^= v ^ (i + 1)
        return x ^ (len(a) + 1)
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
