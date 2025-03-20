---
Difficulty: Hard  
Source: 160 Days of Problem Solving  
Tags:
  - Dynamic Programming
  - Arrays
---

# 🚀 _Day 79. Stock Buy and Sell – Max 2 Transactions Allowed_ 🧠


The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/dynamic-programming-gfg-160/problem/buy-and-sell-a-share-at-most-twice)  

## 💡 **Problem Description:**

In daily share trading, a trader buys shares and sells them on the same day. Given an array **prices[]** representing stock prices throughout the day, find the **maximum profit** a trader could have made with at most **2 transactions**.  


## Code(C++)
```cpp
class Solution {
  public:
    int maxProfit(vector<int>& a) {
        int b1 = INT_MAX, s1 = 0, b2 = INT_MAX, s2 = 0;
        for (int p : a) {
            b1 = min(b1, p);
            s1 = max(s1, p - b1);
            b2 = min(b2, p - s1);
            s2 = max(s2, p - b2);
        }
        return s2;
    }
};
```

## Code (Java)

```java
class Solution {
    public int maxProfit(int[] a) {
        int b1 = Integer.MAX_VALUE, s1 = 0, b2 = Integer.MAX_VALUE, s2 = 0;
        for (int p : a) {
            b1 = Math.min(b1, p);
            s1 = Math.max(s1, p - b1);
            b2 = Math.min(b2, p - s1);
            s2 = Math.max(s2, p - b2);
        }
        return s2;
    }
}
```

## Code (Python)

```python
class Solution:
    def maxProfit(self, a):
        b1, s1, b2, s2 = float('inf'), 0, float('inf'), 0
        for p in a:
            b1, s1, b2, s2 = min(b1, p), max(s1, p - b1), min(b2, p - s1), max(s2, p - b2)
        return s2
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
