--- ❤️ ---

# 🚀 _Day 109. Valid Sudoku_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/valid-sudoku/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <unordered_set>
using namespace std;

class Solution {
public:
    int isValidSudoku(vector<string> &A) {
        // Check each row
        for (int i = 0; i < 9; ++i) {
            unordered_set<char> seen;
            for (int j = 0; j < 9; ++j) {
                char num = A[i][j];
                if (num != '.') {
                    if (seen.find(num) != seen.end()) {
                        return 0;
                    }
                    seen.insert(num);
                }
            }
        }
        
        // Check each column
        for (int j = 0; j < 9; ++j) {
            unordered_set<char> seen;
            for (int i = 0; i < 9; ++i) {
                char num = A[i][j];
                if (num != '.') {
                    if (seen.find(num) != seen.end()) {
                        return 0;
                    }
                    seen.insert(num);
                }
            }
        }
        
        // Check each 3x3 sub-box
        for (int boxRow = 0; boxRow < 3; ++boxRow) {
            for (int boxCol = 0; boxCol < 3; ++boxCol) {
                unordered_set<char> seen;
                for (int i = 0; i < 3; ++i) {
                    for (int j = 0; j < 3; ++j) {
                        char num = A[boxRow * 3 + i][boxCol * 3 + j];
                        if (num != '.') {
                            if (seen.find(num) != seen.end()) {
                                return 0;
                            }
                            seen.insert(num);
                        }
                    }
                }
            }
        }
        
        return 1;
    }
};
```

## Code (Java)

```java
import java.util.HashSet;
import java.util.Set;

public class Solution {
    public int isValidSudoku(String[] A) {
        // Check each row
        for (int i = 0; i < 9; i++) {
            Set<Character> seen = new HashSet<>();
            for (int j = 0; j < 9; j++) {
                char num = A[i].charAt(j);
                if (num != '.') {
                    if (seen.contains(num)) {
                        return 0;
                    }
                    seen.add(num);
                }
            }
        }
        
        // Check each column
        for (int j = 0; j < 9; j++) {
            Set<Character> seen = new HashSet<>();
            for (int i = 0; i < 9; i++) {
                char num = A[i].charAt(j);
                if (num != '.') {
                    if (seen.contains(num)) {
                        return 0;
                    }
                    seen.add(num);
                }
            }
        }
        
        // Check each 3x3 sub-box
        for (int boxRow = 0; boxRow < 3; boxRow++) {
            for (int boxCol = 0; boxCol < 3; boxCol++) {
                Set<Character> seen = new HashSet<>();
                for (int i = 0; i < 3; i++) {
                    for (int j = 0; j < 3; j++) {
                        char num = A[boxRow * 3 + i].charAt(boxCol * 3 + j);
                        if (num != '.') {
                            if (seen.contains(num)) {
                                return 0;
                            }
                            seen.add(num);
                        }
                    }
                }
            }
        }
        
        return 1;
    }
}
```

## Code (Python)

```python
class Solution:
    # @param A : tuple of strings
    # @return an integer
    def isValidSudoku(self, A):
        # Check each row
        for row in A:
            seen = set()
            for num in row:
                if num != '.':
                    if num in seen:
                        return 0
                    seen.add(num)
        
        # Check each column
        for col in range(9):
            seen = set()
            for row in range(9):
                num = A[row][col]
                if num != '.':
                    if num in seen:
                        return 0
                    seen.add(num)
        
        # Check each 3x3 sub-box
        for box_row in range(0, 9, 3):
            for box_col in range(0, 9, 3):
                seen = set()
                for row in range(box_row, box_row + 3):
                    for col in range(box_col, box_col + 3):
                        num = A[row][col]
                        if num != '.':
                            if num in seen:
                                return 0
                            seen.add(num)
        
        return 1
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
