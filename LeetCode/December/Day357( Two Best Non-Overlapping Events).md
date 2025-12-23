--- ❤️ ---

# 🚀 _Day 357.  Two Best Non-Overlapping Events_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/two-best-non-overlapping-events/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int maxTwoEvents(vector<vector<int>>& events) {
        ranges::sort(events);
        int n = events.size();
        vector<int> f(n + 1);
        for (int i = n - 1; ~i; --i) {
            f[i] = max(f[i + 1], events[i][2]);
        }
        int ans = 0;
        for (const auto& e : events) {
            int v = e[2];
            int left = 0, right = n;
            while (left < right) {
                int mid = (left + right) >> 1;
                if (events[mid][0] > e[1]) {
                    right = mid;
                } else {
                    left = mid + 1;
                }
            }
            if (left < n) {
                v += f[left];
            }
            ans = max(ans, v);
        }
        return ans;
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
