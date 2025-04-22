---
Difficulty: Easy
Source: 160 Days of Problem Solving
Tags:
  - Bit Manipulation
  - Bit Magic
---

# 🚀 _Day 112. Unique Number I_ 🧠

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/bit-manipulation-gfg-160/problem/find-unique-number)


## 💡 **Problem Description:**

You are given an **unsorted array** of positive integers in which **every element occurs exactly twice**, except for **one element that appears only once**. Your task is to **find that unique number**.

## Code(C++)
```cpp
class Solution {
  public:
    int findUnique(vector<int> &a) {
        int r = 0;
        for (int x : a) r ^= x;
        return r;
    }
};
```

## Code (Java)

```java
class Solution {
    public int findUnique(int[] arr) {
        int r = 0;
        for (int x : arr) r ^= x;
        return r;
    }
}
```

## Code (Python)

```python
class Solution:
    def findUnique(self, arr):
        r = 0
        for x in arr: r ^= x
        return r
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
