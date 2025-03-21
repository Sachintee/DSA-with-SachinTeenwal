---
Difficulty: Medium  
Source: 160 Days of Problem Solving  
Tags:
  - Dynamic Programming
  - Arrays
---

# 🚀 _Day 80. Stickler Thief_ 🧠

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/dynamic-programming-gfg-160/problem/stickler-theif-1587115621)  

## 💡 **Problem Description:**

Stickler the thief wants to loot money from houses arranged in a line. However, he **cannot loot two consecutive houses** to avoid being caught. His goal is to **maximize** the total amount looted.  

Given an array **arr[]**, where `arr[i]` represents the amount of money in the `i`-th house, determine the **maximum amount** he can loot.  


## Code(C++)
```cpp
class Solution {
  public:
    int findMaxSum(vector<int>& arr) {
        int prev2 = 0, prev1 = 0;
        for (int num : arr) {
            int temp = max(prev1, prev2 + num);
            prev2 = prev1;
            prev1 = temp;
        }
        return prev1;
    }
};
```

## Code (Java)

```java
class Solution {
    public int findMaxSum(int[] arr) {
        int prev2 = 0, prev1 = 0;
        for (int num : arr) {
            int temp = Math.max(prev1, prev2 + num);
            prev2 = prev1;
            prev1 = temp;
        }
        return prev1;
    }
}
```

## Code (Python)

```python
class Solution:  
    def findMaxSum(self, arr):
        prev2 = prev1 = 0
        for num in arr:
            prev2, prev1 = prev1, max(prev1, prev2 + num)
        return prev1
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
