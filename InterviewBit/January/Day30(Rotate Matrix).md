--- ❤️ ---

# 🚀 _Day 30. Rotate_Matrix_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/rotate-matrix/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
#include <vector>
using namespace std;

class Solution {
public:
    void rotate(vector<vector<int>>& A) {
        int N = A.size();

        // Step 1: Transpose the matrix
        for (int i = 0; i < N; i++) {
            for (int j = i + 1; j < N; j++) {
                swap(A[i][j], A[j][i]);
            }
        }

        // Step 2: Reverse each row
        for (int i = 0; i < N; i++) {
            reverse(A[i].begin(), A[i].end());
        }
    }
};

// Driver Code
int main() {
    Solution obj;
    vector<vector<int>> A = {{1, 2}, {3, 4}};
    obj.rotate(A);

    for (auto row : A) {
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
import java.util.*;

class Solution {
    public void rotate(int[][] A) {
        int N = A.length;

        // Step 1: Transpose the matrix
        for (int i = 0; i < N; i++) {
            for (int j = i + 1; j < N; j++) {
                int temp = A[i][j];
                A[i][j] = A[j][i];
                A[j][i] = temp;
            }
        }

        // Step 2: Reverse each row
        for (int i = 0; i < N; i++) {
            int left = 0, right = N - 1;
            while (left < right) {
                int temp = A[i][left];
                A[i][left] = A[i][right];
                A[i][right] = temp;
                left++;
                right--;
            }
        }
    }

    // Driver Code
    public static void main(String[] args) {
        Solution obj = new Solution();
        int[][] A = {{1, 2}, {3, 4}};
        obj.rotate(A);

        for (int[] row : A) {
            System.out.println(Arrays.toString(row));
        }
    }
}

```

## Code (Python)

```python
class Solution:
    def rotate(self, A):
        N = len(A)
        
        # Step 1: Transpose the matrix (swap A[i][j] with A[j][i])
        for i in range(N):
            for j in range(i + 1, N):
                A[i][j], A[j][i] = A[j][i], A[i][j]

        # Step 2: Reverse each row to get the 90-degree rotation
        for row in A:
            row.reverse()

        return A  # In-place modification

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---

<div align="center">
 <h3><b>❤️Visitor Count❤️</b></h3>
   <textalign="center">
   <h4>485</h4>
