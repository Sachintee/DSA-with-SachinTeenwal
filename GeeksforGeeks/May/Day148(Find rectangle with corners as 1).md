# *148. Find Rectangle with Corners as 1*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/find-rectangle-with-corners-as-1--141631/1)


## **🧩 Problem Description**

Given an `n × m` binary matrix `mat[][]` containing only `0`s and `1`s, determine if there exists a rectangle within the matrix such that all four corners of the rectangle are `1`. If such a rectangle exists, return `true`; otherwise, return `false`.


## Code(C++)
```cpp
class Solution {
  public:
    bool ValidCorner(vector<vector<int>>& mat) {
        int n = mat.size(), m = mat[0].size();
        for (int i = 0; i < n; ++i)
            for (int j = i + 1; j < n; ++j) {
                int cnt = 0;
                for (int k = 0; k < m; ++k)
                    cnt += mat[i][k] & mat[j][k];
                if (cnt > 1) return true;
            }
        return false;
    }
};
```

## Code (Java)

```java
class Solution {
    public boolean ValidCorner(int[][] mat) {
        int n = mat.length, m = mat[0].length;
        for (int i = 0; i < n; i++)
            for (int j = i + 1; j < n; j++) {
                int cnt = 0;
                for (int k = 0; k < m; k++)
                    cnt += mat[i][k] & mat[j][k];
                if (cnt > 1) return true;
            }
        return false;
    }
}
```

## Code (Python)

```python
class Solution:
    def ValidCorner(self, mat):
        n, m = len(mat), len(mat[0])
        for i in range(n):
            for j in range(i + 1, n):
                if sum(mat[i][k] & mat[j][k] for k in range(m)) > 1:
                    return True
        return False
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
