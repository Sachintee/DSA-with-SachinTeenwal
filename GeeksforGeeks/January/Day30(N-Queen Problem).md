---
Difficulty: Hard
Source: 160 Days of Problem Solving  
Tags:
  - Recursion
  - Backtracking
---

# 🚀 _Day 30. N-Queen Problem_ 🧠


The problem can be found at the following link: [Problem Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/recursion-and-backtracking-gfg-160/problem/powx-n)

## 💡 **Problem Description:**

You are given a floating point number `b` and an integer `e`, and your task is to calculate \( b^e \) (b raised to the power of e).

## Code(C++)
```cpp
#include <vector>
using namespace std;

class Solution {
private:
    vector<vector<int>> result;
    int row[10];

    bool place(int r, int c) {
        for (int prev = 0; prev < c; prev++) {
            if (row[prev] == r || abs(row[prev] - r) == abs(prev - c))
                return false;
        }
        return true;
    }

    void bt(int c, int n) {
        if (c == n) {
            vector<int> temp;
            for (int i = 0; i < n; i++) 
                temp.push_back(row[i] + 1);
            result.push_back(temp);
            return;
        }
        for (int i = 0; i < n; i++) {
            if (place(i, c)) {
                row[c] = i;
                bt(c + 1, n);
            }
        }
    }

public:
    vector<vector<int>> nQueen(int n) {
        result.clear();
        bt(0, n);
        return result;
    }
};


```

## Code (Java)

```java
import java.util.ArrayList;
import java.util.List;

class Solution {
    private List<List<Integer>> result;
    private int[] row = new int[10];

    private boolean place(int r, int c) {
        for (int prev = 0; prev < c; prev++) {
            if (row[prev] == r || Math.abs(row[prev] - r) == Math.abs(prev - c))
                return false;
        }
        return true;
    }

    private void bt(int c, int n) {
        if (c == n) {
            List<Integer> temp = new ArrayList<>();
            for (int i = 0; i < n; i++) 
                temp.add(row[i] + 1);
            result.add(temp);
            return;
        }
        for (int i = 0; i < n; i++) {
            if (place(i, c)) {
                row[c] = i;
                bt(c + 1, n);
            }
        }
    }

    public List<List<Integer>> nQueen(int n) {
        result = new ArrayList<>();
        bt(0, n);
        return result;
    }
}


```

## Code (Python)

```python
#User function Template for python3

class Solution:
    def __init__(self):
        self.result = []
        self.row = [0] * 10
    
    def place(self, r, c):
        for prev in range(c):
            if self.row[prev] == r or abs(self.row[prev] - r) == abs(prev - c):
                return False
        return True

    def bt(self, c, n):
        if c == n:
            self.result.append([self.row[i] + 1 for i in range(n)])
            return
        for i in range(n):
            if self.place(i, c):
                self.row[c] = i
                self.bt(c + 1, n)

    def nQueen(self, n):
        self.result = []
        self.bt(0, n)
        return self.result
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---

<div align="center">
 <h3><b>❤️Visitor Count❤️</b></h3>
   <textalign="center">
   <h4>783</h4>
