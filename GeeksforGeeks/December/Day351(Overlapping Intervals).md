--- ❤️ ---

# 🚀 _Day 351. Overlapping Intervals_ 🧠


The problem can be found at the following link: [Problem Link](https://www.geeksforgeeks.org/problems/overlapping-intervals--170633/1)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
  public:
    vector<vector<int>> mergeOverlap(vector<vector<int>>& arr) {
        if (arr.empty()) return {};

        // Step 1: sort by start time
        sort(arr.begin(), arr.end());

        vector<vector<int>> res;
        res.push_back(arr[0]);

        // Step 2: merge intervals
        for (int i = 1; i < arr.size(); i++) {
            if (arr[i][0] <= res.back()[1]) {
                // overlap → merge
                res.back()[1] = max(res.back()[1], arr[i][1]);
            } else {
                // no overlap
                res.push_back(arr[i]);
            }
        }

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
