---
title: "➕ Count pairs Sum in matrices | GFG Solution 🧮"
keywords🏷️: ["🔢 matrix pair sum", "💡 2D array", "🧠 two-pointer", "💥 brute-force", "📈 sorted matrix", "📘 GFG", "🏁 competitive programming", "📚 DSA"]

description: "✅ GFG solution for counting valid pairs from two matrices such that their sum equals X. Includes optimized two-pointer logic and more. 🚀"
date: 📅 2025-06-01
---

# *152. Count pairs Sum in matrices*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/count-pairs-sum-in-matrices/1)



## **🧩 Problem Description**

Given two matrices `mat1[][]` and `mat2[][]` of size `n x n`, where elements in each matrix are arranged in strictly ascending order (each row is sorted, and the last element of a row is smaller than the first element of the next row). You are given a target value `x`. Count all pairs `{a, b}` such that `a` is from `mat1` and `b` is from `mat2`, and `a + b = x`.



## Code(C++)
```cpp
class Solution {
  public:
    int countPairs(vector<vector<int>> &a, vector<vector<int>> &b, int x) {
        int r1 = 0, c1 = 0, r2 = b.size() - 1, c2 = b[0].size() - 1, cnt = 0;
        while (r1 < a.size() && r2 >= 0) {
            int sum = a[r1][c1] + b[r2][c2];
            if (sum == x) ++cnt, ++c1, --c2;
            else if (sum < x) ++c1;
            else --c2;
            if (c1 == a[0].size()) c1 = 0, ++r1;
            if (c2 < 0) c2 = b[0].size() - 1, --r2;
        }
        return cnt;
    }
};
```

## Code (Java)

```java
class Solution {
    int countPairs(int[][] a, int[][] b, int x) {
        int r1 = 0, c1 = 0, r2 = b.length - 1, c2 = b[0].length - 1, cnt = 0;
        while (r1 < a.length && r2 >= 0) {
            int sum = a[r1][c1] + b[r2][c2];
            if (sum == x) { cnt++; c1++; c2--; }
            else if (sum < x) c1++;
            else c2--;
            if (c1 == a[0].length) { c1 = 0; r1++; }
            if (c2 < 0) { c2 = b[0].length - 1; r2--; }
        }
        return cnt;
    }
}
```

## Code (Python)

```python
class Solution:
    def countPairs(self, a, b, x):
        r1 = c1 = 0
        r2, c2 = len(b) - 1, len(b[0]) - 1
        cnt = 0
        while r1 < len(a) and r2 >= 0:
            s = a[r1][c1] + b[r2][c2]
            if s == x:
                cnt += 1
                c1 += 1
                c2 -= 1
            elif s < x:
                c1 += 1
            else:
                c2 -= 1
            if c1 == len(a[0]):
                c1 = 0
                r1 += 1
            if c2 < 0:
                c2 = len(b[0]) - 1
                r2 -= 1
        return cnt
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
