--- ❤️ ---

# 🚀 _Day 206. Jump Game Array_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/jump-game-array/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
using namespace std;

class Solution {
public:
    int canJump(vector<int> &A) {
        int n = A.size();
        int max_reach = 0;

        for (int i = 0; i < n; i++) {
            if (i > max_reach)
                return 0;
            max_reach = max(max_reach, i + A[i]);
        }

        return 1;
    }
};

```

## Code (Java)

```java
public class Solution {
    public int canJump(int[] A) {
        int n = A.length;
        int maxReach = 0;

        for (int i = 0; i < n; i++) {
            if (i > maxReach)
                return 0;
            maxReach = Math.max(maxReach, i + A[i]);
        }

        return 1;
    }
}

```

## Code (Python)

```python
class Solution:
    def canJump(self, A):
        n = len(A)
        max_reach = 0

        for i in range(n):
            if i > max_reach:
                return 0
            max_reach = max(max_reach, i + A[i])
        
        return 1

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
