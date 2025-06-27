---
title: "📱 Mobile Numeric Keypad | GFG Solution 🔢"
keywords🏷️: ["📱 mobile keypad", "🔢 dynamic programming", "📊 2D array", "🎯 unique sequences", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Mobile Numeric Keypad problem: count unique sequences of length n using keypad movements with dynamic programming. 🚀"
date: 📅 2025-06-27
---

# *178. Mobile Numeric Keypad*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/mobile-numeric-keypad5456/1)

## **🧩 Problem Description**

You have a standard numeric keypad on a mobile phone. You can press the current button or any button that is directly **above, below, left, or right** of it. Diagonal movements and pressing the bottom row corner buttons (* and #) are **not allowed**.

Given an integer `n`, determine how many **unique sequences** of length `n` can be formed by pressing buttons on the keypad, starting from any digit.

## Code(C++)
```cpp
class Solution {
public:
    int getCount(int n) {
        int ans = 0;
        vector<vector<int>> p(4, vector<int>(3, 1)), c(4, vector<int>(3));
        p[3][0] = p[3][2] = 0;
        vector<vector<int>> d = {{0,0},{0,1},{0,-1},{1,0},{-1,0}};
        for (int k = 2; k <= n; k++) {
            for (int i = 0; i < 4; i++)
                for (int j = 0; j < 3; j++) {
                    if (i==3&&(j==0||j==2)) continue;
                    c[i][j] = 0;
                    for (auto &v : d) {
                        int x = i+v[0], y = j+v[1];
                        if (x>=0 && x<4 && y>=0 && y<3) c[i][j] += p[x][y];
                    }
                }
            p = c;
        }
        for (auto &r : p) for (int v : r) ans += v;
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    public int getCount(int n) {
        int[][] p = new int[4][3], c = new int[4][3];
        for (int i = 0; i < 4; i++) for (int j = 0; j < 3; j++) p[i][j] = 1;
        p[3][0] = p[3][2] = 0;
        int[][] d = {{0,0},{0,1},{0,-1},{1,0},{-1,0}};
        for (int k = 2; k <= n; k++) {
            for (int i = 0; i < 4; i++)
                for (int j = 0; j < 3; j++) {
                    if (i==3&&(j==0||j==2)) continue;
                    c[i][j] = 0;
                    for (int[] v : d) {
                        int x = i + v[0], y = j + v[1];
                        if (x >= 0 && x < 4 && y >= 0 && y < 3) c[i][j] += p[x][y];
                    }
                }
            for (int i = 0; i < 4; i++) System.arraycopy(c[i], 0, p[i], 0, 3);
        }
        int ans = 0;
        for (int[] r : p) for (int v : r) ans += v;
        return ans;
    }
}
```

## Code (Python)

```python
class Solution:
    def getCount(self, n):
        p = [[1]*3 for _ in range(4)]
        p[3][0] = p[3][2] = 0
        d = [(0,0),(0,1),(0,-1),(1,0),(-1,0)]
        for _ in range(2,n+1):
            c = [[0]*3 for _ in range(4)]
            for i in range(4):
                for j in range(3):
                    if i==3 and j in (0,2): continue
                    for dx,dy in d:
                        x,y = i+dx,j+dy
                        if 0<=x<4 and 0<=y<3: c[i][j] += p[x][y]
            p = c
        return sum(sum(r) for r in p)
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
