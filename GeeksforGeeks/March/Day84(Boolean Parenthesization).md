---
Difficulty: Hard  
Source: 160 Days of Problem Solving  
Tags:
  - Dynamic Programming
---

# 🚀 _Day 84. Boolean Parenthesization_ 🧠


The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/dynamic-programming-gfg-160/problem/boolean-parenthesization5610)

## 💡 **Problem Description:** 

Given a **boolean expression** `s` consisting of:
- **Operands**:  
  - `'T'` → **True**  
  - `'F'` → **False**  
- **Operators**:  
  - `'&'` → **Boolean AND**  
  - `'|'` → **Boolean OR**  
  - `'^'` → **Boolean XOR**  

Count the **number of ways** we can parenthesize the expression such that it evaluates to **True**.

## Code(C++)
```cpp
class Solution {
  public:
    int countWays(string &s) {
        int n = s.size();
        vector<vector<int>> T(n, vector<int>(n)), F(n, vector<int>(n));
        for (int i = 0; i < n; i += 2) T[i][i] = s[i] == 'T', F[i][i] = s[i] == 'F';
        for (int l = 2; l < n; l += 2)
            for (int i = 0; i < n - l; i += 2) 
                for (int k = i + 1, j = i + l; k < j; k += 2) {
                    int lt = T[i][k - 1], lf = F[i][k - 1], rt = T[k + 1][j], rf = F[k + 1][j];
                    if (s[k] == '&') T[i][j] += lt * rt, F[i][j] += lt * rf + lf * rt + lf * rf;
                    else if (s[k] == '|') T[i][j] += lt * rt + lt * rf + lf * rt, F[i][j] += lf * rf;
                    else T[i][j] += lt * rf + lf * rt, F[i][j] += lt * rt + lf * rf;
                }
        return T[0][n - 1];
    }
};
```

## Code (Java)

```java
class Solution {
    static int countWays(String s) {
        int n = s.length();
        int[][] T = new int[n][n], F = new int[n][n];
        for (int i = 0; i < n; i += 2) T[i][i] = s.charAt(i) == 'T' ? 1 : 0;
        for (int i = 0; i < n; i += 2) F[i][i] = s.charAt(i) == 'F' ? 1 : 0;
        for (int l = 2; l < n; l += 2)
            for (int i = 0; i < n - l; i += 2)
                for (int k = i + 1, j = i + l; k < j; k += 2) {
                    int lt = T[i][k - 1], lf = F[i][k - 1], rt = T[k + 1][j], rf = F[k + 1][j];
                    if (s.charAt(k) == '&') {
                        T[i][j] += lt * rt;
                        F[i][j] += lt * rf + lf * rt + lf * rf;
                    } else if (s.charAt(k) == '|') {
                        T[i][j] += lt * rt + lt * rf + lf * rt;
                        F[i][j] += lf * rf;
                    } else {
                        T[i][j] += lt * rf + lf * rt;
                        F[i][j] += lt * rt + lf * rf;
                    }
                }
        return T[0][n - 1];
    }
}
```

## Code (Python)

```python
class Solution:
    def countWays(self, s):
        n = len(s)
        T, F = [[0] * n for _ in range(n)], [[0] * n for _ in range(n)]
        for i in range(0, n, 2): 
            T[i][i], F[i][i] = int(s[i] == 'T'), int(s[i] == 'F')
        for l in range(2, n, 2):
            for i in range(0, n - l, 2):
                for k, j in zip(range(i + 1, i + l, 2), [i + l] * (l // 2)):
                    lt, lf, rt, rf = T[i][k - 1], F[i][k - 1], T[k + 1][j], F[k + 1][j]
                    if s[k] == '&': 
                        T[i][j] += lt * rt
                        F[i][j] += lt * rf + lf * rt + lf * rf
                    elif s[k] == '|': 
                        T[i][j] += lt * rt + lt * rf + lf * rt
                        F[i][j] += lf * rf
                    else:  
                        T[i][j] += lt * rf + lf * rt
                        F[i][j] += lt * rt + lf * rf
        return T[0][n - 1]
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
