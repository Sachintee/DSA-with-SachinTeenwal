--- ❤️ ---

# 🚀 _Day 225. Max Rectangle in Binary Matrix_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/max-rectangle-in-binary-matrix/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <stack>
#include <algorithm>

using namespace std;

class Solution {
public:
    int maximalRectangle(vector<vector<int>>& matrix) {
        if (matrix.empty() || matrix[0].empty()) return 0;
        
        int rows = matrix.size();
        int cols = matrix[0].size();
        vector<int> heights(cols, 0);
        int max_area = 0;
        
        for (int i = 0; i < rows; ++i) {
            for (int j = 0; j < cols; ++j) {
                if (matrix[i][j] == 1) {
                    heights[j] += 1;
                } else {
                    heights[j] = 0;
                }
            }
            
            stack<int> st;
            for (int j = 0; j <= cols; ++j) {
                int h = (j == cols) ? 0 : heights[j];
                while (!st.empty() && h < heights[st.top()]) {
                    int height = heights[st.top()];
                    st.pop();
                    int width = st.empty() ? j : j - st.top() - 1;
                    max_area = max(max_area, height * width);
                }
                st.push(j);
            }
        }
        
        return max_area;
    }
};
```

## Code (Java)

```java
import java.util.Stack;

public class Solution {
    public int maximalRectangle(int[][] matrix) {
        if (matrix == null || matrix.length == 0 || matrix[0].length == 0) {
            return 0;
        }
        
        int rows = matrix.length;
        int cols = matrix[0].length;
        int[] heights = new int[cols];
        int maxArea = 0;
        
        for (int i = 0; i < rows; i++) {
            for (int j = 0; j < cols; j++) {
                if (matrix[i][j] == 1) {
                    heights[j] += 1;
                } else {
                    heights[j] = 0;
                }
            }
            
            Stack<Integer> stack = new Stack<>();
            for (int j = 0; j <= cols; j++) {
                int h = (j == cols) ? 0 : heights[j];
                while (!stack.isEmpty() && h < heights[stack.peek()]) {
                    int height = heights[stack.pop()];
                    int width = stack.isEmpty() ? j : j - stack.peek() - 1;
                    maxArea = Math.max(maxArea, height * width);
                }
                stack.push(j);
            }
        }
        
        return maxArea;
    }
}
```

## Code (Python)

```python
class Solution:
    def maximalRectangle(self, A):
        if not A or not A[0]:
            return 0
        
        rows = len(A)
        cols = len(A[0])
        max_area = 0
        
        # Initialize heights array
        heights = [0] * cols
        
        for i in range(rows):
            for j in range(cols):
                # Update the height of the current histogram bar
                if A[i][j] == 1:
                    heights[j] += 1
                else:
                    heights[j] = 0
            
            # Calculate the largest rectangle area in the current histogram
            stack = []
            for idx in range(cols + 1):
                # For the last iteration, we process all remaining elements in the stack
                h = heights[idx] if idx < cols else 0
                while stack and h < heights[stack[-1]]:
                    height = heights[stack.pop()]
                    width = idx if not stack else idx - stack[-1] - 1
                    max_area = max(max_area, height * width)
                stack.append(idx)
        
        return max_area
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
