--- ❤️ ---

# 🚀 _Day 229. Min Sum Path in Triangle_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/min-sum-path-in-triangle/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <algorithm>

using namespace std;

class Solution {
public:
    int minimumTotal(vector<vector<int>>& triangle) {
        if (triangle.empty()) return 0;
        
        for (int i = triangle.size() - 2; i >= 0; --i) {
            for (int j = 0; j < triangle[i].size(); ++j) {
                triangle[i][j] += min(triangle[i+1][j], triangle[i+1][j+1]);
            }
        }
        
        return triangle[0][0];
    }
};
```

## Code (Java)

```java
import java.util.List;

public class Solution {
    public int minimumTotal(List<List<Integer>> triangle) {
        if (triangle == null || triangle.isEmpty()) return 0;
        
        for (int i = triangle.size() - 2; i >= 0; i--) {
            for (int j = 0; j < triangle.get(i).size(); j++) {
                int min = Math.min(triangle.get(i+1).get(j), triangle.get(i+1).get(j+1));
                triangle.get(i).set(j, triangle.get(i).get(j) + min);
            }
        }
        
        return triangle.get(0).get(0);
    }
}
```

## Code (Python)

```python
class Solution:
    def minimumTotal(self, A):
        if not A:
            return 0
        
        # Start from the second last row and move upwards
        for i in range(len(A)-2, -1, -1):
            for j in range(len(A[i])):
                A[i][j] += min(A[i+1][j], A[i+1][j+1])
        
        return A[0][0]
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
