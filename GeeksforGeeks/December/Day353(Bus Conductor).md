
# 🚀 _Day 353. Bus Conductor_ 🧠


The problem can be found at the following link: [Problem Link](https://www.geeksforgeeks.org/problems/bus-conductor--170647/1)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int findMoves(vector<int>& c, vector<int>& p) {
        sort(c.begin(), c.end());
        sort(p.begin(), p.end());
        int res = 0, n = c.size();
        for (int i = 0; i < n; i++) res += abs(c[i] - p[i]);
        return res;
    }
};
```

## Code (Java)

```java

```

## Code (Python)

```python

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
