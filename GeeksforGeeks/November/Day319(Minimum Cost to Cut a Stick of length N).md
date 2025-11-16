--- ❤️ ---

# 🚀 _Day 319. Minimum Cost to Cut a Stick of length N_ 🧠


The problem can be found at the following link: [Problem Link]()

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int minCutCost(int n, vector<int>& cuts) {
        cuts.push_back(0);
        cuts.push_back(n);
        sort(cuts.begin(), cuts.end());
        int sz = cuts.size();
        vector<vector<int>> dp(sz, vector<int>(sz, 0));
        for (int gap = 2; gap < sz; gap++) {
            for (int i = 0; i + gap < sz; i++) {
                int j = i + gap;
                dp[i][j] = INT_MAX;
                for (int k = i + 1; k < j; k++) {
                    dp[i][j] = min(dp[i][j], dp[i][k] + dp[k][j] + cuts[j] - cuts[i]);
                }
            }
        }
        return dp[0][sz - 1];
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
