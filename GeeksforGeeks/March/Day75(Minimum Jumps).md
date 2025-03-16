---
Difficulty: Medium  
Source: 160 Days of Problem Solving  
Tags:
  - Dynamic Programming
  - Greedy
  - Arrays
---

# 🚀 _Day 75. Minimum Jumps_ 🧠

The problem can be found at the following link: [Question Link](http://geeksforgeeks.org/batch/gfg-160-problems/track/dynamic-programming-gfg-160/problem/minimum-number-of-jumps-1587115620)  

## 💡 **Problem Description:**

Given an array `arr[]` of non-negative integers, each element represents the **maximum number of steps** that can be taken forward from that index.  

Find the **minimum number of jumps** required to reach the last index.  
If the last index is not reachable, return `-1`.  


## Code(C++)
```cpp
class Solution {
  public:
    int minJumps(vector<int>& arr) {
        int n = arr.size(), jumps = 0, farthest = 0, end = 0;
        if (n == 1) return 0;
        for (int i = 0; i < n - 1; i++) {
            farthest = max(farthest, i + arr[i]);
            if (i == end) {
                jumps++;
                end = farthest;
                if (end >= n - 1) return jumps;
            }
        }
        return -1;
    }
};
```

## Code (Java)

```java
class Solution {
    static int minJumps(int[] arr) {
        int n = arr.length, jumps = 0, farthest = 0, end = 0;
        if (n == 1) return 0;
        for (int i = 0; i < n - 1; i++) {
            farthest = Math.max(farthest, i + arr[i]);
            if (i == end) {
                jumps++;
                end = farthest;
                if (end >= n - 1) return jumps;
            }
        }
        return -1;
    }
}
```

## Code (Python)

```python
class Solution:
    def minJumps(self, arr):
        n, jumps, farthest, end = len(arr), 0, 0, 0
        if n == 1: return 0
        for i in range(n - 1):
            farthest = max(farthest, i + arr[i])
            if i == end:
                jumps += 1
                end = farthest
                if end >= n - 1: return jumps
        return -1
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
