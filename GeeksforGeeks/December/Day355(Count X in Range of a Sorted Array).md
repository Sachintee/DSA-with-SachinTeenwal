--- ❤️ ---

# 🚀 _Day 355. Count X in Range of a Sorted Array_ 🧠


The problem can be found at the following link: [Problem Link](https://www.geeksforgeeks.org/problems/count-x-in-range-of-a-sorted-array/1)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
  public:
    vector<int> countXInRange(vector<int>& arr, vector<vector<int>>& queries) {
        unordered_map<int, vector<int>> pos;
        
        // Store indices for each value
        for (int i = 0; i < arr.size(); i++) {
            pos[arr[i]].push_back(i);
        }

        vector<int> ans;
        ans.reserve(queries.size());

        for (auto &q : queries) {
            int l = q[0], r = q[1], x = q[2];

            // If x not present
            if (pos.find(x) == pos.end()) {
                ans.push_back(0);
                continue;
            }

            auto &v = pos[x];

            // Count indices in [l, r]
            int cnt = upper_bound(v.begin(), v.end(), r) -
                      lower_bound(v.begin(), v.end(), l);

            ans.push_back(cnt);
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
