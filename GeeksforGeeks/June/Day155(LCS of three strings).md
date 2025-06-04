---
title: "📚 LCS of three Strings | GFG Solution 🧬"
keywords🏷️: ["🧬 LCS", "📘 dynamic programming", "📚 3D DP", "🧠 string problems", "📈 optimization", "📘 GFG", "🏁 competitive programming", "🔁 memoization"]
description: "✅ GFG solution for LCS of 3 strings: dynamic programming with full 3D table, space optimized 2D, and recursion with memoization. 💡"
date: 📅 2025-06-04
---

# *155. LCS of three Strings*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/lcs-of-three-strings0028/1)


## **🧩 Problem Description**

Given three strings `A`, `B`, and `C`, the task is to find the **length of the Longest Common Subsequence (LCS)** present in all three strings.

A **subsequence** is a sequence that appears in the same relative order, but not necessarily contiguous.


## Code(C++)
```cpp
class Solution {
  public:
    int lcsOf3(string& s1, string& s2, string& s3) {
        int n1 = s1.length(), n2 = s2.length(), n3 = s3.length();
        vector<vector<int>> prev(n2 + 1, vector<int>(n3 + 1, 0));
        vector<vector<int>> curr(n2 + 1, vector<int>(n3 + 1, 0));
        for (int i = 1; i <= n1; ++i) {
            for (int j = 1; j <= n2; ++j) {
                for (int k = 1; k <= n3; ++k) {
                    if (s1[i - 1] == s2[j - 1] && s2[j - 1] == s3[k - 1])
                        curr[j][k] = 1 + prev[j - 1][k - 1];
                    else
                        curr[j][k] = max({prev[j][k], curr[j - 1][k], curr[j][k - 1]});
                }
            }
            prev.swap(curr);
        }
        return prev[n2][n3];
    }
};
```

## Code (Java)

```java
class Solution {
    int lcsOf3(String s1, String s2, String s3) {
        int n1 = s1.length(), n2 = s2.length(), n3 = s3.length();
        int[][] prev = new int[n2 + 1][n3 + 1];
        int[][] curr = new int[n2 + 1][n3 + 1];
        for (int i = 1; i <= n1; ++i) {
            for (int j = 1; j <= n2; ++j) {
                for (int k = 1; k <= n3; ++k) {
                    if (s1.charAt(i - 1) == s2.charAt(j - 1) && 
                        s2.charAt(j - 1) == s3.charAt(k - 1))
                        curr[j][k] = 1 + prev[j - 1][k - 1];
                    else
                        curr[j][k] = Math.max(
                            Math.max(prev[j][k], curr[j - 1][k]),
                            curr[j][k - 1]
                        );
                }
            }
            int[][] temp = prev;
            prev = curr;
            curr = temp;
        }
        return prev[n2][n3];
    }
}
```

## Code (Python)

```python
class Solution:
    def lcsOf3(self, s1, s2, s3):
        n1, n2, n3 = len(s1), len(s2), len(s3)
        prev = [[0] * (n3 + 1) for _ in range(n2 + 1)]
        curr = [[0] * (n3 + 1) for _ in range(n2 + 1)]
        for i in range(1, n1 + 1):
            for j in range(1, n2 + 1):
                for k in range(1, n3 + 1):
                    if s1[i - 1] == s2[j - 1] == s3[k - 1]:
                        curr[j][k] = 1 + prev[j - 1][k - 1]
                    else:
                        curr[j][k] = max(
                            prev[j][k],
                            curr[j - 1][k],
                            curr[j][k - 1]
                        )
            prev, curr = curr, prev
        return prev[n2][n3]
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
