---
Difficulty: Medium  
Source: 160 Days of Problem Solving  
Tags:
  - Dynamic Programming
  - sliding-window
  - Mathematical
---

# 🚀 _Day 70. Ways to Reach the n'th Stair_ 🧠


The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/dynamic-programming-gfg-160/problem/count-ways-to-reach-the-nth-stair-1587115620)  

## 💡 **Problem Description:**

There are `n` stairs, and a person standing at the bottom wants to reach the top. The person can climb either **1 stair** or **2 stairs** at a time. Your task is to **count the number of ways** the person can reach the top (order matters).  


## Code(C++)
```cpp
class Solution {
public:
    long long countWays(int n) {
        long long a = 1, b = 1;
        for (int i = 2; i <= n; i++) 
            tie(a, b) = make_tuple(b, a + b);
        return b;
    }
};
```

## Code (Java)

```java
class Solution {
    public long countWays(int n) {
        long a = 1, b = 1;
        while (n-- > 1) {
            b += a;
            a = b - a;
        }
        return b;
    }
}
```

## Code (Python)

```python
class Solution:
    def countWays(self, n):
        a, b = 1, 1
        for _ in range(n - 1):
            a, b = b, a + b
        return b
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
