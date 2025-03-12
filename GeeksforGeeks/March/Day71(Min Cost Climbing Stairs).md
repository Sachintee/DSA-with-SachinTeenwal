---
Difficulty: Medium  
Source: 160 Days of Problem Solving  
Tags:
  - Dynamic Programming
---

# 🚀 _Day 71. Min Cost Climbing Stairs_ 🧠


The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/dynamic-programming-gfg-160/problem/min-cost-climbing-stairs)  

## 💡 **Problem Description:**

Given an array of integers `cost[]`, where `cost[i]` represents the cost of the `i-th` step on a staircase, you can either:  
- Pay the cost at `i-th` step and move **one step** forward.  
- Pay the cost at `i-th` step and move **two steps** forward.  

## Code(C++)
```cpp
class Solution {
  public:
    int minCostClimbingStairs(vector<int>& cost) {
        int a = cost[0], b = cost[1];
        for (int i = 2; i < cost.size(); i++)
            tie(a, b) = make_tuple(b, cost[i] + min(a, b));
        return min(a, b);
    }
};
```

## Code (Java)

```java
class Solution {
    public int minCostClimbingStairs(int[] cost) {
        int a = cost[0], b = cost[1];
        for (int i = 2; i < cost.length; i++) {
            int temp = b;
            b = cost[i] + Math.min(a, b);
            a = temp;
        }
        return Math.min(a, b);
    }
}
```

## Code (Python)

```python
class Solution:
    def minCostClimbingStairs(self, cost):
        for i in range(2, len(cost)):
            cost[i] += min(cost[i - 1], cost[i - 2])
        return min(cost[-1], cost[-2])
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
