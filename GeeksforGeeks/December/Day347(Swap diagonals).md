--- ❤️ ---

# 🚀 _Day 347. Swap diagonals_ 🧠


The problem can be found at the following link: [Problem Link](https://www.geeksforgeeks.org/problems/swap-major-and-minor-diagonals-of-a-square-matrix/1)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
  public:
    void swapDiagonal(vector<vector<int>> &mat) {
        int n = mat.size();
        
        for (int i = 0; i < n; i++) {
            int j = n - 1 - i;   // minor diagonal column index
            swap(mat[i][i], mat[i][j]);
        }
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
