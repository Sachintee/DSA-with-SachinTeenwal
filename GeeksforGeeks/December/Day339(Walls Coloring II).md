--- ❤️ ---

# 🚀 _Day 339. Walls Coloring II_ 🧠


The problem can be found at the following link: [Problem Link](https://www.geeksforgeeks.org/problems/walls-coloring-ii--170647/1)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int minCost(vector<vector<int>>& costs) {
        int n = costs.size(), m = costs[0].size();
        if (m == 1 && n > 1) return -1;
        int m1 = 0, m2 = 0, idx = -1;
        for (int i = 0; i < n; i++) {
            int nm1 = INT_MAX, nm2 = INT_MAX, nidx = -1;
            for (int j = 0; j < m; j++) {
                int c = costs[i][j] + (j == idx ? m2 : m1);
                if (c < nm1) { nm2 = nm1; nm1 = c; nidx = j; }
                else if (c < nm2) nm2 = c;
            }
            m1 = nm1; m2 = nm2; idx = nidx;
        }
        return m1;
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
