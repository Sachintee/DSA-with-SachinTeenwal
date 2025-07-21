--- ❤️ ---

# 🚀 _Day 202. Maximum Path in Triangle_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/maximum-path-in-triangle/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int solve(vector<vector<int> > &A) {
        int n = A.size();
        
        // Start from second last row and go upwards
        for (int i = n - 2; i >= 0; i--) {
            for (int j = 0; j <= i; j++) {
                A[i][j] += max(A[i+1][j], A[i+1][j+1]);
            }
        }
        
        // The top element contains the maximum path sum
        return A[0][0];
    }
};

```

## Code (Java)

```java
public class Solution {
    public int solve(int[][] A) {
        int n = A.length;
        
        // Start from second last row and go upwards
        for (int i = n - 2; i >= 0; i--) {
            for (int j = 0; j <= i; j++) {
                A[i][j] += Math.max(A[i+1][j], A[i+1][j+1]);
            }
        }
        
        // The top element contains the maximum path sum
        return A[0][0];
    }
}

```

## Code (Python)

```python
class Solution:
    # @param A : list of list of integers
    # @return an integer
    def solve(self, A):
        n = len(A)
        # Start from second last row and go upwards
        for i in range(n-2, -1, -1):
            for j in range(i+1):
                # Update current cell with max of its two children
                A[i][j] += max(A[i+1][j], A[i+1][j+1])
        
        # The top cell will have the maximum path sum
        return A[0][0]

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
