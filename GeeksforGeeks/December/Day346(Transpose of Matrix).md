--- ❤️ ---

# 🚀 _Day 346. Transpose of Matrix_ 🧠


The problem can be found at the following link: [Problem Link](https://www.geeksforgeeks.org/problems/transpose-of-matrix-1587115621/1)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
  public:
    vector<vector<int>> transpose(vector<vector<int>>& mat) {
        int n = mat.size();
        
        for (int i = 0; i < n; i++) {
            for (int j = i + 1; j < n; j++) {
                swap(mat[i][j], mat[j][i]);
            }
        }
        
        return mat;
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
