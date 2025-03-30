---
Difficulty: Medium  
Source: 160 Days of Problem Solving  
Tags:
  - Greedy
---

# 🚀 _Day 89. Gas Station_ 🧠

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/greedy-gfg-160/problem/circular-tour-1587115620)  


## 💡 **Problem Description:** 

There are some gas stations along a **circular route**. You are given two integer arrays **gas[]** (the amount of gas at each station) and **cost[]** (the cost to travel to the next station).  

You have a car with an **unlimited gas tank** and you start the journey with an **empty tank** from one of the gas stations.  

Return the **index** of the starting gas station if it's possible to travel around the circuit without running out of gas at any station in a **clockwise direction**.  
If **no such starting station exists**, return **-1**.  
**Note:** If a solution exists, it is **guaranteed to be unique**.  


## Code(C++)
```cpp
class Solution {
  public:
    int startStation(vector<int>& gas, vector<int>& cost) {
        int total = 0, curr = 0, start = 0;
        for (int i = 0; i < gas.size(); i++) {
            int diff = gas[i] - cost[i];
            total += diff;
            curr += diff;
            if (curr < 0) start = i + 1, curr = 0;
        }
        return total >= 0 ? start : -1;
    }
};
```

## Code (Java)

```java
class Solution {
    public int startStation(int[] gas, int[] cost) {
        int total = 0, curr = 0, start = 0;
        for (int i = 0; i < gas.length; i++) {
            int diff = gas[i] - cost[i];
            total += diff;
            curr += diff;
            if (curr < 0) { start = i + 1; curr = 0; }
        }
        return total >= 0 ? start : -1;
    }
}
```

## Code (Python)

```python
class Solution:
    def startStation(self, gas, cost):
        total = curr = start = 0
        for i in range(len(gas)):
            diff = gas[i] - cost[i]
            total += diff
            curr += diff
            if curr < 0: start, curr = i + 1, 0
        return start if total >= 0 else -1
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
