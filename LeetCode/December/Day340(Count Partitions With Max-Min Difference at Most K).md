--- ❤️ ---

# 🚀 _Day 340. Count Partitions With Max-Min Difference at Most K_ 🧠


The problem can be found at the following link: [Problem Link](Count Partitions With Max-Min Difference at Most K)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int countPartitions(vector<int>& nums, int k) {
        const int mod = 1e9 + 7;
        multiset<int> sl;
        int n = nums.size();
        vector<int> f(n + 1, 0), g(n + 1, 0);
        f[0] = 1;
        g[0] = 1;
        int l = 1;
        for (int r = 1; r <= n; ++r) {
            int x = nums[r - 1];
            sl.insert(x);
            while (*sl.rbegin() - *sl.begin() > k) {
                sl.erase(sl.find(nums[l - 1]));
                ++l;
            }
            f[r] = (g[r - 1] - (l >= 2 ? g[l - 2] : 0) + mod) % mod;
            g[r] = (g[r - 1] + f[r]) % mod;
        }
        return f[n];
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
