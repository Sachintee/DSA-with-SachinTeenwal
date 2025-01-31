--- ❤️ ---
Difficulty: Hard
Source: 160 Days of Problem Solving  
Tags:
  - 
---

# 🚀 _Day 31. Solve the Sudoku_ 🧠


The problem can be found at the following link: [Problem Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/recursion-and-backtracking-gfg-160/problem/solve-the-sudoku-1587115621)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
#include <vector>
using namespace std;

class Solution {
public:
    void solveSudoku(vector<vector<int>>& mat) {
        int row[9] = {0}, col[9] = {0}, box[3][3] = {0};

        // Initializing bitmasks
        for (int y = 0; y < 9; y++) {
            for (int x = 0; x < 9; x++) {
                if (mat[y][x] > 0) {
                    int bit = 1 << mat[y][x];
                    row[y] |= bit;
                    col[x] |= bit;
                    box[y / 3][x / 3] |= bit;
                }
            }
        }

        function<bool(int, int)> backtrack = [&](int x, int y) {
            if (y == 9) return true;
            int nx = (x + 1) % 9, ny = (x == 8) ? y + 1 : y;

            if (mat[y][x] != 0) return backtrack(nx, ny);

            for (int num = 1; num <= 9; num++) {
                int bit = 1 << num;
                if ((row[y] & bit) || (col[x] & bit) || (box[y / 3][x / 3] & bit)) continue;

                row[y] |= bit;
                col[x] |= bit;
                box[y / 3][x / 3] |= bit;
                mat[y][x] = num;

                if (backtrack(nx, ny)) return true;

                row[y] &= ~bit;
                col[x] &= ~bit;
                box[y / 3][x / 3] &= ~bit;
                mat[y][x] = 0;
            }
            return false;
        };

        backtrack(0, 0);
    }
};

// Driver Code
int main() {
    vector<vector<int>> mat = {
        {5, 3, 0, 0, 7, 0, 0, 0, 0},
        {6, 0, 0, 1, 9, 5, 0, 0, 0},
        {0, 9, 8, 0, 0, 0, 0, 6, 0},
        {8, 0, 0, 0, 6, 0, 0, 0, 3},
        {4, 0, 0, 8, 0, 3, 0, 0, 1},
        {7, 0, 0, 0, 2, 0, 0, 0, 6},
        {0, 6, 0, 0, 0, 0, 2, 8, 0},
        {0, 0, 0, 4, 1, 9, 0, 0, 5},
        {0, 0, 0, 0, 8, 0, 0, 7, 9}
    };

    Solution obj;
    obj.solveSudoku(mat);

    for (auto row : mat) {
        for (int num : row) {
            cout << num << " ";
        }
        cout << endl;
    }
    return 0;
}

```

## Code (Java)

```java
class Solution {
    public void solveSudoku(int[][] mat) {
        int[] row = new int[9];
        int[] col = new int[9];
        int[][] box = new int[3][3];

        // Initializing bitmasks
        for (int y = 0; y < 9; y++) {
            for (int x = 0; x < 9; x++) {
                if (mat[y][x] > 0) {
                    int bit = 1 << mat[y][x];
                    row[y] |= bit;
                    col[x] |= bit;
                    box[y / 3][x / 3] |= bit;
                }
            }
        }

        backtrack(mat, row, col, box, 0, 0);
    }

    private boolean backtrack(int[][] mat, int[] row, int[] col, int[][] box, int x, int y) {
        if (y == 9) return true;
        int nx = (x + 1) % 9, ny = (x == 8) ? y + 1 : y;

        if (mat[y][x] != 0) return backtrack(mat, row, col, box, nx, ny);

        for (int num = 1; num <= 9; num++) {
            int bit = 1 << num;
            if ((row[y] & bit) != 0 || (col[x] & bit) != 0 || (box[y / 3][x / 3] & bit) != 0)
                continue;

            row[y] |= bit;
            col[x] |= bit;
            box[y / 3][x / 3] |= bit;
            mat[y][x] = num;

            if (backtrack(mat, row, col, box, nx, ny)) return true;

            row[y] &= ~bit;
            col[x] &= ~bit;
            box[y / 3][x / 3] &= ~bit;
            mat[y][x] = 0;
        }
        return false;
    }

    // Driver Code
    public static void main(String[] args) {
        int[][] mat = {
            {5, 3, 0, 0, 7, 0, 0, 0, 0},
            {6, 0, 0, 1, 9, 5, 0, 0, 0},
            {0, 9, 8, 0, 0, 0, 0, 6, 0},
            {8, 0, 0, 0, 6, 0, 0, 0, 3},
            {4, 0, 0, 8, 0, 3, 0, 0, 1},
            {7, 0, 0, 0, 2, 0, 0, 0, 6},
            {0, 6, 0, 0, 0, 0, 2, 8, 0},
            {0, 0, 0, 4, 1, 9, 0, 0, 5},
            {0, 0, 0, 0, 8, 0, 0, 7, 9}
        };

        Solution obj = new Solution();
        obj.solveSudoku(mat);

        for (int[] row : mat) {
            System.out.println(java.util.Arrays.toString(row));
        }
    }
}

```

## Code (Python)

```python
#User function Template for python3

class Solution:
    
    #Function to find a solved Sudoku. 
     def solveSudoku(self, mat):
#        3.5s
        rw=[0]*9
        for y in range(9):
            for ve in mat[y]:
                if ve>0:
                    rw[y]+=1<<ve
        cl=[0]*9
        for x in range(9):
            for ve in list(zip(*mat))[x]:
                if ve>0:
                    cl[x]+=1<<ve
        sq=[[0]*3 for _ in range(3)]
        for y in range(9):
            for x in range(9):
                ve=mat[y][x]
                if ve>0:
                    sq[y//3][x//3]+=1<<ve
        def bt(x=0,y=0):
            nonlocal mat,rw,cl,sq
            if y==9:
                return True
            nx=x+1
            ny=y
            if nx>=9:
                nx=0
                ny=y+1
            if mat[y][x]==0:
                for cand in range(1,10):
                    if (1<<cand)&rw[y]:
                        continue
                    if (1<<cand)&cl[x]:
                        continue
                    if (1<<cand)&sq[y//3][x//3]:
                        continue
                    rw[y]+=1<<cand
                    cl[x]+=1<<cand
                    sq[y//3][x//3]+=1<<cand
                    mat[y][x]=cand
                    if bt(nx,ny):
                        return True
                    rw[y]-=1<<cand
                    cl[x]-=1<<cand
                    sq[y//3][x//3]-=1<<cand
                    mat[y][x]=0
                return False
            return bt(nx,ny)
        bt()
        return mat
        
        # Your code here

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---

<div align="center">
 <h3><b>❤️Visitor Count❤️</b></h3>
   <textalign="center">
   <h4>966</h4>
