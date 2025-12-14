--- ❤️ ---

# 🚀 _Day 348. 2D Submatrix Sum Queries_ 🧠


The problem can be found at the following link: [Problem Link](https://www.geeksforgeeks.org/problems/2d-submatrix-sum-queries/1)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
  public:
    vector<int> prefixSum2D(vector<vector<int>> &mat, vector<vector<int>> &queries) {
        int n = mat.size(), m = mat[0].size();

        // Build 2D prefix sum matrix
        vector<vector<long long>> pref(n, vector<long long>(m, 0));

        for (int i = 0; i < n; i++) {
            for (int j = 0; j < m; j++) {
                pref[i][j] = mat[i][j];
                if (i > 0) pref[i][j] += pref[i - 1][j];
                if (j > 0) pref[i][j] += pref[i][j - 1];
                if (i > 0 && j > 0) pref[i][j] -= pref[i - 1][j - 1];
            }
        }

        vector<int> ans;
        for (auto &q : queries) {
            int r1 = q[0], c1 = q[1], r2 = q[2], c2 = q[3];

            long long sum = pref[r2][c2];

            if (r1 > 0) sum -= pref[r1 - 1][c2];
            if (c1 > 0) sum -= pref[r2][c1 - 1];
            if (r1 > 0 && c1 > 0) sum += pref[r1 - 1][c1 - 1];

            ans.push_back((int)sum);
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
