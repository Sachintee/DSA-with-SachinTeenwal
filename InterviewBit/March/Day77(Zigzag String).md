--- ❤️ ---

# 🚀 _Day 77. Zigzag String_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/zigzag-string/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
#include <vector>
using namespace std;

class Solution {
public:
    string convert(string A, int B) {
        if (B == 1 || B >= A.length()) {
            return A;
        }

        vector<string> rows(B, "");
        int current_row = 0;
        int direction = 1; // 1 for down, -1 for up

        for (char ch : A) {
            rows[current_row] += ch;
            current_row += direction;

            // Change direction if we reach the top or bottom row
            if (current_row == 0 || current_row == B - 1) {
                direction *= -1;
            }
        }

        // Concatenate all rows to get the final result
        string result;
        for (const string& row : rows) {
            result += row;
        }

        return result;
    }
};

// Driver code
int main() {
    Solution sol;
    string A = "PAYPALISHIRING";
    int B = 3;
    cout << sol.convert(A, B) << endl; // Expected Output: "PAHNAPLSIIGYIR"
    return 0;
}

```

## Code (Java)

```java
class Solution {
    public String convert(String A, int B) {
        if (B == 1 || B >= A.length()) {
            return A;
        }

        StringBuilder[] rows = new StringBuilder[B];
        for (int i = 0; i < B; i++) {
            rows[i] = new StringBuilder();
        }

        int currentRow = 0;
        int direction = 1; // 1 for down, -1 for up

        for (char ch : A.toCharArray()) {
            rows[currentRow].append(ch);
            currentRow += direction;

            // Change direction if we reach the top or bottom row
            if (currentRow == 0 || currentRow == B - 1) {
                direction *= -1;
            }
        }

        // Concatenate all rows to get the final result
        StringBuilder result = new StringBuilder();
        for (StringBuilder row : rows) {
            result.append(row);
        }

        return result.toString();
    }

    // Driver code
    public static void main(String[] args) {
        Solution sol = new Solution();
        String A = "PAYPALISHIRING";
        int B = 3;
        System.out.println(sol.convert(A, B)); // Expected Output: "PAHNAPLSIIGYIR"
    }
}

```

## Code (Python)

```python
class Solution:
    def convert(self, A, B):
        if B == 1 or B >= len(A):
            return A
        
        # Create a list of strings for each row
        rows = [""] * B
        current_row = 0
        direction = 1  # 1 for down, -1 for up
        
        for char in A:
            rows[current_row] += char
            current_row += direction
            # Change direction if we reach the top or bottom row
            if current_row == 0 or current_row == B - 1:
                direction *= -1
        
        # Concatenate all rows to get the final result
        return ''.join(rows)
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
